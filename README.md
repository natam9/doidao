seu-repositorio/
├── index.html
├── style.css
├── script.js
└── README.md

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Site no GitHub Pages</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Bem-vindo ao Meu Site</h1>
        <nav>
            <ul>
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#projetos">Projetos</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="sobre">
            <h2>Sobre Mim</h2>
            <p>Este é um site de exemplo hospedado no GitHub Pages.</p>
        </section>

        <section id="projetos">
            <h2>Meus Projetos</h2>
            <div class="projetos-container">
                <!-- Projetos serão adicionados via JavaScript -->
            </div>
        </section>

        <section id="contato">
            <h2>Contato</h2>
            <form id="form-contato">
                <input type="text" placeholder="Seu nome" required>
                <input type="email" placeholder="Seu email" required>
                <textarea placeholder="Sua mensagem" required></textarea>
                <button type="submit">Enviar</button>
            </form>
        </section>
    </main>

    <footer>
        <p>&copy; <span id="ano-atual"></span> Meu Site. Todos os direitos reservados.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>

/* Reset básico */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    color: #333;
    background-color: #f4f4f4;
}

header {
    background: #35424a;
    color: #ffffff;
    padding: 1rem 0;
    text-align: center;
}

nav ul {
    display: flex;
    justify-content: center;
    list-style: none;
    padding: 1rem 0;
}

nav ul li a {
    color: #ffffff;
    text-decoration: none;
    padding: 0.5rem 1rem;
    margin: 0 0.5rem;
    border-radius: 5px;
    transition: background 0.3s;
}

nav ul li a:hover {
    background: #e8491d;
}

main {
    padding: 2rem;
    max-width: 1200px;
    margin: 0 auto;
}

section {
    margin-bottom: 2rem;
    padding: 2rem;
    background: #ffffff;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

h2 {
    color: #35424a;
    margin-bottom: 1rem;
    border-bottom: 2px solid #e8491d;
    padding-bottom: 0.5rem;
}

.projetos-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1rem;
}

.projeto-card {
    border: 1px solid #ddd;
    padding: 1rem;
    border-radius: 5px;
    transition: transform 0.3s;
}

.projeto-card:hover {
    transform: translateY(-5px);
}

form {
    display: grid;
    gap: 1rem;
    max-width: 500px;
}

input, textarea {
    padding: 0.5rem;
    border: 1px solid #ddd;
    border-radius: 5px;
}

button {
    background: #35424a;
    color: #ffffff;
    padding: 0.7rem;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background 0.3s;
}

button:hover {
    background: #e8491d;
}

footer {
    text-align: center;
    padding: 1rem;
    background: #35424a;
    color: #ffffff;
    margin-top: 2rem;
}

/* Responsividade */
@media (max-width: 768px) {
    nav ul {
        flex-direction: column;
    }
    
    nav ul li {
        margin: 0.5rem 0;
    }
}

// Atualiza o ano no footer
document.getElementById('ano-atual').textContent = new Date().getFullYear();

// Dados dos projetos (pode ser substituído por uma API)
const projetos = [
    {
        titulo: "Projeto 1",
        descricao: "Descrição do primeiro projeto incrível.",
        link: "#"
    },
    {
        titulo: "Projeto 2",
        descricao: "Descrição do segundo projeto maravilhoso.",
        link: "#"
    },
    {
        titulo: "Projeto 3",
        descricao: "Descrição do terceiro projeto espetacular.",
        link: "#"
    }
];

// Renderiza os projetos
const projetosContainer = document.querySelector('.projetos-container');

projetos.forEach(projeto => {
    const projetoCard = document.createElement('div');
    projetoCard.className = 'projeto-card';
    projetoCard.innerHTML = `
        <h3>${projeto.titulo}</h3>
        <p>${projeto.descricao}</p>
        <a href="${projeto.link}" class="btn">Ver Projeto</a>
    `;
    projetosContainer.appendChild(projetoCard);
});

// Formulário de contato
const formContato = document.getElementById('form-contato');

formContato.addEventListener('submit', function(e) {
    e.preventDefault();
    alert('Mensagem enviada com sucesso! (Este é um exemplo, nenhum dado foi realmente enviado)');
    formContato.reset();
});

// Efeito suave ao rolar para as seções
document.querySelectorAll('nav a').forEach(anchor => {
    anchor.addEventListener('click', function(e) {
        e.preventDefault();
        
        const targetId = this.getAttribute('href');
        const targetElement = document.querySelector(targetId);
        
        window.scrollTo({
            top: targetElement.offsetTop - 20,
            behavior: 'smooth'
        });
    });
});

# Meu Site no GitHub Pages

Este é o repositório do meu site pessoal hospedado no GitHub Pages.

## Como usar

1. Clone este repositório
2. Faça as alterações desejadas nos arquivos
3. Faça commit e push das alterações

O GitHub Pages irá automaticamente publicar o conteúdo da branch `main` ou `gh-pages`.

## Personalização

- Edite `index.html` para alterar o conteúdo
- Modifique `style.css` para mudar o design
- Atualize `script.js` para adicionar funcionalidades

## Licença

Este projeto está licenciado sob a licença MIT.
