<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alpha Justice - Web 3D Game</title>
    <link rel="stylesheet" href="style.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
</head>
<body>

    <div id="game-container"></div>

    <div id="ui-container">
        <div class="hud">
            <div class="stat">الصحة (HP): <span id="hp-value">100</span></div>
            <div class="stat">المستوى: <span id="level-value">1</span>/10</div>
            <div class="stat">الأعداء المتبقين: <span id="enemies-value">3</span></div>
        </div>

        <div class="controls">
            <div class="skills-bar">
                <button id="btn-attack" class="skill-btn">هجوم عادي ⚔️</button>
                <button id="btn-skill1" class="skill-btn special">صاعقة الرونز 🔥</button>
                <button id="btn-skill2" class="skill-btn special">عدالة ألفا ⚡</button>
            </div>
            <div class="movement-hint">استخدم أسهم الكيبورد أو أزرار الحركة للتنقل</div>
        </div>
    </div>

    <div id="screen-overlay" class="hidden">
        <h1 id="overlay-title">لقد فزت!</h1>
        <button id="btn-restart">اللعب مجدداً</button>
    </div>

    <script src="game.js"></script>
</body>
</html>
