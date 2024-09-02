<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Discord Server</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #000; /* Black background */
            color: #fff; /* White text color */
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            height: 100vh;
        }
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background-color: #111;
            padding: 10px 0;
            text-align: center;
            z-index: 1000;
        }
        .nav-buttons {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-top: 10px;
        }
        .nav-buttons a {
            font-size: 16px;
            color: #fff;
            background-color: #7289da; /* Discord color */
            padding: 10px 20px;
            border-radius: 5px;
            text-decoration: none;
            border: none;
            cursor: pointer;
        }
        .nav-buttons a:hover {
            background-color: #5b6f9d;
        }
        .rgb-text {
            font-size: 24px;
            font-weight: bold;
            background: linear-gradient(45deg, red, orange, yellow, green, blue, indigo, violet);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            animation: rainbow 3s infinite linear;
        }
        @keyframes rainbow {
            0% { background-position: 0% 0%; }
            100% { background-position: 100% 100%; }
        }
        .container {
            background-color: #222; /* Dark grey background for the container */
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
            padding: 20px;
            text-align: center;
            max-width: 600px;
            width: 100%;
            margin-top: 60px; /* Add margin-top to account for fixed header */
        }
        h1 {
            color: #7289da; /* Discord color */
        }
        footer {
            position: fixed;
            bottom: 0;
            width: 100%;
            background-color: #111;
            color: #666;
            text-align: center;
            padding: 10px;
            font-size: 14px;
            background: linear-gradient(45deg, red, blue); /* Red to blue gradient */
            color: transparent;
            -webkit-background-clip: text;
            background-clip: text;
        }
        .section {
            display: none;
        }
        .section.active {
            display: block;
        }
        .view-counter {
            margin-top: 20px;
            font-size: 18px;
            color: #ccc;
        }
    </style>
</head>
<body>
    <header>
        <div class="rgb-text">Cevr's Modding Hub</div>
        <nav class="nav-buttons">
            <a href="#" onclick="showSection('home')">Home</a>
            <a href="#" onclick="showSection('about')">About</a>
            <a href="#" onclick="showSection('contact')">Contact</a>
            <a href="#" onclick="showSection('creator')">Creator</a>
        </nav>
    </header>
    
    <div id="home" class="container section active">
        <h1>Join Our Discord Server</h1>
        <div class="server-info">
            <p><strong>Server Name:</strong> Cevr's Modding Hub</p>
            <p><strong>Description:</strong> Join our community to discuss and collaborate on exciting projects!</p>
        </div>
        <a href="https://discord.gg/cGBJP43RKr" class="button" target="_blank">Join Now</a>
        <div class="view-counter" id="viewCounter">Views: 0</div>
    </div>
    
    <div id="about" class="container section">
        <h1>About Us</h1>
        <p>Welcome to the About page. Here you can learn more about our team and mission.</p>
    </div>
    
    <div id="contact" class="container section">
        <h1>Contact Us</h1>
        <p>For inquiries, please reach out to us at on discord cevr_official.</p>
    </div>
    
    <div id="creator" class="container section">
        <h1>Creator</h1>
        <p>This page is dedicated to the creator of this website.</p>
        <p><strong>Name:</strong> CEVR</p>
        <p><strong>Description:</strong> CEVR is the creator of This Websit is passionate about developing engaging web content.</p>
    </div>
    
    <footer>
        <p>&copy; 2024 CEVR Studios. All rights reserved. MADE BY CEVR</p>
    </footer>

    <script>
        // Function to show the selected section
        function showSection(sectionId) {
            const sections = document.querySelectorAll('.section');
            sections.forEach(section => {
                section.classList.remove('active');
            });
            document.getElementById(sectionId).classList.add('active');
        }

        // Function to update the view counter
        function updateViewCounter() {
            let viewCount = localStorage.getItem('viewCount');
            if (viewCount === null) {
                viewCount = 0;
            } else {
                viewCount = parseInt(viewCount, 10);
            }
            viewCount++;
            localStorage.setItem('viewCount', viewCount);
            document.getElementById('viewCounter').textContent = 'Views: ' + viewCount;
        }

        // Call the function when the page loads
        updateViewCounter();
    </script>
</body>
</html>
