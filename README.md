<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DevRomario - Desenvolvedor & Designer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #1a1a1a;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Header */
        .header {
            text-align: center;
            padding: 80px 0 60px;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.1);
            backdrop-filter: blur(15px);
            z-index: -1;
        }

        .profile-image {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            background: linear-gradient(45deg, #4facfe, #00f2fe);
            margin: 0 auto 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 64px;
            font-weight: bold;
            color: white;
            box-shadow: 0 25px 50px rgba(0,0,0,0.3);
            animation: float 4s ease-in-out infinite;
            border: 4px solid rgba(255,255,255,0.2);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-15px) rotate(5deg); }
        }

        .header h1 {
            font-size: 3.5rem;
            margin-bottom: 15px;
            font-weight: 800;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.3);
            background: linear-gradient(45deg, #fff, #f0f0f0);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .header .subtitle {
            font-size: 1.4rem;
            opacity: 0.95;
            font-weight: 400;
            letter-spacing: 1px;
        }

        /* Main Content */
        .main-content {
            background: white;
            border-radius: 25px;
            box-shadow: 0 40px 80px rgba(0,0,0,0.15);
            margin: -60px auto 0;
            position: relative;
            z-index: 1;
            overflow: hidden;
        }

        .section {
            padding: 60px 50px;
            border-bottom: 1px solid #f5f5f5;
            position: relative;
        }

        .section:last-child {
            border-bottom: none;
        }

        .section-title {
            font-size: 2.2rem;
            color: #2c3e50;
            margin-bottom: 40px;
            position: relative;
            text-align: center;
            font-weight: 700;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, #4facfe, #00f2fe);
            border-radius: 2px;
        }

        /* Apresentação */
        .intro-text {
            font-size: 1.15rem;
            line-height: 1.9;
            color: #555;
            text-align: center;
            max-width: 900px;
            margin: 0 auto;
            font-weight: 400;
        }

        /* Contato */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            margin-top: 40px;
        }

        .contact-item {
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            padding: 25px;
            border-radius: 20px;
            text-align: center;
            transition: all 0.4s ease;
            border: 2px solid transparent;
            position: relative;
            overflow: hidden;
        }

        .contact-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(79, 172, 254, 0.1), transparent);
            transition: left 0.6s;
        }

        .contact-item:hover::before {
            left: 100%;
        }

        .contact-item:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
            border-color: #4facfe;
        }

        .contact-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            filter: drop-shadow(2px 2px 4px rgba(79, 172, 254, 0.3));
        }

        .contact-label {
            font-weight: 700;
            color: #2c3e50;
            margin-bottom: 8px;
            font-size: 1rem;
        }

        .contact-value {
            color: #666;
            font-size: 1rem;
            font-weight: 500;
        }

        /* Áreas de Atuação */
        .areas-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 35px;
            margin-top: 40px;
        }

        .area-card {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 40px 25px;
            border-radius: 25px;
            text-align: center;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .area-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.15), transparent);
            transition: left 0.6s;
        }

        .area-card:hover::before {
            left: 100%;
        }

        .area-card:hover {
            transform: translateY(-12px) scale(1.02);
            box-shadow: 0 25px 50px rgba(0,0,0,0.2);
        }

        .area-icon {
            font-size: 3.5rem;
            margin-bottom: 20px;
            display: block;
            filter: drop-shadow(2px 2px 4px rgba(0,0,0,0.3));
        }

        .area-title {
            font-size: 1.3rem;
            font-weight: 700;
        }

        /* Ferramentas */
        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 25px;
            margin-top: 40px;
        }

        .tool-badge {
            background: white;
            border: 3px solid #4facfe;
            color: #4facfe;
            padding: 18px 25px;
            border-radius: 30px;
            text-align: center;
            font-weight: 700;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .tool-badge::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: #4facfe;
            transition: left 0.3s ease;
            z-index: -1;
        }

        .tool-badge:hover::before {
            left: 0;
        }

        .tool-badge:hover {
            color: white;
            transform: scale(1.08);
            box-shadow: 0 15px 30px rgba(79, 172, 254, 0.3);
        }

        /* Projetos */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin-top: 40px;
        }

        .project-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
            transition: all 0.4s ease;
            border: 2px solid transparent;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 50px rgba(0,0,0,0.15);
            border-color: #4facfe;
        }

        .project-image {
            width: 100%;
            height: 250px;
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            position: relative;
        }

        .project-image::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, rgba(79, 172, 254, 0.8), rgba(118, 75, 162, 0.8));
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .project-card:hover .project-image::after {
            opacity: 1;
        }

        .project-content {
            padding: 25px;
        }

        .project-title {
            font-size: 1.3rem;
            font-weight: 700;
            color: #2c3e50;
            margin-bottom: 10px;
        }

        .project-description {
            color: #666;
            font-size: 1rem;
            line-height: 1.6;
            margin-bottom: 15px;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .project-tag {
            background: #f0f8ff;
            color: #4facfe;
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 0.85rem;
            font-weight: 600;
        }

        /* Frase de Impacto */
        .impact-quote {
            background: linear-gradient(135deg, #2c3e50, #34495e);
            color: white;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .impact-quote::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at 50% 50%, rgba(79, 172, 254, 0.1) 0%, transparent 50%);
        }

        .quote-text {
            font-size: 2rem;
            font-style: italic;
            font-weight: 400;
            position: relative;
            z-index: 1;
            max-width: 800px;
            margin: 0 auto;
        }

        .quote-marks {
            font-size: 5rem;
            color: #4facfe;
            opacity: 0.4;
            line-height: 0;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }

            .header {
                padding: 60px 0 40px;
            }

            .profile-image {
                width: 140px;
                height: 140px;
                font-size: 48px;
            }

            .header h1 {
                font-size: 2.5rem;
            }

            .header .subtitle {
                font-size: 1.2rem;
            }

            .section {
                padding: 40px 25px;
            }

            .section-title {
                font-size: 1.8rem;
            }

            .quote-text {
                font-size: 1.5rem;
            }

            .contact-grid {
                grid-template-columns: 1fr;
            }

            .areas-grid {
                grid-template-columns: 1fr;
            }

            .tools-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Animations */
        .section {
            opacity: 0;
            transform: translateY(40px);
            animation: fadeInUp 1s ease forwards;
        }

        .section:nth-child(1) { animation-delay: 0.1s; }
        .section:nth-child(2) { animation-delay: 0.2s; }
        .section:nth-child(3) { animation-delay: 0.3s; }
        .section:nth-child(4) { animation-delay: 0.4s; }
        .section:nth-child(5) { animation-delay: 0.5s; }
        .section:nth-child(6) { animation-delay: 0.6s; }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Scroll suave */
        html {
            scroll-behavior: smooth;
        }

        /* Hover effects globais */
        .section {
            transition: all 0.3s ease;
        }

        .section:hover {
            background: rgba(79, 172, 254, 0.02);
        }
    </style>
</head>
<body>
    <!-- Header -->
    <div class="header">
        <div class="container">
            <div class="profile-image">R</div>
            <h1>DevRomario</h1>
            <p class="subtitle">Desenvolvedor & Designer Gráfico</p>
        </div>
    </div>

    <!-- Main Content -->
    <div class="container">
        <div class="main-content">
            <!-- Apresentação -->
            <section class="section">
                <h2 class="section-title">Sobre Mim</h2>
                <p class="intro-text">
                    Sou Romario da Silva Santos, um profissional multidisciplinar apaixonado por tecnologia e design. Com experiência sólida em desenvolvimento web, design gráfico e edição de vídeo, transformo ideias criativas em projetos funcionais e visualmente impactantes. Movido pela inovação e pela busca constante por soluções elegantes, combino técnica e criatividade para entregar experiências digitais memoráveis. Minha versatilidade me permite atuar em diferentes frentes, sempre focado em resultados que fazem a diferença.
                </p>
            </section>

            <!-- Contato -->
            <section class="section">
                <h2 class="section-title">Contato</h2>
                <div class="contact-grid">
                    <div class="contact-item">
                        <div class="contact-icon">👤</div>
                        <div class="contact-label">Nome Completo</div>
                        <div class="contact-value">Romario da Silva Santos</div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">💼</div>
                        <div class="contact-label">Nome Profissional</div>
                        <div class="contact-value">DevRomario</div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📧</div>
                        <div class="contact-label">E-mail</div>
                        <div class="contact-value">romasantos.023@gmail.com</div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📱</div>
                        <div class="contact-label">Telefone</div>
                        <div class="contact-value">(71) 98482-8604</div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📍</div>
                        <div class="contact-label">Localização</div>
                        <div class="contact-value">Salvador, Brasil</div>
                    </div>
                </div>
            </section>

            <!-- Áreas de Atuação -->
            <section class="section">
                <h2 class="section-title">Áreas de Atuação</h2>
                <div class="areas-grid">
                    <div class="area-card">
                        <span class="area-icon">🎨</span>
                        <div class="area-title">Design Gráfico</div>
                    </div>
                    <div class="area-card">
                        <span class="area-icon">🎬</span>
                        <div class="area-title">Edição de Vídeo</div>
                    </div>
                    <div class="area-card">
                        <span class="area-icon">💻</span>
                        <div class="area-title">Desenvolvimento Web</div>
                    </div>
                </div>
            </section>

            <!-- Ferramentas -->
            <section class="section">
                <h2 class="section-title">Ferramentas Dominadas</h2>
                <div class="tools-grid">
                    <div class="tool-badge">HTML/CSS</div>
                    <div class="tool-badge">JavaScript</div>
                    <div class="tool-badge">Figma</div>
                    <div class="tool-badge">Canva</div>
                    <div class="tool-badge">PowerBI</div>
                    <div class="tool-badge">HelpDesk</div>
                </div>
            </section>

            <!-- Projetos -->
            <section class="section">
                <h2 class="section-title">Projetos</h2>
                <div class="projects-grid">
                    <div class="project-card">
                        <div class="project-image">
                            <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR42mP8/5+hHgAHggJ/PchI7wAAAABJRU5ErkJggg==" alt="App Mobile Autocuidado" style="width: 100%; height: 100%; object-fit: cover; border-radius: 0;" id="project1-img">
                        </div>
                        <div class="project-content">
                            <h3 class="project-title">App Mobile - Autocuidado</h3>
                            <p class="project-description">Interface de aplicativo mobile focado em autocuidado e bem-estar, com design em tons de rosa e elementos visuais que remetem ao amor próprio.</p>
                            <div class="project-tags">
                                <span class="project-tag">UI/UX Design</span>
                                <span class="project-tag">Mobile App</span>
                                <span class="project-tag">Figma</span>
                            </div>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-image">
                            <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR42mP8/5+hHgAHggJ/PchI7wAAAABJRU5ErkJggg==" alt="Material Comemorativo Clínica Sermec" style="width: 100%; height: 100%; object-fit: cover; border-radius: 0;" id="project2-img">
                        </div>
                        <div class="project-content">
                            <h3 class="project-title">Material Comemorativo - Clínica Sermec</h3>
                            <p class="project-description">Peça gráfica comemorativa para o Dia do Profissional de Administração da Clínica Sermec, celebrando 30 anos de história com design corporativo em azul.</p>
                            <div class="project-tags">
                                <span class="project-tag">Design Gráfico</span>
                                <span class="project-tag">Identidade Visual</span>
                                <span class="project-tag">Canva</span>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Frase de Impacto -->
            <section class="section impact-quote">
                <div class="quote-marks">"</div>
                <p class="quote-text">Entre o código e a criação, eu construo experiências que se conectam com pessoas.</p>
                <div class="quote-marks" style="transform: rotate(180deg);">"</div>
            </section>
        </div>
    </div>

    <script>
        // Função para carregar as imagens dos projetos
        async function loadProjectImages() {
            try {
                // Carrega a primeira imagem (App Mobile)
                const img1Data = await window.fs.readFile('Image 1', { encoding: 'base64' });
                const project1Img = document.getElementById('project1-img');
                if (project1Img) {
                    project1Img.src = `data:image/png;base64,${img1Data}`;
                }
                
                // Carrega a segunda imagem (Clínica Sermec)
                const img2Data = await window.fs.readFile('Image 2', { encoding: 'base64' });
                const project2Img = document.getElementById('project2-img');
                if (project2Img) {
                    project2Img.src = `data:image/png;base64,${img2Data}`;
                }
            } catch (error) {
                console.log('Erro ao carregar imagens:', error);
                // Mantém as imagens placeholder em caso de erro
            }
        }

        // Executa quando a página carrega
        document.addEventListener('DOMContentLoaded', loadProjectImages);
    </script>
</body>
</html>
