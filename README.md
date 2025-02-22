<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YourMany</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Welcome to YourMany</h1>
        <p>Play exciting games and win amazing prizes!</p>
    </header>

    <section id="games">
        <h2>Our Games</h2>
        <div class="game">
            <h3>Lucky Lottery</h3>
            <p>Join our daily lottery and win up to BDT 10,000!</p>
            <button>Play Now</button>
        </div>
        <div class="game">
            <h3>Spin the Wheel</h3>
            <p>Spin the wheel and win instant prizes!</p>
            <button>Play Now</button>
        </div>
    </section>

    <footer>
        <p>&copy; 2023 YourMany. All rights reserved.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
    color: #333;
}

header {
    background-color: #4CAF50;
    color: white;
    padding: 20px;
    text-align: center;
}

#games {
    display: flex;
    justify-content: space-around;
    padding: 20px;
}

.game {
    background-color: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    text-align: center;
    width: 30%;
}

button {
    background-color: #4CAF50;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #45a049;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px;
    position: fixed;
    width: 100%;
    bottom: 0;
}
