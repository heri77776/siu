<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página Web Interactiva</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    
    <style>
        /* Reset CSS básico */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Roboto', sans-serif;
            background-color: #e0f7fa; /* Fondo claro */
            display: flex;
            flex-direction: row;
            height: 100vh;
            position: relative;
        }

        .header {
            position: fixed;
            width: 100%;
            background: linear-gradient(135deg, #0077b3, #00aaff);
            color: #fff;
            padding: 15px 20px;
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.4);
            z-index: 1000;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: background 0.3s;
        }

        .header h1 {
            margin: 0;
        }

        .toggle-btn {
            background: #00aaff;
            border: none;
            color: #fff;
            padding: 10px 15px;
            cursor: pointer;
            border-radius: 5px;
            transition: background 0.3s, transform 0.3s;
        }

        .toggle-btn:hover {
            background: #0099cc;
            transform: scale(1.05);
        }

        .container {
            margin-top: 70px;
            display: flex;
            width: 100%;
            transition: margin-left 0.3s ease;
        }

        .sidebar {
            width: 250px;
            background: linear-gradient(to bottom, #006bb3, #005f99);
            color: #fff;
            padding: 20px;
            position: fixed;
            height: 100%;
            overflow-y: auto;
            transform: translateX(-100%);
            transition: transform 0.3s ease;
            box-shadow: 2px 0 20px rgba(0, 0, 0, 0.4);
        }

        .sidebar.active {
            transform: translateX(0);
        }

        .sidebar a {
            color: #fff;
            text-decoration: none;
            display: block;
            padding: 15px;
            border-radius: 5px;
            transition: background 0.3s, transform 0.3s;
            margin-bottom: 10px;
        }

        .sidebar a:hover {
            background: #0099cc;
            transform: translateX(5px); /* Efecto de desplazamiento */
        }

        .content {
            margin-left: 0;
            padding: 20px;
            width: calc(100% - 250px);
            transition: margin-left 0.3s ease;
            overflow-y: auto;
            height: calc(100vh - 70px);
        }

        .category {
            margin-bottom: 30px;
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.2);
            position: relative;
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer; /* Cambia el cursor al pasar sobre la categoría */
        }

        .category:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
        }

        .category h2 {
            margin-bottom: 10px;
            color: #005f99;
        }

        .category p {
            color: #666;
            line-height: 1.6;
        }

        .interactive-figure {
            position: fixed;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: #0077b3; /* Azul oscuro */
            transition: background 0.3s, transform 0.3s;
            pointer-events: none;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
        }

        .robot {
            width: 50px;
            height: auto;
            margin: 10px auto;
            animation: move 1s infinite alternate;
        }

        @keyframes move {
            0% {
                transform: translateY(0);
            }
            100% {
                transform: translateY(-10px);
            }
        }

        @media (max-width: 768px) {
            .sidebar {
                width: 200px;
            }

            .content {
                width: calc(100% - 200px);
            }
        }

        @media (max-width: 480px) {
            .sidebar {
                width: 150px;
            }

            .content {
                width: calc(100% - 150px);
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <button class="toggle-btn" id="toggle-btn">Menu</button>
        <h1>POLI DUDAS</h1>
    </header>

    <div class="container">
        <nav class="sidebar" id="sidebar">
            <a href="http://127.0.0.1:5500/CHATBOT.HTML">Chat Bot</a>
            <a href="https://www.google.com.mx/maps/place/Escuela+Polit%C3%A9cnica+de+Guadalajara./@20.6590462,-103.3276709,17z/data=!3m1!4b1!4m6!3m5!1s0x8428b225975e7b8d:0x10d733ff85e0db84!8m2!3d20.6590462!4d-103.325096!16s%2Fg%2F1tjkg376?entry=ttu&g_ep=EgoyMDI0MTAwOS4wIKXMDSoASAFQAw%3D%3D">Ubicación</a>
            <a href="pagina3.html">Avisos</a>
            <a href="pagina4.html">Número de contacto de la escuela</a>
            <a href="pagina5.html">Correo de los desarrolladores</a>
        </nav>
    
        <main class="content" id="content">
            <div class="category" id="categoria1" data-url="http://127.0.0.1:5500/mision/vision.html">
                <h2>MISION // VISION </h2>
                <svg class="robot" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64">
                    <g fill="#4a90e2">
                        <rect x="20" y="22" width="24" height="30" rx="3"/>
                        <rect x="18" y="18" width="28" height="6" rx="2"/>
                        <circle cx="24" cy="12" r="4" fill="#f39c12"/>
                        <circle cx="40" cy="12" r="4" fill="#f39c12"/>
                        <rect x="20" y="26" width="4" height="4" fill="#2c3e50"/>
                        <rect x="40" y="26" width="4" height="4" fill="#2c3e50"/>
                        <rect x="18" y="52" width="28" height="2"/>
                    </g>
                    <g fill="#fff">
                        <circle cx="24" cy="12" r="2"/>
                        <circle cx="40" cy="12" r="2"/>
                    </g>
                </svg>
                <p> consulta aqui informacion </p>
            </div>
            <div class="category" id="categoria2" data-url="http://127.0.0.1:5500/carreras.html">
                <h2>Carreras</h2>
                <svg class="robot" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64">
                    <g fill="#4a90e2">
                        <rect x="20" y="22" width="24" height="30" rx="3"/>
                        <rect x="18" y="18" width="28" height="6" rx="2"/>
                        <circle cx="24" cy="12" r="4" fill="#f39c12"/>
                        <circle cx="40" cy="12" r="4" fill="#f39c12"/>
                        <rect x="20" y="26" width="4" height="4" fill="#2c3e50"/>
                        <rect x="40" y="26" width="4" height="4" fill="#2c3e50"/>
                        <rect x="18" y="52" width="28" height="2"/>
                    </g>
                    <g fill="#fff">
                        <circle cx="24" cy="12" r="2"/>
                        <circle cx="40" cy="12" r="2"/>
                    </g>
                </svg>
                <p>en esta parte encontraras informacion detallada sobre las carreras que te puedes eleguir en la escuela politecnica de guadalajara .</p>
            </div>
            <div class="category" id="categoria3" data-url="http://127.0.0.1:5500/sociedad.html">
                <h2>Sociedad de alumnos </h2>
                <svg class="robot" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64">
                    <g fill="#4a90e2">
                        <rect x="20" y="22" width="24" height="30" rx="3"/>
                        <rect x="18" y="18" width="28" height="6" rx="2"/>
                        <circle cx="24" cy="12" r="4" fill="#f39c12"/>
                        <circle cx="40" cy="12" r="4" fill="#f39c12"/>
                        <rect x="20" y="26" width="4" height="4" fill="#2c3e50"/>
                        <rect x="40" y="26" width="4" height="4" fill="#2c3e50"/>
                        <rect x="18" y="52" width="28" height="2"/>
                    </g>
                    <g fill="#fff">
                        <circle cx="24" cy="12" r="2"/>
                        <circle cx="40" cy="12" r="2"/>
                    </g>
                </svg>
                <p>Descripción de la categoría 3.</p>
            </div>
            <div class="category" id="categoria4" data-url="http://127.0.0.1:5500/mitrasporte.html">
                <h2>tarjeta mi pasaje verde para estudiantes </h2>
                <svg class="robot" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64">
                    <g fill="#4a90e2">
                        <rect x="20" y="22" width="24" height="30" rx="3"/>
                        <rect x="18" y="18" width="28" height="6" rx="2"/>
                        <circle cx="24" cy="12" r="4" fill="#f39c12"/>
                        <circle cx="40" cy="12" r="4" fill="#f39c12"/>
                        <rect x="20" y="26" width="4" height="4" fill="#2c3e50"/>
                        <rect x="40" y="26" width="4" height="4" fill="#2c3e50"/>
                        <rect x="18" y="52" width="28" height="2"/>
                    </g>
                    <g fill="#fff">
                        <circle cx="24" cy="12" r="2"/>
                        <circle cx="40" cy="12" r="2"/>
                    </g>
                </svg>
                <p>Descripción de la categoría 4.</p>
            </div>
           
        </main>
    </div>

    <div class="interactive-figure" id="interactive-figure"></div>
    <script>
        const toggleBtn = document.getElementById('toggle-btn');
        const sidebar = document.getElementById('sidebar');
        const content = document.getElementById('content');
        const interactiveFigure = document.getElementById('interactive-figure');

        toggleBtn.addEventListener('click', () => {
            sidebar.classList.toggle('active');
            content.style.marginLeft = sidebar.classList.contains('active') ? '250px' : '0';
        });

        // Cambiar la figura interactiva de posición suavemente
        document.addEventListener('mousemove', (e) => {
            interactiveFigure.style.transition = 'transform 0.1s';
            interactiveFigure.style.transform = `translate(${e.clientX - 25}px, ${e.clientY - 25}px)`;
        });

        // Cambiar de color y hacer que rebote
        interactiveFigure.addEventListener('click', () => {
            const randomColor = '#' + Math.floor(Math.random() * 16777215).toString(16);
            interactiveFigure.style.backgroundColor = randomColor;
            interactiveFigure.style.transform += ' scale(1.2)';
            setTimeout(() => {
                interactiveFigure.style.transform = interactiveFigure.style.transform.replace(' scale(1.2)', '');
            }, 200);
        });

        // esto redirijea lasotrsf paguinas
        document.querySelectorAll('.category').forEach(category => {
            category.addEventListener('click', () => {
                const url = category.getAttribute('data-url');
                window.location.href = url;
            });
        });
    </script>
</body>
</html>
 
