<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Festejando a Conexão Campo-Cidade</title>
    <style>
        /* Reset e Estilos Gerais */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --verde-campo: #4a7c59;
            --marrom-terra: #8b5a2b;
            --cinza-cidade: #6c757d;
            --branco: #f8f9fa;
            --preto: #212529;
            --amarelo-sol: #ffc107;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--preto);
            background-color: var(--branco);
        }
        
        /* Acessibilidade */
        .sr-only {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0, 0, 0, 0);
            white-space: nowrap;
            border-width: 0;
        }
        
        /* Cabeçalho */
        header {
            background: linear-gradient(to right, var(--verde-campo), var(--cinza-cidade));
            color: var(--branco);
            padding: 2rem 0;
            text-align: center;
        }
        
        header h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        header p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto;
        }
        
        /* Navegação */
        nav {
            background-color: var(--marrom-terra);
            padding: 1rem;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
            flex-wrap: wrap;
        }
        
        nav li {
            margin: 0 1rem;
        }
        
        nav a {
            color: var(--branco);
            text-decoration: none;
            font-weight: bold;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            transition: background-color 0.3s;
        }
        
        nav a:hover, nav a:focus {
            background-color: var(--verde-campo);
            outline: 2px solid var(--amarelo-sol);
        }
        
        /* Conteúdo Principal */
        main {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1rem;
        }
        
        section {
            margin-bottom: 3rem;
        }
        
        h2 {
            color: var(--verde-campo);
            margin-bottom: 1.5rem;
            text-align: center;
            font-size: 2rem;
        }
        
        /* Galeria */
        .galeria {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }
        
        .galeria-item {
            position: relative;
            overflow: hidden;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        
        .galeria-item:hover {
            transform: translateY(-5px);
        }
        
        .galeria-item img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            display: block;
        }
        
        .galeria-legenda {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(0, 0, 0, 0.7);
            color: var(--branco);
            padding: 1rem;
            transform: translateY(100%);
            transition: transform 0.3s;
        }
        
        .galeria-item:hover .galeria-legenda {
            transform: translateY(0);
        }
        
        /* Cards */
        .cards {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: center;
        }
        
        .card {
            background-color: var(--branco);
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            max-width: 350px;
            transition: transform 0.3s;
        }
        
        .card:hover {
            transform: translateY(-5px);
        }
        
        .card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }
        
        .card-conteudo {
            padding: 1.5rem;
        }
        
        .card h3 {
            color: var(--verde-campo);
            margin-bottom: 1rem;
        }
        
        /* Rodapé */
        footer {
            background: linear-gradient(to right, var(--verde-campo), var(--cinza-cidade));
            color: var(--branco);
            text-align: center;
            padding: 2rem 0;
            margin-top: 3rem;
        }
        
        footer p {
            margin-bottom: 1rem;
        }
        
        .redes-sociais {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 1rem;
        }
        
        .redes-sociais a {
            color: var(--branco);
            font-size: 1.5rem;
            transition: color 0.3s;
        }
        
        .redes-sociais a:hover, .redes-sociais a:focus {
            color: var(--amarelo-sol);
            outline: none;
        }
        
        /* Botão de Acessibilidade */
        .acessibilidade {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: var(--verde-campo);
            color: var(--branco);
            border: none;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            font-size: 1.5rem;
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 100;
        }
        
        .acessibilidade:hover {
            background-color: var(--marrom-terra);
        }
        
        /* Responsividade */
        @media (max-width: 768px) {
            header h1 {
                font-size: 2rem;
            }
            
            nav ul {
                flex-direction: column;
                align-items: center;
            }
            
            nav li {
                margin: 0.5rem 0;
            }
            
            .galeria {
                grid-template-columns: 1fr;
            }
        }
        
        /* Modo Alto Contraste */
        .alto-contraste {
            background-color: black !important;
            color: white !important;
        }
        
        .alto-contraste header,
        .alto-contraste footer,
        .alto-contraste nav {
            background: black !important;
            color: yellow !important;
            border: 1px solid yellow;
        }
        
        .alto-contraste h1,
        .alto-contraste h2,
        .alto-contraste h3,
        .alto-contraste a {
            color: yellow !important;
        }
        
        .alto-contraste .card {
            background-color: black !important;
            border: 1px solid yellow;
            color: white !important;
        }
    </style>
</head>
<body>
    <!-- Botão de Acessibilidade -->
    <button class="acessibilidade" id="btnAcessibilidade" aria-label="Ativar alto contraste">
        A
    </button>
    
    <!-- Cabeçalho -->
    <header>
        <h1>Festejando a Conexão Campo-Cidade</h1>
        <p>Celebrando a harmonia e a interdependência entre a vida rural e urbana que nutrem nosso país</p>
    </header>
    
    <!-- Navegação -->
    <nav>
        <ul>
            <li><a href="#sobre">Sobre</a></li>
            <li><a href="#galeria">Galeria</a></li>
            <li><a href="#beneficios">Benefícios</a></li>
            <li><a href="#eventos">Eventos</a></li>
            <li><a href="#contato">Contato</a></li>
        </ul>
    </nav>
    
    <!-- Conteúdo Principal -->
    <main>
        <section id="sobre">
            <h2>Sobre a Conexão</h2>
            <p>O campo e a cidade são realidades que se complementam. Enquanto o campo produz os alimentos que nutrem a população urbana, a cidade oferece tecnologia, serviços e mercados que impulsionam o desenvolvimento rural. Esta conexão vital merece ser celebrada!</p>
            
            <div class="cards">
                <article class="card">
                    <img src="https://images.unsplash.com/photo-1498837167922-ddd27525d352?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Agricultor colhendo vegetais frescos">
                    <div class="card-conteudo">
                        <h3>Alimentos Frescos</h3>
                        <p>O campo fornece alimentos frescos e nutritivos para as cidades, garantindo saúde e qualidade de vida para a população urbana.</p>
                    </div>
                </article>
                
                <article class="card">
                    <img src="https://images.unsplash.com/photo-1500382017468-9049fed747ef?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Paisagem rural com plantações e montanhas ao fundo">
                    <div class="card-conteudo">
                        <h3>Preservação Ambiental</h3>
                        <p>As áreas rurais são essenciais para a preservação de ecossistemas, recursos hídricos e a biodiversidade que sustentam a vida nas cidades.</p>
                    </div>
                </article>
                
                <article class="card">
                    <img src="https://images.unsplash.com/photo-1521791136064-7986c2920216?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Feira de produtos orgânicos na cidade">
                    <div class="card-conteudo">
                        <h3>Cultura e Tradições</h3>
                        <p>A troca cultural entre campo e cidade enriquece a sociedade, preservando tradições e promovendo a diversidade.</p>
                    </div>
                </article>
            </div>
        </section>
        
        <section id="galeria">
            <h2>Nossa Galeria</h2>
            <p>Explore imagens que capturam a beleza e a importância da conexão entre o campo e a cidade.</p>
            
            <div class="galeria">
                <div class="galeria-item">
                    <img src="https://images.unsplash.com/photo-1523741543316-beb7fc7023d8?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Caminhão transportando alimentos do campo para a cidade">
                    <div class="galeria-legenda">
                        <h3>Transporte de Alimentos</h3>
                        <p>A logística que conecta a produção rural aos consumidores urbanos</p>
                    </div>
                </div>
                
                <div class="galeria-item">
                    <img src="https://images.unsplash.com/photo-1550581190-9c1c48d21d6c?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Feira de agricultores na cidade">
                    <div class="galeria-legenda">
                        <h3>Feiras Urbanas</h3>
                        <p>Agricultores levam seus produtos diretamente aos consumidores nas cidades</p>
                    </div>
                </div>
                
                <div class="galeria-item">
                    <img src="https://images.unsplash.com/photo-1516937941344-00b4e0337589?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Tecnologia agrícola moderna">
                    <div class="galeria-legenda">
                        <h3>Tecnologia no Campo</h3>
                        <p>Inovações urbanas aumentam a produtividade agrícola</p>
                    </div>
                </div>
                
                <div class="galeria-item">
                    <img src="https://images.unsplash.com/photo-1500382017468-9049fed747ef?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Turistas visitando uma fazenda">
                    <div class="galeria-legenda">
                        <h3>Turismo Rural</h3>
                        <p>Urbanos redescobrem as raízes no campo</p>
                    </div>
                </div>
                
                <div class="galeria-item">
                    <img src="https://images.unsplash.com/photo-1498837167922-ddd27525d352?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Crianças aprendendo sobre agricultura">
                    <div class="galeria-legenda">
                        <h3>Educação Ambiental</h3>
                        <p>Escolas urbanas visitam propriedades rurais para aprendizado</p>
                    </div>
                </div>
                
                <div class="galeria-item">
                    <img src="https://images.unsplash.com/photo-1521791136064-7986c2920216?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Produtos artesanais em exposição">
                    <div class="galeria-legenda">
                        <h3>Artesanato Rural</h3>
                        <p>Técnicas tradicionais encontram mercado nas cidades</p>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="beneficios">
            <h2>Benefícios da Conexão</h2>
            <p>A integração entre campo e cidade traz vantagens para toda a sociedade:</p>
            
            <ul style="margin-top: 1rem; margin-left: 2rem;">
                <li style="margin-bottom: 0.5rem;">Alimentos mais frescos e saudáveis nas cidades</li>
                <li style="margin-bottom: 0.5rem;">Melhores preços para os produtores rurais</li>
                <li style="margin-bottom: 0.5rem;">Preservação de saberes tradicionais</li>
                <li style="margin-bottom: 0.5rem;">Desenvolvimento de tecnologias apropriadas</li>
                <li style="margin-bottom: 0.5rem;">Oportunidades de turismo e lazer</li>
                <li style="margin-bottom: 0.5rem;">Conservação ambiental e sustentabilidade</li>
            </ul>
            
            <div style="margin-top: 2rem; background-color: #e9ecef; padding: 1.5rem; border-radius: 8px;">
                <h3 style="color: var(--marrom-terra); margin-bottom: 1rem;">Dados Importantes</h3>
                <p>Segundo a FAO, cerca de 80% dos alimentos consumidos nas cidades vêm da agricultura familiar. A conexão direta entre produtores rurais e consumidores urbanos reduz desperdícios e melhora a qualidade nutricional.</p>
            </div>
        </section>
        
        <section id="eventos">
            <h2>Eventos e Celebrações</h2>
            <p>Participe dos eventos que celebram a conexão campo-cidade:</p>
            
            <div class="cards" style="margin-top: 2rem;">
                <article class="card">
                    <img src="https://images.unsplash.com/photo-1519817650390-64a93db51149?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Feira de produtos orgânicos">
                    <div class="card-conteudo">
                        <h3>Feira do Produtor</h3>
                        <p><strong>Data:</strong> Todo primeiro sábado do mês</p>
                        <p><strong>Local:</strong> Praça Central</p>
                        <p>Agricultores locais vendem diretamente ao consumidor</p>
                    </div>
                </article>
                
                <article class="card">
                    <img src="https://images.unsplash.com/photo-1544396821-4dd40b938ad3?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Festa da colheita">
                    <div class="card-conteudo">
                        <h3>Festa da Colheita</h3>
                        <p><strong>Data:</strong> 15 de agosto</p>
                        <p><strong>Local:</strong> Parque Municipal</p>
                        <p>Celebração das tradições agrícolas com música, dança e gastronomia</p>
                    </div>
                </article>
                
                <article class="card">
                    <img src="https://images.unsplash.com/photo-1527529482837-4698179dc6ce?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=80" alt="Visita a fazenda">
                    <div class="card-conteudo">
                        <h3>Dia na Roça</h3>
                        <p><strong>Data:</strong> 12 de outubro</p>
                        <p><strong>Local:</strong> Fazendas participantes</p>
                        <p>Experiência rural para famílias urbanas</p>
                    </div>
                </article>
            </div>
        </section>
        
        <section id="contato">
            <h2>Entre em Contato</h2>
            <p>Quer participar, sugerir eventos ou saber mais sobre nossa iniciativa?</p>
            
            <form style="max-width: 600px; margin: 2rem auto; background-color: #f8f9fa; padding: 2rem; border-radius: 8px;">
                <div style="margin-bottom: 1rem;">
                    <label for="nome" style="display: block; margin-bottom: 0.5rem;">Nome:</label>
                    <input type="text" id="nome" name="nome" style="width: 100%; padding: 0.5rem; border: 1px solid #ced4da; border-radius: 4px;">
                </div>
                
                <div style="margin-bottom: 1rem;">
                    <label for="email" style="display: block; margin-bottom: 0.5rem;">E-mail:</label>
                    <input type="email" id="email" name="email" style="width: 100%; padding: 0.5rem; border: 1px solid #ced4da; border-radius: 4px;">
                </div>
                
                <div style="margin-bottom: 1rem;">
                    <label for="mensagem" style="display: block; margin-bottom: 0.5rem;">Mensagem:</label>
                    <textarea id="mensagem" name="mensagem" rows="4" style="width: 100%; padding: 0.5rem; border: 1px solid #ced4da; border-radius: 4px;"></textarea>
                </div>
                
                <button type="submit" style="background-color: var(--verde-campo); color: white; padding: 0.75rem 1.5rem; border: none; border-radius: 4px; cursor: pointer; font-weight: bold;">Enviar Mensagem</button>
            </form>
        </section>
    </main>
    
    <!-- Rodapé -->
    <footer>
        <p>Festejando a Conexão Campo-Cidade</p>
        <p>Promovendo o diálogo e a integração entre o rural e o urbano</p>
        
        <div class="redes-sociais">
            <a href="#" aria-label="Facebook"><i class="fab fa-facebook"></i></a>
            <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
            <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
            <a href="#" aria-label="YouTube"><i class="fab fa-youtube"></i></a>
        </div>
        
        <p style="margin-top: 2rem;">&copy; 2023 - Todos os direitos reservados</p>
    </footer>
    
    <!-- Scripts -->
    <script>
        // Botão de alto contraste
        document.getElementById('btnAcessibilidade').addEventListener('click', function() {
            document.body.classList.toggle('alto-contraste');
            
            // Alterar texto do botão para indicar o estado
            if (document.body.classList.contains('alto-contraste')) {
                this.textContent = 'A';
                this.setAttribute('aria-label', 'Desativar alto contraste');
            } else {
                this.textContent = 'A';
                this.setAttribute('aria-label', 'Ativar alto contraste');
            }
        });
        
        // Adicionando Font Awesome para ícones (simulação)
        // Em um site real, você incluiria o link para o CDN do Font Awesome
        setTimeout(() => {
            const style = document.createElement('style');
            style.innerHTML = `
                .fa-facebook:before { content: "F"; }
                .fa-instagram:before { content: "I"; }
                .fa-twitter:before { content: "T"; }
                .fa-youtube:before { content: "Y"; }
                .fab {
                    font-style: normal;
                    font-weight: bold;
                    font-family: initial;
                }
            `;
            document.head.appendChild(style);
        }, 100);
    </script>
</body>
</html>
