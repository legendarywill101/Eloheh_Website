<html>
<head>
    <title>Team Eloheh - Team 10</title>
    <style>
        body {
            background-color: #BD9A7A;
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        .container {
            display: flex;
            height: 100vh;
        }
        .nav {
            width: 25%;
            background-color: #999999;
            padding: 20px;
            box-sizing: border-box;
        }
        .main {
            width: 75%;
            padding: 0;
            box-sizing: border-box;
            overflow: hidden;
        }
        .nav ul {
            list-style-type: none;
            padding: 0;
        }
        .nav ul li {
            margin-bottom: 10px;
        }
        .nav ul li a {
            text-decoration: none;
            color: #000;
            cursor: pointer;
        }
        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
        .last-modified {
            font-size: 1.0em;
            color: #f0e68c;
            font-family: 'Times New Roman', Times, serif;
            margin-top: 20px;
        }
    </style>
</head>
<body onload="loadContent('home')">
    <div class="container">
        <div class="nav">
            <h3>Navigation</h3>
            <ul>
                <li><a onclick="loadContent('home')">Eloheh Home</a></li>
                <li><a onclick="loadExternal('https://adinayar.github.io/Eloheh1-2/')">Eloheh Story/History</a></li>
                <li><a onclick="loadExternal('https://tanishamittal22.github.io/MGMT382/')">Eloheh Products</a></li>
                <li><a onclick="loadExternal('https://hlumpcik04.github.io/')">Eloheh Services</a></li>
                <li><a onclick="loadExternal('https://legendarywill101.github.io/Eloheh-Inc-Company-Reviews/')">Eloheh Reviews</a></li>
            </ul>
            <p class="last-modified">Last modified: <span id="nav-modified"></span></p>
        </div>
        <div class="main">
            <iframe id="content-frame" srcdoc=""></iframe>
        </div>
    </div>

    <script>
        const pages = {
            home: `
                <h1>Welcome to Team Eloheh</h1>
                <h2>Team #10</h2>
                <p>Team Members:</p>
                <ul>
                    <li>William</li>
                    <li>Adi</li>
                    <li>Holden</li>
                    <li>Tanisha</li>
                </ul>
                <p style="font-size: 1.0em; color: #f0e68c; font-family: 'Times New Roman', Times, serif; margin-top: 20px;">
                    Last modified: ${new Date(document.lastModified).toLocaleString()}
                </p>
            `
        };

        function loadContent(page) {
            const frame = document.getElementById('content-frame');
            frame.removeAttribute('src');
            frame.setAttribute('srcdoc', pages[page]);
        }

        function loadExternal(url) {
            const frame = document.getElementById('content-frame');
            frame.removeAttribute('srcdoc');
            frame.setAttribute('src', url);
        }

        function showLastModified(id) {
            const date = new Date(document.lastModified);
            document.getElementById(id).textContent = date.toLocaleString();
        }

        document.addEventListener('DOMContentLoaded', () => {
            showLastModified('nav-modified');
        });
    </script>
</body>
</html>
