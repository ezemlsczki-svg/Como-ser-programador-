<!DOCTYPE html>
<html lang="pt-pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DevMaster - Curso 40 Aulas</title>
    <style>
        :root {
            --primary: #00ff88;
            --dark: #0f172a;
            --card: #1e293b;
            --text: #f8fafc;
        }

        body {
            font-family: 'Segoe UI', sans-serif;
            background-color: var(--dark);
            color: var(--text);
            margin: 0;
            line-height: 1.6;
        }

        header {
            background: linear-gradient(135deg, #1e293b, #0f172a);
            padding: 60px 20px;
            text-align: center;
            border-bottom: 2px solid var(--primary);
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
        }

        .stats {
            display: flex;
            justify-content: space-around;
            background: var(--card);
            padding: 20px;
            border-radius: 10px;
            margin-top: -40px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .module-card {
            background: var(--card);
            margin: 20px 0;
            padding: 20px;
            border-radius: 10px;
            border-left: 5px solid var(--primary);
            transition: 0.3s;
        }

        .module-card:hover {
            transform: scale(1.02);
        }

        .lesson-list {
            display: none;
            margin-top: 15px;
            padding-left: 20px;
            border-top: 1px solid #334155;
        }

        .lesson-item {
            list-style: none;
            padding: 10px 0;
            display: flex;
            align-items: center;
            border-bottom: 1px solid #334155;
        }

        .lesson-item::before {
            content: "▶";
            color: var(--primary);
            margin-right: 10px;
            font-size: 12px;
        }

        .btn-toggle {
            background: var(--primary);
            color: var(--dark);
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            float: right;
        }

        .progress-bar {
            width: 100%;
            background: #334155;
            height: 10px;
            border-radius: 5px;
            margin-top: 20px;
        }

        .progress-fill {
            width: 5%; /* Inicia em 5% */
            background: var(--primary);
            height: 100%;
            border-radius: 5px;
            transition: 1s;
        }

        footer {
            text-align: center;
            padding: 40px;
            color: #64748b;
        }

        /* Modal para Aula */
        #lesson-modal {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: var(--card);
            padding: 30px;
            border-radius: 15px;
            z-index: 100;
            width: 80%;
            max-width: 600px;
            border: 1px solid var(--primary);
        }
    </style>
</head>
<body>

<header>
    <h1>🚀 Jornada do Programador Pro</h1>
    <p>Domina o Full-Stack em 40 Aulas Práticas</p>
</header>

<div class="container">
    <div class="stats">
        <div><strong>4</strong> Módulos</div>
        <div><strong>40</strong> Aulas</div>
        <div><strong>1</strong> Projeto Final</div>
    </div>

    <div class="progress-bar">
        <div class="progress-fill" id="p-fill"></div>
    </div>
    <p><small>Progresso do Curso: <span id="p-text">5%</span></small></p>

    <div class="module-card">
        <button class="btn-toggle" onclick="toggle('m1')">Ver Aulas</button>
        <h3>📦 Módulo 1: Fundamentos HTML5</h3>
        <p>Aprende a criar a estrutura de qualquer site do mundo.</p>
        <div id="m1" class="lesson-list">
            <div class="lesson-item" onclick="openLesson(1)">Aula 01: O que é a Web?</div>
            <div class="lesson-item">Aula 02: Instalando o Editor de Código</div>
            <div class="lesson-item">Aula 03: Tags básicas: h1, p, div</div>
            <div class="lesson-item">Aula 04: Criando Listas e Menus</div>
            <div class="lesson-item">Aula 05: Links e Navegação Interna</div>
            <div class="lesson-item">... e mais 5 aulas</div>
        </div>
    </div>

    <div class="module-card">
        <button class="btn-toggle" onclick="toggle('m2')">Ver Aulas</button>
        <h3>🎨 Módulo 2: Design com CSS3</h3>
        <p>Cores, layouts, fontes e responsividade para telemóvel.</p>
        <div id="m2" class="lesson-list">
            <div class="lesson-item">Aula 11: Seletores e Cores</div>
            <div class="lesson-item">Aula 12: Box Model (Espaçamentos)</div>
            <div class="lesson-item">Aula 13: Flexbox (Alinhamento Magico)</div>
            <div class="lesson-item">Aula 14: CSS Grid Layout</div>
            <div class="lesson-item">... e mais 6 aulas</div>
        </div>
    </div>

    <div class="module-card">
        <button class="btn-toggle" onclick="toggle('m3')">Ver Aulas</button>
        <h3>⚡ Módulo 3: Lógica JavaScript</h3>
        <p>Dá vida ao teu site com programação real.</p>
        <div id="m3" class="lesson-list">
            <div class="lesson-item">Aula 21: Variáveis e Funções</div>
            <div class="lesson-item">Aula 22: Condicionais e Bucles</div>
            <div class="lesson-item">Aula 23: Manipulação do DOM</div>
            <div class="lesson-item">... e mais 7 aulas</div>
        </div>
    </div>

    <div class="module-card">
        <button class="btn-toggle" onclick="toggle('m4')">Ver Aulas</button>
        <h3>🏆 Módulo 4: Projeto Final & Mercado</h3>
        <p>Publica o teu site e prepara o teu portfólio.</p>
        <div id="m4" class="lesson-list">
            <div class="lesson-item">Aula 31: Git e GitHub</div>
            <div class="lesson-item">Aula 40: Construindo o Dashboard Final</div>
        </div>
    </div>
</div>

<div id="lesson-modal">
    <h2 id="m-title">Título da Aula</h2>
    <p id="m-content">Conteúdo da aula aqui...</p>
    <button onclick="closeModal()">Fechar e Marcar Concluída</button>
</div>

<footer>
    <p>Feito para quem quer ser Dev. 2026</p>
</footer>

<script>
    function toggle(id) {
        let el = document.getElementById(id);
        el.style.display = el.style.display === 'block' ? 'none' : 'block';
    }

    function openLesson(n) {
        document.getElementById('lesson-modal').style.display = 'block';
        document.getElementById('m-title').innerText = "Aula 01: Introdução";
        document.getElementById('m-content').innerText = "Bem-vindo! Nesta aula vais entender que o HTML é a linguagem que o navegador lê para desenhar textos e imagens.";
    }

    function closeModal() {
        document.getElementById('lesson-modal').style.display = 'none';
        document.getElementById('p-fill').style.width = '100%';
        document.getElementById('p-text').innerText = '100% (Modo Demo)';
        alert("Aula concluída! Estás no caminho certo.");
    }
</script>

</body>
</html>
