<script type="text/javascript">
        var gk_isXlsx = false;
        var gk_xlsxFileLookup = {};
        var gk_fileData = {};
        function filledCell(cell) {
          return cell !== '' && cell != null;
        }
        function loadFileData(filename) {
        if (gk_isXlsx && gk_xlsxFileLookup[filename]) {
            try {
                var workbook = XLSX.read(gk_fileData[filename], { type: 'base64' });
                var firstSheetName = workbook.SheetNames[0];
                var worksheet = workbook.Sheets[firstSheetName];

                // Convert sheet to JSON to filter blank rows
                var jsonData = XLSX.utils.sheet_to_json(worksheet, { header: 1, blankrows: false, defval: '' });
                // Filter out blank rows (rows where all cells are empty, null, or undefined)
                var filteredData = jsonData.filter(row => row.some(filledCell));

                // Heuristic to find the header row by ignoring rows with fewer filled cells than the next row
                var headerRowIndex = filteredData.findIndex((row, index) =>
                  row.filter(filledCell).length >= filteredData[index + 1]?.filter(filledCell).length
                );
                // Fallback
                if (headerRowIndex === -1 || headerRowIndex > 25) {
                  headerRowIndex = 0;
                }

                // Convert filtered JSON back to CSV
                var csv = XLSX.utils.aoa_to_sheet(filteredData.slice(headerRowIndex)); // Create a new sheet from filtered array of arrays
                csv = XLSX.utils.sheet_to_csv(csv, { header: 1 });
                return csv;
            } catch (e) {
                console.error(e);
                return "";
            }
        }
        return gk_fileData[filename] || "";
        }
        </script>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Z DEVASTATION - Zombie Apocalypse Server</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            background-color: #1a1a1a;
            color: #e0e0e0;
            background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="25" cy="25" r="1" fill="%23ffffff" opacity="0.1"/><circle cx="75" cy="75" r="1" fill="%23ffffff" opacity="0.1"/><circle cx="50" cy="10" r="0.5" fill="%23ffffff" opacity="0.05"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
            background-attachment: fixed;
        }
        header {
            background-color: #057474;
            padding: 20px;
            text-align: center;
            border-bottom: 3px solid #8B0000;
        }
        h1 {
            margin: 0;
            color: #FF4500;
            font-size: 2.5em;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.8);
        }
        nav {
            background-color: #000;
            padding: 10px;
            text-align: center;
        }
        nav a {
            color: #e0e0e0;
            text-decoration: none;
            margin: 0 15px;
            font-weight: bold;
            transition: color 0.3s;
        }
        nav a:hover {
            color: #FF4500;
        }
        section {
            padding: 40px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        #home {
            text-align: center;
            background-color: rgba(0,0,0,0.3);
            border-radius: 10px;
            margin: 20px;
        }
        #about {
            background-color: rgba(139,0,0,0.2);
            border-left: 5px solid #8B0000;
        }
        #join {
            background-color: rgba(0,0,0,0.3);
            border-radius: 10px;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            margin: 10px 0;
            padding: 10px;
            background-color: rgba(255,255,255,0.1);
            border-radius: 5px;
        }
        .discord-btn {
            display: inline-block;
            background-color: #7289DA;
            color: white;
            padding: 15px 30px;
            text-decoration: none;
            border-radius: 5px;
            font-weight: bold;
            transition: background-color 0.3s;
        }
        .discord-btn:hover {
            background-color: #5B6EAE;
        }
        footer {
            background-color: #000;
            text-align: center;
            padding: 20px;
            border-top: 3px solid #8B0000;
            margin-top: 40px;
        }
        @media (max-width: 768px) {
            h1 { font-size: 2em; }
            nav a { display: block; margin: 5px 0; }
        }
    </style>
</head>
<body>
    <header>
        <h1>Z DEVASTATION</h1>
        <p>Zombie Apocalypse Roleplay Server</p>
    </header>
    <nav>
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#join">Join Us</a>
    </nav>
    <section id="home">
        <h2>Welcome to Z DEVASTATION</h2>
        <p>Step into a post-apocalyptic world overrun by zombies. Survive, build, and roleplay in a thrilling community-driven server!</p>
        <a href="#join" class="discord-btn">Join Our Discord</a>
    </section>
    <section id="about">
        <h2>About the Server</h2>
        <p>Z DEVASTATION is a dedicated roleplay server set in a zombie apocalypse. Our community thrives on immersive storytelling, survival mechanics, and cooperative gameplay.</p>
        <ul>
            <li>Custom lore and factions</li>
            <li>Dynamic events and missions</li>
            <li>Active and friendly staff team</li>
            <li>Regular updates and community feedback</li>
        </ul>
    </section>
    <section id="join">
        <h2>Join the Apocalypse</h2>
        <p>Ready to survive? Join our Discord to get started, meet the community, and dive into the roleplay!</p>
        <a href="https://discord.gg/QGEATMD36E" class="discord-btn">Join Discord Now</a>
    </section>
    <footer>
        <p>&copy; 2025 Z DEVASTATION. All rights reserved.</p>
    </footer>
</body>
</html>
