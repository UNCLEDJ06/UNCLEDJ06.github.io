<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Roman Empire</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@700&family=EB+Garamond&display=swap');

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #111;
      color: #f1c40f;
      font-family: 'EB Garamond', serif;
      text-align: center;
      padding: 20px;
    }

    header {
      background: linear-gradient(to bottom, #8B0000, #450000);
      padding: 30px 20px;
      border-bottom: 5px solid #f1c40f;
    }

    h1 {
      font-family: 'Cinzel', serif;
      font-size: 3.5rem;
      color: #f1c40f;
      text-shadow: 3px 3px 6px #000;
    }

    .spqr {
      width: 120px;
      margin: 15px auto;
      filter: drop-shadow(0 0 8px #f1c40f);
    }

    .discord-btn {
      display: inline-block;
      margin: 30px auto;
      padding: 16px 40px;
      background: #7289da;
      color: white;
      font-weight: bold;
      text-decoration: none;
      border-radius: 50px;
      font-size: 1.3rem;
      transition: 0.3s;
      box-shadow: 0 4px 10px rgba(0,0,0,0.5);
    }

    .discord-btn:hover {
      background: #5a6bc0;
      transform: scale(1.05);
    }

    .hierarchy-img {
      max-width: 90%;
      margin: 40px auto;
      border: 8px solid #f1c40f;
      border-radius: 12px;
      box-shadow: 0 0 20px rgba(241, 196, 15, 0.4);
    }

    footer {
      margin-top: 50px;
      padding: 20px;
      color: #aaa;
      font-size: 0.9rem;
    }

    @media (max-width: 768px) {
      h1 { font-size: 2.5rem; }
      .discord-btn { font-size: 1.1rem; padding: 14px 30px; }
    }
  </style>
</head>
<body>

  <header>
    <h1>ROMAN EMPIRE</h1>
    <img src="spqr.png" alt="SPQR" class="spqr" />
  </header>

  <main>
    <p style="font-size:1.3rem; margin:20px 0;">
      Join the legions. Serve the Emperor. Conquer Roblox.
    </p>

    <a href="https://discord.gg/egM8wEZuuX" target="_blank" class="discord-btn">
      ⚔️ JOIN DISCORD ⚔️
    </a>

    <h2 style="margin:30px 0; color:#f1c40f; font-family:'Cinzel',serif;">
      Command Hierarchy
    </h2>

    <!-- === YOUR IMAGE GOES HERE === -->
    <!-- Save your uploaded image as 'hierarchy.png' in the same folder -->
    <img src="hierarchy.png" alt="Roman Empire Hierarchy" class="hierarchy-img" />

  </main>

  <footer>
    &copy; 2025 Roman Empire | Roblox Group • All hail the Emperor
  </footer>

</body>
</html>
