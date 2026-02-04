<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Liar Game - FIXED v2 - - Juego del Impostor</title>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/qrcode@1.5.3/build/qrcode.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/html5-qrcode@2.3.8/html5-qrcode.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .app-container {
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
            font-size: 14px;
        }

        .input, .select {
            width: 100%;
            padding: 12px 16px;
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            font-size: 16px;
            transition: all 0.3s;
        }

        .input:focus, .select:focus {
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
            transition: all 0.3s;
            margin-bottom: 10px;
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

        .button-danger {
            background: #ff6b6b;
            color: white;
        }

        .button-success {
            background: #51cf66;
            color: white;
        }

        .role-card {
            padding: 20px;
            border-radius: 16px;
            text-align: center;
            margin-bottom: 20px;
        }

        .role-honest {
            background: linear-gradient(135deg, #51cf66 0%, #37b24d 100%);
            color: white;
        }

        .role-impostor {
            background: linear-gradient(135deg, #ff6b6b 0%, #fa5252 100%);
            color: white;
        }

        .secret-word {
            font-size: 36px;
            font-weight: bold;
            margin-top: 10px;
        }

        .message-item {
            background: #f8f9fa;
            padding: 12px 16px;
            border-radius: 12px;
            margin-bottom: 10px;
            border-left: 4px solid #667eea;
        }

        .player-name {
            font-weight: 600;
            color: #667eea;
            margin-bottom: 4px;
        }

        .player-word {
            color: #333;
        }

        .vote-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 10px;
            margin-bottom: 20px;
        }

        .vote-button {
            padding: 16px;
            background: #f8f9fa;
            border: 2px solid #e0e0e0;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 600;
        }

        .vote-button:hover {
            border-color: #667eea;
            background: #f0f4ff;
        }

        .vote-button.selected {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-color: #667eea;
        }

        .info-box {
            background: #f8f9fa;
            padding: 16px;
            border-radius: 12px;
            margin-bottom: 20px;
        }

        .info-text {
            color: #666;
            font-size: 14px;
            line-height: 1.6;
        }

        .score-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 12px 16px;
            background: #f8f9fa;
            border-radius: 12px;
            margin-bottom: 8px;
        }

        .score-name {
            font-weight: 600;
            color: #333;
        }

        .score-points {
            font-size: 18px;
            font-weight: bold;
            color: #667eea;
        }

        .winner {
            background: linear-gradient(135deg, #51cf66 0%, #37b24d 100%);
            color: white;
        }

        .winner .score-name,
        .winner .score-points {
            color: white;
        }

        .qr-container {
            text-align: center;
            margin: 20px 0;
        }

        #qr-code {
            display: inline-block;
            padding: 20px;
            background: white;
            border-radius: 12px;
        }

        .waiting-players {
            margin-top: 20px;
        }

        .player-chip {
            display: inline-block;
            background: #e7f5ff;
            color: #1971c2;
            padding: 8px 16px;
            border-radius: 20px;
            margin: 4px;
            font-weight: 600;
            font-size: 14px;
        }

        .turn-indicator {
            background: #fff3bf;
            color: #856404;
            padding: 12px 16px;
            border-radius: 12px;
            text-align: center;
            font-weight: 600;
            margin-bottom: 20px;
        }

        .result-card {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            padding: 20px;
            border-radius: 16px;
            margin-bottom: 20px;
        }

        .result-title {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 10px;
            text-align: center;
        }

        .result-success {
            color: #37b24d;
        }

        .result-fail {
            color: #fa5252;
        }

        .impostors-list {
            text-align: center;
            margin: 10px 0;
            font-size: 14px;
            color: #666;
        }

        .impostor-name {
            color: #fa5252;
            font-weight: bold;
        }

        #scanner-container {
            margin: 20px 0;
        }

        .loading {
            text-align: center;
            padding: 40px;
            color: #667eea;
            font-weight: 600;
        }

        .round-history-item {
            background: #f8f9fa;
            padding: 16px;
            border-radius: 12px;
            margin-bottom: 12px;
            border-left: 4px solid #667eea;
        }

        .round-number {
            font-weight: bold;
            color: #667eea;
            margin-bottom: 8px;
        }

        @media (max-width: 480px) {
            .card {
                padding: 20px;
            }

            .title {
                font-size: 24px;
            }

            .vote-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div id="root"></div>

    <script type="text/babel">
        const { useState, useEffect } = React;

        // Categorías de palabras
        const WordCategories = {
            "Animales": [
                "Perro", "Gato", "León", "Tigre", "Elefante", "Jirafa", "Mono", "Caballo",
                "Vaca", "Cerdo", "Oveja", "Gallina", "Pato", "Pez", "Tiburón", "Ballena",
                "Delfín", "Águila", "Búho", "Pingüino", "Canguro", "Koala", "Panda", "Oso"
            ],
            "Frutas": [
                "Manzana", "Banana", "Naranja", "Fresa", "Uva", "Sandía", "Melón", "Piña",
                "Mango", "Pera", "Durazno", "Cereza", "Kiwi", "Papaya", "Limón", "Granada",
                "Coco", "Arándano", "Frambuesa", "Ciruela", "Higo", "Maracuyá"
            ],
            "Países": [
                "Argentina", "Brasil", "Chile", "México", "España", "Francia", "Italia",
                "Alemania", "Japón", "China", "India", "Canadá", "Australia", "Rusia",
                "Egipto", "Perú", "Colombia", "Venezuela", "Ecuador", "Uruguay", "Paraguay"
            ],
            "Profesiones": [
                "Doctor", "Profesor", "Ingeniero", "Abogado", "Chef", "Policía", "Bombero",
                "Enfermero", "Arquitecto", "Dentista", "Veterinario", "Piloto", "Programador",
                "Diseñador", "Músico", "Actor", "Deportista", "Carpintero", "Plomero", "Electricista"
            ],
            "Deportes": [
                "Fútbol", "Básquet", "Tenis", "Natación", "Voleibol", "Golf", "Béisbol",
                "Rugby", "Hockey", "Boxeo", "Atletismo", "Ciclismo", "Esquí", "Surf",
                "Escalada", "Gimnasia", "Esgrima", "Karate", "Judo", "Taekwondo"
            ],
            "Comidas": [
                "Pizza", "Hamburguesa", "Pasta", "Sushi", "Tacos", "Empanadas", "Paella",
                "Lasaña", "Ensalada", "Sopa", "Asado", "Milanesa", "Ravioles", "Ñoquis",
                "Burrito", "Quesadilla", "Fajitas", "Curry", "Pad Thai", "Ramen"
            ],
            "Objetos del hogar": [
                "Mesa", "Silla", "Sofá", "Cama", "Lámpara", "Espejo", "Reloj", "Televisor",
                "Refrigerador", "Horno", "Microondas", "Lavadora", "Plancha", "Aspiradora",
                "Escritorio", "Estante", "Cortina", "Almohada", "Manta", "Cuadro"
            ],
            "Colores": [
                "Rojo", "Azul", "Verde", "Amarillo", "Naranja", "Morado", "Rosa", "Negro",
                "Blanco", "Gris", "Marrón", "Celeste", "Violeta", "Turquesa", "Dorado",
                "Plateado", "Beige", "Coral", "Lavanda", "Esmeralda"
            ]
        };

        // Utilidades de almacenamiento
        const Storage = {
            saveGame: (game) => {
                localStorage.setItem(`game_${game.gameId}`, JSON.stringify(game));
            },
            getGame: (gameId) => {
                const data = localStorage.getItem(`game_${gameId}`);
                return data ? JSON.parse(data) : null;
            },
            savePlayerInfo: (name, phone) => {
                localStorage.setItem('player_name', name);
                localStorage.setItem('player_phone', phone);
            },
            getPlayerInfo: () => ({
                name: localStorage.getItem('player_name') || '',
                phone: localStorage.getItem('player_phone') || ''
            })
        };

        // Gestor del juego
        const GameManager = {
            createGame: (playerCount, impostorCount, category, hostName, hostPhone) => {
                const gameId = Math.random().toString(36).substr(2, 8).toUpperCase();
                
                const game = {
                    gameId,
                    players: [{ name: hostName, phone: hostPhone, index: 0 }],
                    impostorIndices: [],
                    category,
                    secretWord: '',
                    phase: 'WAITING',
                    currentTurnIndex: 0,
                    currentRound: 0,
                    totalRounds: 12,
                    messages: [],
                    scores: { [hostName]: 0 },
                    votes: {},
                    roundHistory: [],
                    maxPlayers: playerCount,
                    maxImpostors: impostorCount
                };

                Storage.saveGame(game);
                return gameId;
            },

            joinGame: (gameData, playerName, playerPhone) => {
                let game = Storage.getGame(gameData.gameId);
                
                if (!game) {
                    game = {
                        ...gameData,
                        messages: [],
                        votes: {},
                        roundHistory: [],
                        scores: {}
                    };
                }

                const existingPlayer = game.players.find(p => p.phone === playerPhone);
                if (!existingPlayer) {
                    game.players.push({ name: playerName, phone: playerPhone, index: game.players.length });
                    game.scores[playerName] = 0;
                }

                Storage.saveGame(game);
                return game;
            },

            startGame: (gameId) => {
                const game = Storage.getGame(gameId);
                if (!game || game.players.length < 3) return false;

                GameManager.startNewRound(gameId);
                return true;
            },

            startNewRound: (gameId) => {
                const game = Storage.getGame(gameId);
                if (!game) return false;

                game.messages = [];
                game.votes = {};
                game.currentTurnIndex = 0;
                game.phase = 'PLAYING';

                const words = WordCategories[game.category];
                game.secretWord = words[Math.floor(Math.random() * words.length)];

                const playerCount = game.players.length;
                const impostorCount = game.maxImpostors || (playerCount <= 4 ? 1 : playerCount <= 7 ? 2 : 3);

                game.impostorIndices = [];
                while (game.impostorIndices.length < impostorCount) {
                    const randomIdx = Math.floor(Math.random() * playerCount);
                    if (!game.impostorIndices.includes(randomIdx)) {
                        game.impostorIndices.push(randomIdx);
                    }
                }

                Storage.saveGame(game);
                return true;
            },

            sendWord: (gameId, playerName, word) => {
                const game = Storage.getGame(gameId);
                if (!game) return false;

                game.messages.push({ player: playerName, word });

                if (game.currentTurnIndex < game.players.length - 1) {
                    game.currentTurnIndex++;
                } else {
                    game.phase = 'VOTING';
                }

                Storage.saveGame(game);
                return true;
            },

            vote: (gameId, playerName, votedPlayer) => {
                const game = Storage.getGame(gameId);
                if (!game) return false;

                game.votes[playerName] = votedPlayer;

                if (Object.keys(game.votes).length === game.players.length) {
                    GameManager.calculateResults(gameId);
                }

                Storage.saveGame(game);
                return true;
            },

            calculateResults: (gameId) => {
                const game = Storage.getGame(gameId);
                if (!game) return false;

                const voteCount = {};
                Object.values(game.votes).forEach(vote => {
                    voteCount[vote] = (voteCount[vote] || 0) + 1;
                });

                const votedOut = Object.keys(voteCount).reduce((a, b) => voteCount[a] > voteCount[b] ? a : b);
                const votedOutIndex = game.players.findIndex(p => p.name === votedOut);
                const caught = game.impostorIndices.includes(votedOutIndex);

                game.lastResult = {
                    votedOut,
                    caught,
                    impostors: game.players
                        .filter((_, idx) => game.impostorIndices.includes(idx))
                        .map(p => p.name)
                };

                game.roundHistory.push({
                    roundNumber: game.currentRound,
                    votedOut,
                    caught,
                    impostors: game.lastResult.impostors
                });

                if (caught) {
                    game.players.forEach(p => {
                        if (p.name !== votedOut) {
                            game.scores[p.name] = (game.scores[p.name] || 0) + 1;
                        }
                    });
                } else {
                    game.players.forEach(p => {
                        if (game.impostorIndices.includes(game.players.indexOf(p))) {
                            game.scores[p.name] = (game.scores[p.name] || 0) + 2;
                        }
                    });
                }

                game.currentRound++;
                game.phase = 'ROUND_RESULTS';

                Storage.saveGame(game);
                return true;
            },

            continueToNextRound: (gameId) => {
                const game = Storage.getGame(gameId);
                if (!game) return false;

                if (game.currentRound >= game.totalRounds) {
                    game.phase = 'FINAL_RESULTS';
                } else {
                    GameManager.startNewRound(gameId);
                }

                Storage.saveGame(game);
                return true;
            }
        };

        // Componente Principal
        function LiarGame() {
            const [screen, setScreen] = useState('home');
            const [gameId, setGameId] = useState('');
            const [playerName, setPlayerName] = useState('');
            const [playerPhone, setPlayerPhone] = useState('');
            const [game, setGame] = useState(null);

            useEffect(() => {
                const savedInfo = Storage.getPlayerInfo();
                setPlayerName(savedInfo.name);
                setPlayerPhone(savedInfo.phone);
            }, []);

            useEffect(() => {
                if (gameId) {
                    const interval = setInterval(() => {
                        const updatedGame = Storage.getGame(gameId);
                        setGame(updatedGame);
                    }, 1000);
                    return () => clearInterval(interval);
                }
            }, [gameId]);

            const renderScreen = () => {
                switch (screen) {
                    case 'home':
                        return <HomeScreen 
                            onCreateGame={() => setScreen('create')}
                            onJoinGame={() => setScreen('join')}
                            playerName={playerName}
                            setPlayerName={setPlayerName}
                            playerPhone={playerPhone}
                            setPlayerPhone={setPlayerPhone}
                        />;
                    case 'create':
                        return <CreateGameScreen 
                            playerName={playerName}
                            playerPhone={playerPhone}
                            onGameCreated={(id) => {
                                setGameId(id);
                                setGame(Storage.getGame(id));
                                setScreen('waiting');
                            }}
                            onBack={() => setScreen('home')}
                        />;
                    case 'join':
                        return <JoinGameScreen 
                            playerName={playerName}
                            playerPhone={playerPhone}
                            onGameJoined={(id) => {
                                setGameId(id);
                                const joinedGame = Storage.getGame(id);
                                setGame(joinedGame);
                                // ARREGLADO: ahora usamos joinedGame en lugar de game
                                if (joinedGame?.phase === 'WAITING') {
                                    setScreen('waiting');
                                } else {
                                    setScreen('game');
                                }
                            }}
                            onBack={() => setScreen('home')}
                        />;
                    case 'waiting':
                        return <WaitingScreen 
                            game={game}
                            playerName={playerName}
                            onStartGame={() => {
                                GameManager.startGame(gameId);
                                setGame(Storage.getGame(gameId));
                                setScreen('game');
                            }}
                        />;
                    case 'game':
                        if (!game) return <div className="loading">Cargando...</div>;
                        
                        if (game.phase === 'VOTING') {
                            return <VoteScreen 
                                game={game}
                                playerName={playerName}
                                onVoteSubmit={() => {
                                    setGame(Storage.getGame(gameId));
                                }}
                            />;
                        } else if (game.phase === 'ROUND_RESULTS') {
                            return <RoundResultsScreen 
                                game={game}
                                onContinue={() => {
                                    GameManager.continueToNextRound(gameId);
                                    setGame(Storage.getGame(gameId));
                                }}
                            />;
                        } else if (game.phase === 'FINAL_RESULTS') {
                            return <FinalResultsScreen 
                                game={game}
                                onNewGame={() => {
                                    setScreen('home');
                                    setGameId('');
                                    setGame(null);
                                }}
                            />;
                        } else {
                            return <GameScreen 
                                game={game}
                                playerName={playerName}
                                onWordSent={() => setGame(Storage.getGame(gameId))}
                            />;
                        }
                    default:
                        return <div>Error</div>;
                }
            };

            return (
                <div className="app-container">
                    {renderScreen()}
                </div>
            );
        }

        // Pantalla de inicio
        function HomeScreen({ onCreateGame, onJoinGame, playerName, setPlayerName, playerPhone, setPlayerPhone }) {
            const handleSaveInfo = () => {
                if (playerName && playerPhone) {
                    Storage.savePlayerInfo(playerName, playerPhone);
                }
            };

            return (
                <div className="card">
                    <div className="header">
                        <div className="title">🎭 Liar Game</div>
                        <div className="subtitle">Juego del Impostor</div>
                    </div>

                    <div className="input-group">
                        <label className="label">Tu Nombre</label>
                        <input 
                            type="text" 
                            className="input"
                            value={playerName}
                            onChange={(e) => setPlayerName(e.target.value)}
                            placeholder="Ingresa tu nombre"
                            onBlur={handleSaveInfo}
                        />
                    </div>

                    <div className="input-group">
                        <label className="label">Tu Teléfono</label>
                        <input 
                            type="tel" 
                            className="input"
                            value={playerPhone}
                            onChange={(e) => setPlayerPhone(e.target.value)}
                            placeholder="+54 9 11 1234-5678"
                            onBlur={handleSaveInfo}
                        />
                    </div>

                    <button 
                        className="button button-primary"
                        onClick={onCreateGame}
                        disabled={!playerName || !playerPhone}
                    >
                        Crear Partida Nueva
                    </button>

                    <button 
                        className="button button-secondary"
                        onClick={onJoinGame}
                        disabled={!playerName || !playerPhone}
                    >
                        Unirse a Partida
                    </button>

                    <div className="info-box" style={{marginTop: '20px'}}>
                        <div className="info-text">
                            <strong>¿Cómo jugar?</strong><br/>
                            • El anfitrión crea una partida<br/>
                            • Los demás escanean el QR para unirse<br/>
                            • Algunos jugadores serán impostores<br/>
                            • Deben decir palabras relacionadas sin ser descubiertos<br/>
                            • Al final de cada ronda, votan al sospechoso
                        </div>
                    </div>
                </div>
            );
        }

        // Pantalla de crear partida
        function CreateGameScreen({ playerName, playerPhone, onGameCreated, onBack }) {
            const [playerCount, setPlayerCount] = useState(4);
            const [impostorCount, setImpostorCount] = useState(1);
            const [category, setCategory] = useState('Animales');

            const handleCreate = () => {
                if (playerCount < 3 || playerCount > 10) {
                    alert('Debe haber entre 3 y 10 jugadores');
                    return;
                }
                if (impostorCount < 1 || impostorCount >= playerCount) {
                    alert('Número de impostores inválido');
                    return;
                }

                try {
                    const gameId = GameManager.createGame(
                        playerCount,
                        impostorCount,
                        category,
                        playerName,
                        playerPhone
                    );
                    onGameCreated(gameId);
                } catch (error) {
                    console.error('Error creando partida:', error);
                    alert('Error al crear la partida');
                }
            };

            return (
                <div className="card">
                    <div className="header">
                        <div className="title">Crear Partida</div>
                    </div>

                    <div className="input-group">
                        <label className="label">Número de Jugadores (3-10)</label>
                        <input 
                            type="number" 
                            className="input"
                            min="3"
                            max="10"
                            value={playerCount}
                            onChange={(e) => setPlayerCount(parseInt(e.target.value))}
                        />
                    </div>

                    <div className="input-group">
                        <label className="label">Número de Impostores</label>
                        <input 
                            type="number" 
                            className="input"
                            min="1"
                            max={playerCount - 1}
                            value={impostorCount}
                            onChange={(e) => setImpostorCount(parseInt(e.target.value))}
                        />
                    </div>

                    <div className="input-group">
                        <label className="label">Categoría</label>
                        <select 
                            className="select"
                            value={category}
                            onChange={(e) => setCategory(e.target.value)}
                        >
                            {Object.keys(WordCategories).map(cat => (
                                <option key={cat} value={cat}>{cat}</option>
                            ))}
                        </select>
                    </div>

                    <button className="button button-primary" onClick={handleCreate}>
                        Crear Partida
                    </button>

                    <button className="button button-secondary" onClick={onBack}>
                        Volver
                    </button>
                </div>
            );
        }

        // Pantalla de unirse a partida
        function JoinGameScreen({ playerName, playerPhone, onGameJoined, onBack }) {
            const [gameIdInput, setGameIdInput] = useState('');
            const [scanning, setScanning] = useState(false);

            const handleJoin = () => {
                const game = Storage.getGame(gameIdInput);
                if (!game) {
                    alert('Partida no encontrada');
                    return;
                }

                const gameData = {
                    gameId: game.gameId,
                    players: game.players,
                    impostorIndices: game.impostorIndices,
                    category: game.category,
                    secretWord: game.secretWord,
                    totalRounds: game.totalRounds
                };

                GameManager.joinGame(gameData, playerName, playerPhone);
                onGameJoined(gameIdInput);
            };

            const handleScanQR = () => {
                setScanning(true);
                const html5QrCode = new Html5Qrcode('scanner-container');
                
                html5QrCode.start(
                    { facingMode: 'environment' },
                    { fps: 10, qrbox: { width: 250, height: 250 } },
                    (decodedText) => {
                        try {
                            const gameData = JSON.parse(decodedText);
                            html5QrCode.stop();
                            setScanning(false);
                            GameManager.joinGame(gameData, playerName, playerPhone);
                            onGameJoined(gameData.gameId);
                        } catch (e) {
                            alert('QR inválido');
                        }
                    }
                ).catch(err => {
                    console.error(err);
                    setScanning(false);
                });
            };

            return (
                <div className="card">
                    <div className="header">
                        <div className="title">Unirse a Partida</div>
                    </div>

                    {!scanning ? (
                        <>
                            <div className="input-group">
                                <label className="label">Código de Partida</label>
                                <input 
                                    type="text" 
                                    className="input"
                                    value={gameIdInput}
                                    onChange={(e) => setGameIdInput(e.target.value.toUpperCase())}
                                    placeholder="Ej: ABC12345"
                                />
                            </div>

                            <button className="button button-primary" onClick={handleJoin}>
                                Unirse
                            </button>

                            <button className="button button-secondary" onClick={handleScanQR}>
                                📷 Escanear QR
                            </button>

                            <button className="button button-secondary" onClick={onBack}>
                                Volver
                            </button>
                        </>
                    ) : (
                        <>
                            <div id="scanner-container"></div>
                            <button 
                                className="button button-secondary"
                                onClick={() => {
                                    setScanning(false);
                                }}
                            >
                                Cancelar
                            </button>
                        </>
                    )}
                </div>
            );
        }

        // Pantalla de espera
        function WaitingScreen({ game, playerName, onStartGame }) {
            const [qrGenerated, setQrGenerated] = useState(false);

            useEffect(() => {
                if (game && !qrGenerated) {
                    const gameData = {
                        gameId: game.gameId,
                        players: game.players,
                        impostorIndices: game.impostorIndices,
                        category: game.category,
                        secretWord: game.secretWord,
                        totalRounds: game.totalRounds
                    };

                    const qrContainer = document.getElementById('qr-code');
                    if (qrContainer) {
                        qrContainer.innerHTML = '';
                        QRCode.toCanvas(
                            JSON.stringify(gameData),
                            { width: 200, margin: 2 },
                            (err, canvas) => {
                                if (!err) {
                                    qrContainer.appendChild(canvas);
                                    setQrGenerated(true);
                                }
                            }
                        );
                    }
                }
            }, [game, qrGenerated]);

            if (!game) return <div className="loading">Cargando...</div>;

            const isHost = game.players[0].name === playerName;

            return (
                <div className="card">
                    <div className="header">
                        <div className="title">Esperando Jugadores</div>
                    </div>

                    <div className="info-box">
                        <div className="info-text">
                            Código de partida: <strong>{game.gameId}</strong>
                        </div>
                    </div>

                    <div className="qr-container">
                        <p style={{color: '#666', marginBottom: '10px'}}>Escanea para unirte:</p>
                        <div id="qr-code"></div>
                    </div>

                    <div className="waiting-players">
                        <label className="label">Jugadores ({game.players.length}/{game.maxPlayers}):</label>
                        <div style={{marginBottom: '20px'}}>
                            {game.players.map(player => (
                                <div key={player.name} className="player-chip">
                                    {player.name}
                                </div>
                            ))}
                        </div>
                    </div>

                    {isHost && game.players.length >= 3 && (
                        <button className="button button-primary" onClick={onStartGame}>
                            Iniciar Partida ({game.players.length} jugadores)
                        </button>
                    )}

                    {!isHost && (
                        <div className="info-box">
                            <div className="info-text">
                                Esperando a que el anfitrión inicie la partida...
                            </div>
                        </div>
                    )}
                </div>
            );
        }

        // Pantalla de juego
        function GameScreen({ game, playerName, onWordSent }) {
            const [word, setWord] = useState('');

            const currentPlayer = game.players[game.currentTurnIndex].name;
            const isMyTurn = currentPlayer === playerName;
            const isImpostor = game.impostorIndices.includes(
                game.players.findIndex(p => p.name === playerName)
            );

            const handleSendWord = () => {
                if (word.trim()) {
                    GameManager.sendWord(game.gameId, playerName, word);
                    setWord('');
                    onWordSent();
                }
            };

            return (
                <div className="card">
                    <div className="header">
                        <div className="title">Ronda {game.currentRound + 1}</div>
                    </div>

                    <div className="role-card" style={{
                        background: isImpostor ? 
                            'linear-gradient(135deg, #ff6b6b 0%, #fa5252 100%)' : 
                            'linear-gradient(135deg, #51cf66 0%, #37b24d 100%)'
                    }}>
                        <div style={{fontSize: '14px', fontWeight: '600', marginBottom: '10px'}}>
                            Tu rol:
                        </div>
                        <div style={{fontSize: '20px', fontWeight: 'bold'}}>
                            {isImpostor ? '🕵️ Impostor' : '👤 Jugador Normal'}
                        </div>
                        {isImpostor && (
                            <div style={{fontSize: '12px', marginTop: '10px', opacity: 0.9}}>
                                Descubre la palabra sin ser atrapado
                            </div>
                        )}
                        {!isImpostor && (
                            <>
                                <div className="secret-word">{game.secretWord}</div>
                            </>
                        )}
                    </div>

                    <div className="turn-indicator">
                        Turno de: <strong>{currentPlayer}</strong>
                    </div>

                    {isMyTurn && (
                        <div className="input-group">
                            <label className="label">Di una palabra relacionada</label>
                            <input 
                                type="text" 
                                className="input"
                                value={word}
                                onChange={(e) => setWord(e.target.value)}
                                onKeyPress={(e) => e.key === 'Enter' && handleSendWord()}
                                placeholder="Tu palabra..."
                            />
                            <button 
                                className="button button-primary"
                                style={{marginTop: '10px'}}
                                onClick={handleSendWord}
                            >
                                Enviar Palabra
                            </button>
                        </div>
                    )}

                    <div style={{marginTop: '20px'}}>
                        <label className="label">Palabras Dichas:</label>
                        {game.messages.length === 0 ? (
                            <div className="info-box">
                                <div className="info-text">Aún no hay palabras...</div>
                            </div>
                        ) : (
                            game.messages.map((msg, idx) => (
                                <div key={idx} className="message-item">
                                    <div className="player-name">{msg.player}</div>
                                    <div className="player-word">{msg.word}</div>
                                </div>
                            ))
                        )}
                    </div>
                </div>
            );
        }

        // Pantalla de votación
        function VoteScreen({ game, playerName, onVoteSubmit }) {
            const [selectedPlayer, setSelectedPlayer] = useState('');

            if (!game) return <div className="loading">Cargando...</div>;

            const hasVoted = game.votes[playerName];
            const votablePlayer = game.players.filter(p => p.name !== playerName);

            const handleVote = () => {
                if (selectedPlayer) {
                    GameManager.vote(game.gameId, playerName, selectedPlayer);
                    onVoteSubmit();
                }
            };

            return (
                <div className="card">
                    <div className="header">
                        <div className="title">⚖️ Votación</div>
                        <div className="subtitle">¿Quién es el impostor?</div>
                    </div>

                    {hasVoted ? (
                        <div className="info-box">
                            <div className="info-text">
                                Has votado por: <strong>{game.votes[playerName]}</strong><br/>
                                Esperando a que todos voten...
                            </div>
                        </div>
                    ) : (
                        <>
                            <div className="vote-grid">
                                {votablePlayer.map(player => (
                                    <button
                                        key={player.name}
                                        className={`vote-button ${selectedPlayer === player.name ? 'selected' : ''}`}
                                        onClick={() => setSelectedPlayer(player.name)}
                                    >
                                        {player.name}
                                    </button>
                                ))}
                            </div>

                            <button 
                                className="button button-danger"
                                onClick={handleVote}
                                disabled={!selectedPlayer}
                            >
                                Confirmar Voto
                            </button>
                        </>
                    )}

                    <div className="info-box" style={{marginTop: '20px'}}>
                        <div className="info-text">
                            Votos recibidos: {Object.keys(game.votes).length} / {game.players.length}
                        </div>
                    </div>
                </div>
            );
        }

        // Pantalla de resultados de ronda
        function RoundResultsScreen({ game, onContinue }) {
            if (!game || !game.lastResult) return <div className="loading">Cargando...</div>;

            const { votedOut, caught, impostors } = game.lastResult;

            return (
                <div className="card">
                    <div className="header">
                        <div className="title">Resultados Ronda {game.currentRound}</div>
                    </div>

                    <div className="result-card">
                        <div className={`result-title ${caught ? 'result-success' : 'result-fail'}`}>
                            {caught ? '✅ ¡Impostor Atrapado!' : '❌ Impostor Escapó'}
                        </div>
                        <div style={{textAlign: 'center', fontSize: '18px', marginTop: '10px'}}>
                            Votaron a: <strong>{votedOut}</strong>
                        </div>
                        <div className="impostors-list">
                            Los impostores eran: {impostors.map((imp, idx) => (
                                <span key={idx} className="impostor-name">
                                    {imp}{idx < impostors.length - 1 && ', '}
                                </span>
                            ))}
                        </div>
                    </div>

                    <div style={{marginTop: '20px'}}>
                        <label className="label">Puntajes:</label>
                        {Object.entries(game.scores)
                            .sort(([, a], [, b]) => b - a)
                            .map(([name, score]) => (
                                <div key={name} className="score-item">
                                    <span className="score-name">{name}</span>
                                    <span className="score-points">{score}</span>
                                </div>
                            ))
                        }
                    </div>

                    <button 
                        className="button button-primary"
                        style={{marginTop: '20px'}}
                        onClick={onContinue}
                    >
                        {game.currentRound < game.totalRounds ? 'Siguiente Ronda' : 'Ver Resultados Finales'}
                    </button>
                </div>
            );
        }

        // Pantalla de resultados finales
        function FinalResultsScreen({ game, onNewGame }) {
            if (!game) return <div className="loading">Cargando...</div>;

            const sortedScores = Object.entries(game.scores).sort(([, a], [, b]) => b - a);
            const winner = sortedScores[0];

            return (
                <div className="card">
                    <div className="header">
                        <div className="title">🏆 Resultados Finales</div>
                    </div>

                    <div className="result-card">
                        <div className="result-title result-success">
                            Ganador: {winner[0]}
                        </div>
                        <div style={{textAlign: 'center', fontSize: '36px', fontWeight: 'bold', color: '#667eea'}}>
                            {winner[1]} puntos
                        </div>
                    </div>

                    <div style={{marginTop: '20px'}}>
                        <label className="label">Clasificación Final:</label>
                        {sortedScores.map(([name, score], idx) => (
                            <div key={name} className={`score-item ${idx === 0 ? 'winner' : ''}`}>
                                <span className="score-name">
                                    {idx + 1}. {name}
                                </span>
                                <span className="score-points">{score}</span>
                            </div>
                        ))}
                    </div>

                    <div style={{marginTop: '20px'}}>
                        <label className="label">Historial de Rondas:</label>
                        {game.roundHistory.map((round, idx) => (
                            <div key={idx} className="round-history-item">
                                <div className="round-number">Ronda {round.roundNumber + 1}</div>
                                <div style={{fontSize: '14px', color: '#666'}}>
                                    Votado: {round.votedOut}<br/>
                                    {round.caught ? '✅ Impostor atrapado' : '❌ Impostor escapó'}<br/>
                                    Impostores: {round.impostors.join(', ')}
                                </div>
                            </div>
                        ))}
                    </div>

                    <button 
                        className="button button-primary"
                        style={{marginTop: '20px'}}
                        onClick={onNewGame}
                    >
                        Nueva Partida
                    </button>
                </div>
            );
        }

        // Renderizar la aplicación
        ReactDOM.render(<LiarGame />, document.getElementById('root'));
    </script>
</body>
</html>
