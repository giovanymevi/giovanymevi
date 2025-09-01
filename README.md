
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portafolio 3D - Giovanny Mendoza Villamizar</title>
    <link href="https://fonts.googleapis.com/css2?family=Raleway:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Raleway', sans-serif;
            background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
            color: #fff;
            min-height: 100vh;
            overflow-x: hidden;
            perspective: 1000px;
        }

        .container {
            width: 100%;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .portfolio-card {
            width: 85%;
            max-width: 1200px;
            background: rgba(255, 255, 255, 0.08);
            border-radius: 20px;
            overflow: hidden;
            backdrop-filter: blur(10px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            transform-style: preserve-3d;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate3d(0.2, 0.1, 0, 5deg); }
            50% { transform: translateY(-20px) rotate3d(0.2, 0.1, 0, -5deg); }
        }

        .header {
            padding: 40px;
            text-align: center;
            background: rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }

        .name {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 5px;
            transform: translateZ(50px);
            text-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { text-shadow: 0 0 5px #fff, 0 0 10px #fff, 0 0 15px #0073e6, 0 0 20px #0073e6; }
            to { text-shadow: 0 0 10px #fff, 0 0 20px #fff, 0 0 30px #0073e6, 0 0 40px #0073e6; }
        }

        .title {
            font-size: 1.2rem;
            font-weight: 300;
            letter-spacing: 3px;
            margin-bottom: 30px;
            transform: translateZ(30px);
        }

        .content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            padding: 40px;
        }

        .section {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 25px;
            transform-style: preserve-3d;
            transition: transform 0.5s ease, box-shadow 0.5s ease;
        }

        .section:hover {
            transform: translateY(-10px) rotateX(5deg) rotateY(-5deg) translateZ(10px);
            box-shadow: 0 20px 30px rgba(0, 0, 0, 0.4);
        }

        .section-title {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: #4db8ff;
            border-bottom: 2px solid #4db8ff;
            padding-bottom: 10px;
            transform: translateZ(30px);
        }

        .project-list {
            list-style: none;
        }

        .project-item {
            padding: 15px;
            margin-bottom: 15px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            transform: translateZ(20px);
            transition: transform 0.3s ease;
            cursor: pointer;
        }

        .project-item:hover {
            transform: translateZ(30px) scale(1.03);
            background: rgba(77, 184, 255, 0.2);
        }

        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
        }

        .skill {
            padding: 10px 20px;
            background: rgba(77, 184, 255, 0.2);
            border-radius: 20px;
            transform: translateZ(20px);
            transition: all 0.3s ease;
        }

        .skill:hover {
            transform: translateZ(30px) scale(1.1);
            background: rgba(77, 184, 255, 0.4);
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .form-group label {
            font-weight: 600;
            transform: translateZ(20px);
        }

        .form-group input, .form-group textarea {
            padding: 12px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.1);
            color: white;
            transform: translateZ(15px);
            transition: all 0.3s ease;
        }

        .form-group input:focus, .form-group textarea:focus {
            outline: none;
            background: rgba(255, 255, 255, 0.15);
            transform: translateZ(25px);
        }

        .btn {
            padding: 12px 30px;
            background: linear-gradient(45deg, #4db8ff, #0073e6);
            border: none;
            border-radius: 30px;
            color: white;
            font-weight: 600;
            letter-spacing: 1px;
            cursor: pointer;
            transform: translateZ(25px);
            transition: all 0.3s ease;
            align-self: flex-start;
        }

        .btn:hover {
            transform: translateZ(35px) scale(1.05);
            box-shadow: 0 10px 20px rgba(0, 115, 230, 0.4);
        }

        .floating-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
            overflow: hidden;
        }

        .floating-element {
            position: absolute;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 50%;
        }

        .element-1 {
            width: 300px;
            height: 300px;
            top: -150px;
            right: -150px;
            animation: rotate 30s linear infinite;
        }

        .element-2 {
            width: 200px;
            height: 200px;
            bottom: -100px;
            left: -100px;
            animation: rotate 25s linear infinite reverse;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .footer {
            text-align: center;
            padding: 30px;
            background: rgba(0, 0, 0, 0.3);
            font-weight: 300;
            letter-spacing: 2px;
            transform: translateZ(40px);
        }

        /* Efectos 3D y perspectiva */
        .portfolio-card {
            transform: rotateX(5deg) rotateY(10deg);
            transition: transform 0.5s ease;
        }

        .portfolio-card:hover {
            transform: rotateX(0deg) rotateY(0deg);
        }

        /* Responsive */
        @media (max-width: 992px) {
            .content {
                grid-template-columns: 1fr;
            }
            
            .name {
                font-size: 2.5rem;
            }
        }

        @media (max-width: 576px) {
            .header {
                padding: 30px 20px;
            }
            
            .content {
                padding: 20px;
            }
            
            .name {
                font-size: 2rem;
                letter-spacing: 3px;
            }
            
            .title {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="portfolio-card">
            <div class="header">
                <h1 class="name">GIOVANNY MENDOZA VILLAMIZAR</h1>
                <p class="title">Desarrollador Full Stack & Diseñador UX/UI</p>
                
                <div class="floating-elements">
                    <div class="floating-element element-1"></div>
                    <div class="floating-element element-2"></div>
                </div>
            </div>
            
            <div class="content">
                <div class="section">
                    <h2 class="section-title">Proyectos</h2>
                    <ul class="project-list">
                        <li class="project-item">E-commerce con React y Node.js</li>
                        <li class="project-item">Aplicación de Gestión de Tareas</li>
                        <li class="project-item">Sistema de Reservas Online</li>
                        <li class="project-item">Dashboard Analítico con D3.js</li>
                        <li class="project-item">App Móvil de Delivery</li>
                    </ul>
                </div>
                
                <div class="section">
                    <h2 class="section-title">Habilidades</h2>
                    <div class="skills-container">
                        <div class="skill">JavaScript</div>
                        <div class="skill">React</div>
                        <div class="skill">Node.js</div>
                        <div class="skill">Three.js</div>
                        <div class="skill">CSS3</div>
                        <div class="skill">HTML5</div>
                        <div class="skill">MongoDB</div>
                        <div class="skill">Express</div>
                        <div class="skill">UI/UX Design</div>
                    </div>
                </div>
                
                <div class="section">
                    <h2 class="section-title">Experiencia</h2>
                    <p>+5 años de experiencia en desarrollo web, especializado en crear aplicaciones interactivas y experiencias de usuario inmersivas. He trabajado con startups y empresas internacionales.</p>
                    <br>
                    <p>Actualmente me enfoco en el desarrollo de aplicaciones 3D y realidad aumentada para web.</p>
                </div>
                
                <div class="section">
                    <h2 class="section-title">Contacto</h2>
                    <form class="contact-form">
                        <div class="form-group">
                            <label for="name">Nombre</label>
                            <input type="text" id="name" placeholder="Tu nombre">
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" placeholder="Tu email">
                        </div>
                        <div class="form-group">
                            <label for="message">Mensaje</label>
                            <textarea id="message" rows="4" placeholder="Tu mensaje"></textarea>
                        </div>
                        <button type="submit" class="btn">Enviar Mensaje</button>
                    </form>
                </div>
            </div>
            
            <div class="footer">
                <p>© 2023 Giovanny Mendoza Villamizar - Todos los derechos reservados</p>
            </div>
        </div>
    </div>

    <script>
        // Efectos de movimiento 3D con el mouse
        document.addEventListener('DOMContentLoaded', function() {
            const card = document.querySelector('.portfolio-card');
            const sections = document.querySelectorAll('.section');
            
            // Efecto de parallax con el movimiento del mouse
            document.addEventListener('mousemove', function(e) {
                const x = (window.innerWidth / 2 - e.clientX) / 25;
                const y = (window.innerHeight / 2 - e.clientY) / 25;
                
                card.style.transform = `rotateY(${x}deg) rotateX(${-y}deg)`;
                
                // Efecto en los elementos internos
                sections.forEach(section => {
                    const speed = parseInt(section.getAttribute('data-speed')) || 15;
                    const xPos = (window.innerWidth / 2 - e.clientX) / speed;
                    const yPos = (window.innerHeight / 2 - e.clientY) / speed;
                    
                    section.style.transform = `translateY(${-yPos}px) translateX(${xPos}px) translateZ(20px)`;
                });
            });
            
            // Resetear la posición cuando el mouse sale de la card
            card.addEventListener('mouseleave', function() {
                card.style.transform = 'rotateY(0deg) rotateX(0deg)';
                sections.forEach(section => {
                    section.style.transform = 'translateZ(0px)';
                });
            });
            
            // Efecto de typing para el título
            const nameElement = document.querySelector('.name');
            const originalName = nameElement.textContent;
            nameElement.textContent = '';
            
            let i = 0;
            function typeWriter() {
                if (i < originalName.length) {
                    nameElement.textContent += originalName.charAt(i);
                    i++;
                    setTimeout(typeWriter, 100);
                }
            }
            
            // Iniciar el efecto de escritura
            setTimeout(typeWriter, 500);
        });
    </script>
</body>
</html>
