<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Arda Agar | Portföy</title>
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  <style>
    /* Genel stil */
    body {
      margin: 0;
      font-family: 'Roboto', sans-serif;
      background: linear-gradient(120deg, #1f1c2c, #928dab);
      color: #fff;
      overflow-x: hidden;
    }

    header {
      text-align: center;
      padding: 60px 20px;
      background: rgba(0,0,0,0.3);
      animation: fadeIn 2s ease-in-out;
    }

    header h1 {
      font-size: 3rem;
      margin-bottom: 10px;
    }

    header p {
      font-size: 1.2rem;
      margin-top: 0;
    }

    /* Projeler kartları */
    .projects {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
      padding: 50px;
    }

    .card {
      background: rgba(255,255,255,0.05);
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 0 30px rgba(0,0,0,0.5);
      transform: translateY(0);
      transition: transform 0.5s ease, box-shadow 0.5s ease;
      cursor: pointer;
    }

    .card:hover {
      transform: translateY(-20px);
      box-shadow: 0 20px 40px rgba(0,0,0,0.7);
    }

    .card img {
      width: 100%;
      display: block;
      transition: transform 0.5s ease;
    }

    .card:hover img {
      transform: scale(1.05);
    }

    .card-content {
      padding: 20px;
    }

    .card-content h3 {
      margin: 0 0 10px 0;
      font-size: 1.5rem;
    }

    .card-content p {
      margin: 0;
      font-size: 1rem;
      color: #ddd;
    }

    /* Teknolojiler badge'leri */
    .tech {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      padding: 30px;
    }

    .tech img {
      width: 60px;
      transition: transform 0.3s;
    }

    .tech img:hover {
      transform: scale(1.3) rotate(10deg);
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 30px 10px;
      background: rgba(0,0,0,0.3);
    }

    /* Animasyonlar */
    @keyframes fadeIn {
      from {opacity: 0; transform: translateY(-30px);}
      to {opacity: 1; transform: translateY(0);}
    }
  </style>
</head>
<body>

<header>
  <h1>Merhaba, ben Arda! 👋</h1>
  <p>17 yaşında genç bir yazılımcıyım. Oyun modlama ve web geliştirme ile ilgileniyorum.<br>
  Başlıca diller: Lua, PHP, JS, Python, Java, C#, C++, C, Ruby, Go, Rust, Kotlin, TypeScript</p>
</header>

<section class="projects">
  <div class="card">
    <img src="https://media.giphy.com/media/3ohc0Vr7gq5Qf8x7cY/giphy.gif" alt="TaskMaster">
    <div class="card-content">
      <h3>TaskMaster</h3>
      <p>Yapılacaklar listesi uygulaması, karanlık mod ve localStorage desteği.</p>
      <p>🌐 <a href="https://geoarda.github.io/TaskMaster/" target="_blank">Demo</a> | 📁 <a href="https://github.com/geoarda/TaskMaster" target="_blank">Repo</a></p>
    </div>
  </div>

  <div class="card">
    <img src="https://media.giphy.com/media/xT9IgG50Fb7Mi0prBC/giphy.gif" alt="CodeCalcPro">
    <div class="card-content">
      <h3>CodeCalcPro</h3>
      <p>Modern hesap makinesi, renk temaları ve basit arayüz.</p>
      <p>🌐 <a href="https://geoarda.github.io/CodeCalcPro/" target="_blank">Demo</a> | 📁 <a href="https://github.com/geoarda/CodeCalcPro" target="_blank">Repo</a></p>
    </div>
  </div>

  <div class="card">
    <img src="https://media.giphy.com/media/26xBuwvrzP0FZxC6A/giphy.gif" alt="Bilgisayar Parçası Sitesi">
    <div class="card-content">
      <h3>Bilgisayar Parçası Satış Sitesi</h3>
      <p>Okul projesi, basit ve kullanışlı bilgisayar parçaları satış sitesi.</p>
      <p>🌐 <a href="http://bilgisayarparcasisatan.somee.com/" target="_blank">Demo</a></p>
    </div>
  </div>
</section>

<section class="tech">
  <img src="https://img.shields.io/badge/Lua-2C2D72?style=for-the-badge&logo=lua&logoColor=white" alt="Lua">
  <img src="https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JS">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=java&logoColor=white" alt="Java">
  <img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=c%2b%2b&logoColor=white" alt="C++">
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React">
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js">
</section>

<footer>
  <p>LinkedIn: <a href="https://www.linkedin.com/in/arda-a-020bb5380/" target="_blank">Arda Agar</a> | Discord: MoodyALostor</p>
  <p>Turn code into creativity, one project at a time. 🚀</p>
</footer>

</body>
</html>
