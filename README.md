<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>لعبة 3D - البطل ضد الوحوش</title>
  <style>
    body {
      margin: 0;
      background: #111;
      color: #fff;
      font-family: Tahoma, sans-serif;
      overflow: hidden;
    }
    #hud {
      position: absolute;
      top: 10px;
      left: 10px;
      background: rgba(0,0,0,0.5);
      padding: 10px;
      border-radius: 8px;
    }
    button {
      margin: 5px;
      padding: 10px;
      background: #444;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background: #666;
    }
  </style>
</head>
<body>
  <div id="hud">
    <h1>🎮 لعبة البطل</h1>
    <p>المستوى: <span id="level">1</span> | النقاط: <span id="score">0</span></p>
    <button onclick="attack()">هجوم ⚔️</button>
    <button onclick="skill()">مهارة ✨</button>
  </div>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
  <script>
    let scene, camera, renderer;
    let hero, monsters = [];
    let level = 1, score = 0;

    function init() {
      scene = new THREE.Scene();
      camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
      renderer = new THREE.WebGLRenderer();
      renderer.setSize(window.innerWidth, window.innerHeight);
      document.body.appendChild(renderer.domElement);

      // أرضية
      const planeGeometry = new THREE.PlaneGeometry(50, 50);
      const planeMaterial = new THREE.MeshBasicMaterial({color: 0x333333});
      const plane = new THREE.Mesh(planeGeometry, planeMaterial);
      plane.rotation.x = -Math.PI/2;
      scene.add(plane);

      // البطل
      const heroGeometry = new THREE.BoxGeometry(1, 2, 1);
      const heroMaterial = new THREE.MeshBasicMaterial({color: 0x00ff00});
      hero = new THREE.Mesh(heroGeometry, heroMaterial);
      hero.position.y = 1;
      scene.add(hero);

      camera.position.set(0, 5, 10);
      camera.lookAt(hero.position);

      spawnMonsters();
      animate();
    }

    function spawnMonsters() {
      monsters.forEach(m => scene.remove(m));
      monsters = [];
      let count = level * 2;
      for (let i = 0; i < count; i++) {
        const monsterGeometry = new THREE.SphereGeometry(1, 16, 16);
        const monsterMaterial = new THREE.MeshBasicMaterial({color: 0xff0000});
        const monster = new THREE.Mesh(monsterGeometry, monsterMaterial);
        monster.position.set(Math.random()*20-10, 1, Math.random()*20-10);
        scene.add(monster);
        monsters.push(monster);
      }
      // زعيم المستوى 5 و 10
      if (level === 5 || level === 10) {
        const bossGeometry = new THREE.BoxGeometry(3, 4, 3);
        const bossMaterial = new THREE.MeshBasicMaterial({color: 0x0000ff});
        const boss = new THREE.Mesh(bossGeometry, bossMaterial);
        boss.position.set(0, 2, -5);
        scene.add(boss);
        monsters.push(boss);
      }
    }

    function attack() {
      score += 10;
      document.getElementById("score").innerText = score;
      if (score >= level * 50) {
        level++;
        document.getElementById("level").innerText = level;
        if (level <= 10) spawnMonsters();
      }
    }

    function skill() {
      score += 25;
      document.getElementById("score").innerText = score;
    }

    function animate() {
      requestAnimationFrame(animate);
      renderer.render(scene, camera);
    }

    init();
  </script>
</body>
</html>