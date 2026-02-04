<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Liar Game - Juego del Impostor</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
        }
        .card {
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            margin-bottom: 20px;
        }
        .header {
            text-align: center;
            margin-bottom: 30px;
        }
        .title {
            font-size: 32px;
            font-weight: bold;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
        }
        .subtitle {
            color: #666;
            font-size: 14px;
        }
        .input-group {
            margin-bottom: 20px;
        }
        .label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #333;
        }
        input, select {
            width: 100%;
            padding: 12px 16px;
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            font-size: 16px;
        }
        input:focus, select:focus {
            outline: none;
            border-color: #667eea;
        }
        .button {
            width: 100%;
            padding: 14px;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            margin-bottom: 10px;
            transition: all 0.3s;
        }
        .button-primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }
        .button-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(102, 126, 234, 0.4);
        }
        .button-secondary {
            background: #f0f0f0;
            color: #333;
        }
        .button-secondary:hover {
            background: #e0e0e0;
        }
        .info-box {
            background: #f8f9fa;
            padding: 16px;
            border-radius: 12px;
            margin-bottom: 20px;
            color: #666;
            font-size: 14px;
            line-height: 1.6;
        }
        .hidden {
            display: none;
        }
        .success {
            background: #51cf66;
            color: white;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 20px;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Pantalla de Inicio -->
        <div id="homeScreen" class="card">
            <div class="header">
                <div class="title">🎭 Liar Game</div>
                <div class="subtitle">Juego del Impostor</div>
            </div>

            <div class="input-group">
                <label class="label">Tu Nombre</label>
                <input type="text" id="playerName" placeholder="Ingresa tu nombre">
            </div>

            <div class="input-group">
                <label class="label">Tu Teléfono</label>
                <input type="tel" id="playerPhone" placeholder="+54 9 11 1234-5678">
            </div>

            <button class="button button-primary" onclick="goToCreateGame()">
                Crear Partida Nueva
            </button>

            <button class="button button-secondary" onclick="goToJoinGame()">
                Unirse a Partida
            </button>

            <div class="info-box">
                <strong>¿Cómo jugar?</strong><br/>
                • El anfitrión crea una partida<br/>
                • Los demás escanean el QR para unirse<br/>
                • Algunos jugadores serán impostores<br/>
                • Deben decir palabras relacionadas sin ser descubiertos<br/>
                • Al final de cada ronda, votan al sospechoso
            </div>
        </div>

        <!-- Pantalla de Crear Partida -->
        <div id="createScreen" class="card hidden">
            <div class="header">
                <div class="title">Crear Partida</div>
            </div>

            <div class="input-group">
                <label class="label">Número de Jugadores (3-10)</label>
                <input type="number" id="playerCount" min="3" max="10" value="4">
            </div>

            <div class="input-group">
                <label class="label">Número de Impostores</label>
                <input type="number" id="impostorCount" min="1" max="9" value="1">
            </div>

            <div class="input-group">
                <label class="label">Categoría</label>
                <select id="category">
                    <option>Animales</option>
                    <option>Frutas</option>
                    <option>Países</option>
                    <option>Profesiones</option>
                    <option>Deportes</option>
                    <option>Comidas</option>
                </select>
            </div>

            <button class="button button-primary" onclick="createGame()">
                Crear Partida
            </button>

            <button class="button button-secondary" onclick="goHome()">
                Volver
            </button>
        </div>

        <!-- Pantalla de Espera -->
        <div id="waitingScreen" class="card hidden">
            <div class="header">
                <div class="title">Esperando Jugadores</div>
            </div>

            <div class="success" id="gameMessage"></div>

            <div class="info-box">
                Código de partida: <strong id="gameCode"></strong>
            </div>

            <div style="margin-bottom: 20px;">
                <label class="label">Jugadores conectados:</label>
                <div id="playersList"></div>
            </div>

            <button class="button button-primary" id="startBtn" onclick="startGame()" style="display:none;">
                Iniciar Partida
            </button>

            <div class="info-box" id="waitMessage">
                Esperando a que el anfitrión inicie...
            </div>
        </div>

        <!-- Pantalla de Juego -->
        <div id="gameScreen" class="card hidden">
            <div class="header">
                <div class="title" id="roundTitle">Ronda 1</div>
            </div>

            <div style="padding: 20px; border-radius: 16px; text-align: center; margin-bottom: 20px;" id="roleCard">
            </div>

            <div style="background: #fff3bf; color: #856404; padding: 12px; border-radius: 12px; text-align: center; font-weight: 600; margin-bottom: 20px;">
                Turno de: <strong id="currentPlayer"></strong>
            </div>

            <div class="input-group" id="wordInput" style="display:none;">
                <label class="label">Di una palabra relacionada</label>
                <input type="text" id="wordField" placeholder="Tu palabra..." onkeypress="if(event.key==='Enter') sendWord()">
                <button class="button button-primary" onclick="sendWord()" style="margin-top: 10px;">
                    Enviar Palabra
                </button>
            </div>

            <div style="margin-top: 20px;">
                <label class="label">Palabras Dichas:</label>
                <div id="messagesList"></div>
            </div>
        </div>

        <!-- Pantalla de Votación -->
        <div id="voteScreen" class="card hidden">
            <div class="header">
                <div class="title">⚖️ Votación</div>
                <div class="subtitle">¿Quién es el impostor?</div>
            </div>

            <div id="voteButtons" style="display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 10px; margin-bottom: 20px;"></div>

            <button class="button button-primary" id="confirmVoteBtn" onclick="submitVote()" style="display:none;">
                Confirmar Voto
            </button>

            <div class="info-box" id="voteStatus"></div>
        </div>

        <!-- Pantalla de Resultados -->
        <div id="resultsScreen" class="card hidden">
            <div class="header">
                <div class="title">Resultados</div>
            </div>

            <div id="resultsContent"></div>

            <button class="button button-primary" onclick="goHome()">
                Nueva Partida
            </button>
        </div>
    </div>

    <script>
        const WordCategories = {
            "Animales": ["Perro", "Gato", "León", "Tigre", "Elefante", "Jirafa", "Mono", "Caballo", "Vaca", "Cerdo"],
            "Frutas": ["Manzana", "Banana", "Naranja", "Fresa", "Uva", "Sandía", "Melón", "Piña", "Mango", "Pera"],
            "Países": ["Argentina", "Brasil", "Chile", "México", "España", "Francia", "Italia", "Alemania", "Japón", "China"],
            "Profesiones": ["Doctor", "Profesor", "Ingeniero", "Abogado", "Chef", "Policía", "Bombero", "Enfermero", "Arquitecto", "Dentista"],
            "Deportes": ["Fútbol", "Básquet", "Tenis", "Natación", "Voleibol", "Golf", "Béisbol", "Rugby", "Hockey", "Boxeo"],
            "Comidas": ["Pizza", "Hamburguesa", "Pasta", "Sushi", "Tacos", "Empanadas", "Paella", "Lasaña", "Ensalada", "Sopa"]
        };

        let gameState = {
            gameId: '',
            phase: 'home',
            playerName: '',
            playerPhone: '',
            players: [],
            isHost: false,
            secretWord: '',
            impostorIndices: [],
            messages: [],
            votes: {},
            currentTurn: 0,
            scores: {},
            category: 'Animales'
        };

        function showScreen(screenName) {
            document.querySelectorAll('.card').forEach(card => card.classList.add('hidden'));
            document.getElementById(screenName).classList.remove('hidden');
        }

        function goHome() {
            gameState.phase = 'home';
            showScreen('homeScreen');
        }

        function goToCreateGame() {
            const name = document.getElementById('playerName').value.trim();
            const phone = document.getElementById('playerPhone').value.trim();

            if (!name || !phone) {
                alert('Por favor ingresa nombre y teléfono');
                return;
            }

            gameState.playerName = name;
            gameState.playerPhone = phone;
            gameState.phase = 'create';
            showScreen('createScreen');
        }

        function goToJoinGame() {
            const name = document.getElementById('playerName').value.trim();
            const phone = document.getElementById('playerPhone').value.trim();

            if (!name || !phone) {
                alert('Por favor ingresa nombre y teléfono');
                return;
            }

            gameState.playerName = name;
            gameState.playerPhone = phone;
            alert('Funcionalidad de unirse en desarrollo. Por ahora solo puedes crear partidas.');
        }

        function createGame() {
            const playerCount = parseInt(document.getElementById('playerCount').value);
            const impostorCount = parseInt(document.getElementById('impostorCount').value);
            const category = document.getElementById('category').value;

            if (playerCount < 3 || playerCount > 10) {
                alert('Debe haber entre 3 y 10 jugadores');
                return;
            }

            if (impostorCount < 1 || impostorCount >= playerCount) {
                alert('Número de impostores inválido');
                return;
            }

            gameState.gameId = Math.random().toString(36).substr(2, 8).toUpperCase();
            gameState.players = [{ name: gameState.playerName, phone: gameState.playerPhone }];
            gameState.isHost = true;
            gameState.category = category;
            gameState.phase = 'waiting';
            gameState.scores[gameState.playerName] = 0;

            updateWaitingScreen();
            showScreen('waitingScreen');
        }

        function updateWaitingScreen() {
            document.getElementById('gameCode').textContent = gameState.gameId;
            document.getElementById('gameMessage').textContent = `Código: ${gameState.gameId}`;
            
            const playersList = gameState.players.map(p => `<div style="display: inline-block; background: #e7f5ff; color: #1971c2; padding: 8px 16px; border-radius: 20px; margin: 4px; font-weight: 600;">${p.name}</div>`).join('');
            document.getElementById('playersList').innerHTML = playersList;

            if (gameState.isHost && gameState.players.length >= 3) {
                document.getElementById('startBtn').style.display = 'block';
                document.getElementById('waitMessage').style.display = 'none';
            } else {
                document.getElementById('startBtn').style.display = 'none';
                document.getElementById('waitMessage').style.display = 'block';
            }
        }

        function startGame() {
            gameState.phase = 'playing';
            startNewRound();
        }

        function startNewRound() {
            const words = WordCategories[gameState.category];
            gameState.secretWord = words[Math.floor(Math.random() * words.length)];
            gameState.messages = [];
            gameState.votes = {};
            gameState.currentTurn = 0;

            const playerCount = gameState.players.length;
            const impostorCount = gameState.players.length <= 4 ? 1 : gameState.players.length <= 7 ? 2 : 3;

            gameState.impostorIndices = [];
            while (gameState.impostorIndices.length < impostorCount) {
                const idx = Math.floor(Math.random() * playerCount);
                if (!gameState.impostorIndices.includes(idx)) {
                    gameState.impostorIndices.push(idx);
                }
            }

            showGameScreen();
        }

        function showGameScreen() {
            const currentPlayer = gameState.players[gameState.currentTurn];
            const isMyTurn = currentPlayer.name === gameState.playerName;
            const isImpostor = gameState.impostorIndices.includes(gameState.currentTurn);

            document.getElementById('roundTitle').textContent = `Ronda 1`;
            document.getElementById('currentPlayer').textContent = currentPlayer.name;

            const roleCard = document.getElementById('roleCard');
            if (isImpostor) {
                roleCard.style.background = 'linear-gradient(135deg, #ff6b6b 0%, #fa5252 100%)';
                roleCard.innerHTML = '<div style="color: white; font-size: 20px; font-weight: bold;">🕵️ IMPOSTOR</div>';
            } else {
                roleCard.style.background = 'linear-gradient(135deg, #51cf66 0%, #37b24d 100%)';
                roleCard.innerHTML = `<div style="color: white; font-size: 20px; font-weight: bold;">👤 JUGADOR NORMAL</div><div style="color: white; font-size: 36px; margin-top: 10px; font-weight: bold;">${gameState.secretWord}</div>`;
            }

            document.getElementById('wordInput').style.display = isMyTurn ? 'block' : 'none';
            
            updateMessagesList();
            showScreen('gameScreen');
        }

        function updateMessagesList() {
            const messagesList = document.getElementById('messagesList');
            if (gameState.messages.length === 0) {
                messagesList.innerHTML = '<div class="info-box">Aún no hay palabras...</div>';
            } else {
                messagesList.innerHTML = gameState.messages.map((msg, idx) => 
                    `<div style="background: #f8f9fa; padding: 12px 16px; border-radius: 12px; margin-bottom: 10px; border-left: 4px solid #667eea;">
                        <div style="font-weight: 600; color: #667eea;">${msg.player}</div>
                        <div style="color: #333;">${msg.word}</div>
                    </div>`
                ).join('');
            }
        }

        function sendWord() {
            const word = document.getElementById('wordField').value.trim();
            if (!word) {
                alert('Ingresa una palabra');
                return;
            }

            gameState.messages.push({
                player: gameState.playerName,
                word: word
            });

            document.getElementById('wordField').value = '';
            gameState.currentTurn++;

            if (gameState.currentTurn < gameState.players.length) {
                updateMessagesList();
                showGameScreen();
            } else {
                showVoteScreen();
            }
        }

        function showVoteScreen() {
            gameState.phase = 'voting';
            const voteButtons = document.getElementById('voteButtons');
            const otherPlayers = gameState.players.filter(p => p.name !== gameState.playerName);

            voteButtons.innerHTML = otherPlayers.map(player =>
                `<button class="button button-secondary" onclick="selectPlayer('${player.name}')" style="padding: 16px;" id="btn-${player.name}">
                    ${player.name}
                </button>`
            ).join('');

            document.getElementById('voteStatus').innerHTML = `Votos: ${Object.keys(gameState.votes).length}/${gameState.players.length}`;
            document.getElementById('confirmVoteBtn').style.display = 'block';
            showScreen('voteScreen');
        }

        function selectPlayer(name) {
            document.querySelectorAll('[id^="btn-"]').forEach(btn => {
                btn.style.background = '#f0f0f0';
                btn.style.color = '#333';
            });

            const btn = document.getElementById(`btn-${name}`);
            btn.style.background = 'linear-gradient(135deg, #667eea 0%, #764ba2 100%)';
            btn.style.color = 'white';

            gameState.selectedVote = name;
        }

        function submitVote() {
            if (!gameState.selectedVote) {
                alert('Selecciona un jugador');
                return;
            }

            gameState.votes[gameState.playerName] = gameState.selectedVote;

            if (Object.keys(gameState.votes).length === gameState.players.length) {
                showResults();
            } else {
                document.getElementById('voteStatus').innerHTML = `Votos: ${Object.keys(gameState.votes).length}/${gameState.players.length}<br/>Esperando otros votos...`;
                document.getElementById('confirmVoteBtn').style.display = 'none';
            }
        }

        function showResults() {
            const voteCount = {};
            Object.values(gameState.votes).forEach(vote => {
                voteCount[vote] = (voteCount[vote] || 0) + 1;
            });

            const votedOut = Object.keys(voteCount).reduce((a, b) => voteCount[a] > voteCount[b] ? a : b);
            const caught = gameState.impostorIndices.includes(gameState.players.findIndex(p => p.name === votedOut));

            const impostors = gameState.impostorIndices.map(idx => gameState.players[idx].name).join(', ');

            let resultsHTML = `
                <div style="background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%); padding: 20px; border-radius: 16px; margin-bottom: 20px;">
                    <div style="font-size: 24px; font-weight: bold; text-align: center; margin-bottom: 10px; color: ${caught ? '#37b24d' : '#fa5252'};">
                        ${caught ? '✅ ¡Impostor Atrapado!' : '❌ Impostor Escapó'}
                    </div>
                    <div style="text-align: center; font-size: 18px; margin-bottom: 10px;">
                        Votaron a: <strong>${votedOut}</strong>
                    </div>
                    <div style="text-align: center; font-size: 14px; color: #666;">
                        Impostores: <strong>${impostors}</strong>
                    </div>
                </div>
            `;

            document.getElementById('resultsContent').innerHTML = resultsHTML;
            gameState.phase = 'results';
            showScreen('resultsScreen');
        }
    </script>
</body>
</html>
