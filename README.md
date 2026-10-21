<!DOCTYPE html>
<html lang="sv">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Halloween</title>
    <link rel="preconnect" href="https://googleapis.com">
    <link rel="preconnect" href="https://gstatic.com" crossorigin>
    <link href="https://googleapis.com/css2?family=Creepster&family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: 
                linear-gradient(to bottom, rgba(255, 255, 255, 0.03) 1px, transparent 1px),
                linear-gradient(to right, rgba(255, 255, 255, 0.03) 1px, transparent 1px),
                radial-gradient(circle at center, #2c1654 0%, #0b071a 70%, #000000 100%);
            background-size: 40px 40px, 40px 40px, 100% 100%;
            color: #ffffff;
            font-family: 'Montserrat', sans-serif;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }

        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 150px;
            background: radial-gradient(ellipse at top, rgba(255, 255, 255, 0.08) 0%, transparent 70%);
            pointer-events: none;
        }

        .spider-container {
            position: absolute;
            top: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 10;
        }

        .spider {
            position: absolute;
            top: -40px;
            width: 40px;
            height: 40px;
            background: #111;
            border-radius: 50%;
        }

        .spider::before {
            content: '';
            position: absolute;
            top: -2000px;
            left: 50%;
            width: 1px;
            height: 2000px;
            background: rgba(255, 255, 255, 0.25);
        }

        .spider-body::before, .spider-body::after {
            content: '';
            position: absolute;
            background: #111;
            border-radius: 50%;
        }

        .spider-body::before {
            width: 16px;
            height: 16px;
            top: -10px;
            left: 12px;
        }

        .spider-body::after {
            width: 6px;
            height: 6px;
            top: -4px;
            left: 14px;
            background: #ff5500;
            box-shadow: 6px 0 #ff5500;
        }

        .legs {
            position: absolute;
            width: 100%;
            height: 100%;
        }

        .legs::before, .legs::after {
            content: '';
            position: absolute;
            width: 14px;
            height: 10px;
            border: 2px solid #111;
            border-bottom: none;
            border-radius: 10px 10px 0 0;
        }

        .legs::before {
            left: -8px;
            top: 8px;
            border-right: none;
            box-shadow: -2px 8px 0 #111, -4px 16px 0 #111, -2px 24px 0 #111;
            transform: rotate(-20deg);
        }

        .legs::after {
            right: -8px;
            top: 8px;
            border-left: none;
            box-shadow: 2px 8px 0 #111, 4px 16px 0 #111, 2px 24px 0 #111;
            transform: rotate(20deg);
        }

        .sp1 { left: 5%; animation: dangle1 7s infinite ease-in-out; }
        .sp2 { left: 18%; animation: dangle2 9s infinite ease-in-out 1s; }
        .sp3 { left: 32%; animation: dangle3 8s infinite ease-in-out 0.5s; }
        .sp5 { left: 68%; animation: dangle2 7.5s infinite ease-in-out 1.5s; }
        .sp6 { left: 82%; animation: dangle1 10s infinite ease-in-out 0.2s; }
        .sp7 { left: 93%; animation: dangle3 8.5s infinite ease-in-out 1.2s; }

        @keyframes dangle1 {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(180px); }
        }
        @keyframes dangle2 {
            0%, 100% { transform: translateY(0); }
            45% { transform: translateY(320px); }
            75% { transform: translateY(150px); }
        }
        @keyframes dangle3 {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(240px); }
        }

        .card {
            background: rgba(20, 15, 35, 0.75);
            border: 2px solid #ff5500;
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            max-width: 500px;
            width: 90%;
            box-shadow: 0 0 30px rgba(255, 85, 0, 0.3);
            backdrop-filter: blur(10px);
            z-index: 5;
            position: relative;
        }

        .main-title {
            font-family: 'Creepster', cursive;
            font-size: 4rem;
            color: #ff5500;
            text-shadow: 0 0 10px #ff5500, 0 0 20px #ff2200;
            margin-bottom: 10px;
            letter-spacing: 2px;
            animation: pulse 2s infinite alternate;
        }

        @keyframes pulse {
            0% { text-shadow: 0 0 10px #ff5500, 0 0 20px #ff2200; transform: scale(1); }
            100% { text-shadow: 0 0 15px #ff7700, 0 0 30px #ff4400, 0 0 40px #ff2200; transform: scale(1.03); }
        }

        .pumpkin {
            font-size: 5rem;
            margin: 20px 0;
            display: inline-block;
            animation: sway 3s infinite ease-in-out;
        }

        @keyframes sway {
            0%, 100% { transform: rotate(-5deg); }
            50% { transform: rotate(5deg); }
        }

        .greeting {
            font-size: 1.5rem;
            color: #bb99ff;
            margin-bottom: 15px;
            font-weight: bold;
        }

        .message {
            font-size: 1.1rem;
            line-height: 1.6;
            color: #dddddd;
            margin-bottom: 30px;
        }

        .btn {
            background: linear-gradient(45deg, #ff5500, #ff2200);
            color: white;
            border: none;
            padding: 15px 35px;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(255, 22, 0, 0.4);
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .btn:hover {
            background: linear-gradient(45deg, #ff7700, #ff4400);
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(255, 85, 0, 0.6);
        }

        .btn:active {
            transform: translateY(-1px);
        }
    </style>
</head>
<body>

    <div class="spider-container">
        <div class="spider sp1"><div class="spider-body"></div><div class="legs"></div></div>
        <div class="spider sp2"><div class="spider-body"></div><div class="legs"></div></div>
        <div class="spider sp3"><div class="spider-body"></div><div class="legs"></div></div>
        <div class="spider sp5"><div class="spider-body"></div><div class="legs"></div></div>
        <div class="spider sp6"><div class="spider-body"></div><div class="legs"></div></div>
        <div class="spider sp7"><div class="spider-body"></div><div class="legs"></div></div>
    </div>

    <div class="card">
        <h1 class="main-title">Halloween</h1>
        <div class="pumpkin">🎃</div>
        <p class="greeting">Bus eller godis!</p>
        <p class="message">Vi önskar dig en kuslig och skrämmande glad kväll full av magi, spöken och massor av sötsaker. Må mörkret ge dig mycket nöje!</p>
        <button class="btn" onclick="alert('Bus eller godis! 🍬👻')">Öppna överraskningen</button>
    </div>

</body>
</html>
