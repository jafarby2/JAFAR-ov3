<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>واجهة محل أسطورية</title>
  <style>
    body {
      margin: 0;
      font-family: 'Tahoma', sans-serif;
      background: linear-gradient(to right, #ffecd2, #fcb69f);
    }
    header {
      background-color: #2c3e50;
      color: white;
      padding: 20px;
      text-align: center;
    }
    nav {
      display: flex;
      justify-content: center;
      background-color: #34495e;
    }
    nav a {
      color: white;
      padding: 14px 20px;
      text-decoration: none;
      transition: background 0.3s;
    }
    nav a:hover {
      background-color: #1abc9c;
    }
    .hero {
      height: 400px;
      background: url('https://picsum.photos/1200/400?shop') center/cover no-repeat;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 40px;
      font-weight: bold;
      text-shadow: 2px 2px 5px #000;
    }
    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      padding: 40px;
    }
    .card {
      background: white;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      overflow: hidden;
      transition: transform 0.3s;
    }
    .card:hover {
      transform: scale(1.05);
    }
    .card img {
      width: 100%;
      height: 200px;
      object-fit: cover;
    }
    .card h3 {
      margin: 15px;
      color: #2c3e50;
    }
    .card p {
      margin: 0 15px 15px;
      color: #7f8c8d;
    }
    .btn {
      display: block;
      margin: 15px;
      padding: 10px;
      text-align: center;
      background-color: #1abc9c;
      color: white;
      text-decoration: none;
      border-radius: 5px;
      transition: background 0.3s;
    }
    .btn:hover {
      background-color: #16a085;
    }
    footer {
      background-color: #2c3e50;
      color: white;
      text-align: center;
      padding: 15px;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <header>
    <h1>متجر الأحلام</h1>
    <p>أفضل المنتجات بأجمل الأسعار</p>
  </header>
  <nav>
    <a href="#">الرئيسية</a>
    <a href="#">المنتجات</a>
    <a href="#">عروض</a>
    <a href="#">تواصل معنا</a>
  </nav>
  <div class="hero">مرحبا بكم في متجرنا ✨</div>
  <section class="products">
    <div class="card">
      <img src="https://picsum.photos/300/200?item1" alt="منتج 1">
      <h3>منتج 1</h3>
      <p>وصف قصير للمنتج.</p>
      <a href="#" class="btn">اشتري الآن</a>
    </div>
    <div class="card">
      <img src="https://picsum.photos/300/200?item2" alt="منتج 2">
      <h3>منتج 2</h3>
      <p>وصف قصير للمنتج.</p>
      <a href="#" class="btn">اشتري الآن</a>
    </div>
    <div class="card">
      <img src="https://picsum.photos/300/200?item3" alt="منتج 3">
      <h3>منتج 3</h3>
      <p>وصف قصير للمنتج.</p>
      <a href="#" class="btn">اشتري الآن</a>
    </div>
  </section>
  <footer>
    <p>© 2026 متجر الأحلام - جميع الحقوق محفوظة</p>
  </footer>
</body>
</html>