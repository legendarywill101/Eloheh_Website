<html>
<head>
    <title>Team Eloheh - Team 10</title>
    <style>
        body {
            background-color: #d3d3d3;
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
            background-color: #BD9A7A;
            padding: 20px;
            box-sizing: border-box;
        }
        .main {
            width: 75%;
            padding: 20px;
            box-sizing: border-box;
            overflow-y: auto;
            color: #000000;
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
        .last-modified {
            font-size: 0.8em;
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
                <li><a onclick="loadContent('home')">Home</a></li>
                <li><a onclick="loadContent('page1')">Page 1</a></li>
                <li><a onclick="loadContent('page2')">Page 2</a></li>
                <li><a onclick="loadContent('page3')">Page 3</a></li>
                <li><a onclick="loadContent('page4')">Page 4</a></li>
            </ul>
            <p class="last-modified">Last modified: <span id="nav-modified"></span></p>
        </div>
        <div class="main">
            <div id="content"></div>
            <p class="last-modified">Last modified: <span id="main-modified"></span></p>
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
            `,
            page1: `
                <h1>Page 1</h1>
                <p>This is the content of Page 1.</p>
            `,
            page2: `
                <h1>Page 2</h1>
                <p>This is the content of Page 2.</p>
            `,
            page3: `
                <h1>Page 3</h1>
                <p>This is the content of Page 3.</p>
            `,
            page4: `
                <h1>Page 4</h1>
                <p>This is the content of Page 4.</p>
            `
        };

        function loadContent(page) {
            document.getElementById('content').innerHTML = pages[page];
            showLastModified('main-modified');
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
