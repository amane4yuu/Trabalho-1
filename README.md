# Trabalho-1

# alunos:
Maria Eduarda de Sousa Rocha 557456  

Pedro César Duarte Pinto Silva 554618

Antonio Emanuel Abreu da Silva 561528


# 1º questão:
 
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Questões</title>
</head>
<body>
    <h1>Questões</h1>
    <p>Essa página visa responder as questões referentes a atividade.</p>
    <a href="https://www.example.com/" target="_blank">Clique aqui para acessar outra página</a>
</body>
</html>
Faraday

# 2º Questão

 <section>: Cada bloco de texto é encapsulado em uma tag <section>, que semânticamente representa uma seção independente do conteúdo.
class: Cada <section> tem uma classe distinta (bloco-1, bloco-2, bloco-3), que permite aplicar estilos específicos a cada bloco.
Faraday

# 3° QUestão:
 

Adicionar um padding-top ou margin-top ao conteúdo principal


A ideia aqui é adicionar um espaçamento no topo do conteúdo principal para garantir que ele não fique escondido atrás da barra fixa.
Vantagens:

    Simples e direto: Você só precisa adicionar um padding-top (ou margin-top) ao conteúdo principal. Isso resolve o problema sem grandes alterações no HTML.
    Fácil de implementar: Se você já tem um design pronto, basta adicionar esse estilo à classe do conteúdo principal, o que facilita a solução.

Desvantagens:

    Precisa de ajustes manuais: O valor do padding-top precisa ser ajustado com base na altura da barra de navegação. Se a altura da barra mudar (por exemplo, em telas pequenas ou durante mudanças no design), você precisará ajustar esse valor manualmente.
    Não é a solução mais flexível: Em sites dinâmicos, se a altura da barra de navegação mudar dependendo do contexto (por exemplo, ao expandir o menu), você precisará ajustar novamente os valores.

-------------------------------------------------

    Usar a propriedade z-index e position: relative para o conteúdo principal


Uma outra solução seria usar o z-index para garantir que o conteúdo principal seja colocado abaixo da barra de navegação, sem que ele se sobreponha.
Vantagens:

    Solução mais robusta: O uso de z-index com position: relative pode garantir que o conteúdo principal seja renderizado corretamente abaixo da barra fixa, especialmente se você tiver outros elementos flutuantes ou com diferentes camadas.
    Mais flexível: Essa abordagem pode funcionar bem em sites mais complexos, onde o conteúdo não precisa de um padding-top fixo e o layout depende de vários elementos sobrepostos.

Desvantagens:

    Exige atenção com o uso de z-index: Usar z-index incorretamente pode causar problemas com a sobreposição de outros elementos. Se você não configurar os valores de z-index corretamente, pode ocorrer um comportamento inesperado em outros elementos da página.
    Mais complexo: Embora a solução seja mais flexível, ela pode ser mais difícil de implementar se você não estiver familiarizado com o controle de camadas (z-index) e o comportamento de empilhamento de elementos.


# 4° questão 

Na abordagem "Mobile First", você começa criando o layout e os estilos para dispositivos móveis (telas menores) e, em seguida, vai aprimorando o design para telas maiores com o uso de media queries.
Como funciona:

    Estilo básico: Comece com o estilo padrão para telas pequenas (como smartphones). Isso significa que os estilos padrões vão atender ao design para dispositivos móveis.
    Media Queries para telas maiores: Depois, você aplica estilos para telas maiores (tablets, desktops) usando media queries que "adicionam" ou modificam o design conforme o tamanho da tela aumenta.

O estilo inicial aplica-se a dispositivos móveis, com width: 100% e fontes menores.
Quando a tela tem pelo menos 768px (típico de tablets), a largura do conteúdo é restringida a 750px e o tamanho da fonte do título é aumentado.
Quando a tela atinge 1024px ou mais (desktops), a largura da .container aumenta para 1000px e o tamanho da fonte também cresce.
Faraday
 — 
Hoje às 19:45
/* Estilos padrão para dispositivos móveis /
body {
    font-family: Arial, sans-serif;
    padding: 20px;
    font-size: 16px;
}

.container {
    width: 100%;  / O conteúdo ocupa toda a largura da tela /
}

h1 {
    font-size: 24px;  / Tamanho de fonte ajustado para telas pequenas /
}

/ Media Query para telas maiores (tablets e acima) /
@media (min-width: 768px) {
    .container {
        width: 750px; / Limita a largura da caixa para telas maiores /
    }

    h1 {
        font-size: 32px;  / Aumenta o tamanho da fonte em telas maiores /
    }
}

/ Media Query para telas grandes (desktops) /
@media (min-width: 1024px) {
    .container {
        width: 1000px;  / Limita a largura para telas de desktop /
    }

    h1 {
        font-size: 40px;  / Aumenta ainda mais o tamanho da fonte */
    }
}
Na abordagem "Desktop First", você começa criando o layout e os estilos para telas grandes (desktop) e depois usa media queries para adaptar os estilos às telas menores.
Como funciona:

    Estilo para desktop: Comece criando os estilos para dispositivos de maior largura (normalmente desktops ou laptops).
    Media Queries para telas menores: Após definir os estilos para desktop, adicione media queries para dispositivos móveis e tablets, ajustando o layout conforme necessário.

O estilo inicial é projetado para desktops, com uma largura fixa de 1200px para o conteúdo e fontes grandes.
Quando a tela tem no máximo 1024px (tablets), a largura da .container é ajustada para 900px e a fonte é reduzida.
Quando a tela é 768px ou menor (dispositivos móveis), a largura da .container ocupa 100% da tela e o padding e fonte também são ajustados.
/* Estilos para desktop (por padrão, assume-se que a tela é grande) /
body {
    font-family: Arial, sans-serif;
    padding: 40px;
    font-size: 20px;
}

.container {
    width: 1200px;  / Largura fixa para telas grandes /
    margin: 0 auto;  / Centraliza o conteúdo /
}

h1 {
    font-size: 48px;  / Tamanho de fonte grande para telas grandes /
}

/ Media Query para tablets /
@media (max-width: 1024px) {
    .container {
        width: 900px;  / Ajusta a largura para telas menores /
    }

    h1 {
        font-size: 36px;  / Reduz o tamanho da fonte /
    }
}

/ Media Query para dispositivos móveis /
@media (max-width: 768px) {
    .container {
        width: 100%;  / Faz com que a largura ocupe toda a tela /
    }

    h1 {
        font-size: 24px;  / Reduz ainda mais o tamanho da fonte /
    }

    body {
        padding: 20px;  / Diminui o padding em dispositivos móveis */
    }
}

    Conflitos de Hierarquia de Media Queries


Quando se usa ambas as abordagens, um possível conflito pode surgir entre a ordem das media queries. A ordem das regras CSS é importante: as regras definidas para telas maiores podem sobrepor as regras para telas menores, a menos que você use media queries corretamente.

    Resolução: Em "Mobile First", as media queries são adicionadas a partir de telas pequenas. As regras padrão devem ser aplicadas sem uma media query, e os estilos para telas maiores devem ser definidos usando min-width.
    Em "Desktop First", as regras padrão são para telas grandes, e as media queries devem ser usadas para dispositivos menores com max-width.

# Questão 5
Tamanho de Fontes e Layouts


O tamanho de fontes e os layouts podem precisar de ajustes dependendo da resolução da tela. Em ambos os casos, certifique-se de que os estilos definidos para uma categoria de dispositivo não quebrem o design em outra.

    Resolução: Use valores relativos como em ou rem para fontes, para que elas se ajustem de maneira mais flexível em diferentes resoluções.
Estrutura Clara para Leitores de Tela: Tags semânticas como <header>, <section>, <article>, e <nav> permitem que os leitores de tela identifiquem a estrutura da página de forma mais precisa. Isso melhora a navegação e a compreensão da página. Por exemplo, quando um leitor de tela encontra um <header>, ele pode anunciar isso para o usuário, permitindo que o conteúdo de introdução ou navegação da página seja rapidamente identificado.

    Facilidade de Navegação:
        <header>: Geralmente contém o título da página, logotipo e links de navegação importantes. Ao usar a tag <header>, você está sinalizando essa seção ao leitor de tela, tornando mais fácil para o usuário encontrar rapidamente essas informações.
        <nav>: Indica um bloco de navegação. Usar esta tag permite que leitores de tela identifiquem facilmente links de navegação em toda a página, tornando a navegação mais eficiente.
        <section>: Divide a página em seções distintas de conteúdo. Usar <section> ajuda o leitor de tela a entender a estrutura do conteúdo e facilita a navegação entre diferentes partes do site.
        <article>: Marca conteúdo autossuficiente, como postagens de blog ou notícias. Isso ajuda os leitores de tela a identificar partes do conteúdo que podem ser lidas de forma independente.

    Melhor Descrição e Interatividade: A utilização de tags semânticas também facilita a interação com elementos como links e formulários, além de garantir que cada componente seja lido de maneira clara e contextualizada.

    SEO (Otimização para Motores de Busca)


As tags semânticas também são fundamentais para o SEO. O Google e outros motores de busca usam o conteúdo semântico para entender melhor a estrutura da página e classificar o conteúdo adequadamente.
Benefícios para SEO:
Melhor Compreensão da Estrutura do Conteúdo: Tags como <header>, <section>, e <article> ajudam os motores de busca a compreenderem a hierarquia e a importância relativa do conteúdo. Por exemplo:
        O <header> é geralmente considerado uma área importante da página, com informações cruciais, como título e navegação.
        O <section> é usado para agrupar conteúdo relacionado, o que ajuda o Google a entender o que é relevante dentro de cada parte da página.
        O <article> é uma unidade de conteúdo que pode ser indexada independentemente, o que é essencial para páginas como blogs e notícias.

    Relevância das Palavras-chave: O uso de tags semânticas corretamente ajuda a organizar o conteúdo de maneira lógica e estruturada, permitindo que os motores de busca entendam melhor quais são os tópicos centrais da página. Isso pode melhorar a relevância das palavras-chave e a indexação do conteúdo.

    Aumento da Visibilidade e Classificação: Motores de busca como o Google priorizam sites que utilizam boas práticas de estruturação semântica. Isso pode resultar em uma melhor classificação nas páginas de resultados de pesquisa (SERPs), já que o conteúdo é mais fácil de ser indexado.
O uso de tags semânticas HTML5, como <header>, <section>, <article>, e <nav>, oferece uma base sólida tanto para a acessibilidade quanto para o SEO. Essas tags ajudam a criar uma estrutura mais compreensível para leitores de tela e motores de busca, tornando o conteúdo da página mais fácil de ser navegado e indexado.

Para garantir que sua estrutura seja acessível e otimizada para SEO, você pode usar ferramentas de validação de acessibilidade, testar com leitores de tela, e seguir boas práticas de SEO, como o uso correto de meta tags, links internos e títulos hierárquicos. Ao fazer isso, você melhora a experiência do usuário e a visibilidade do seu site nos motores de busca.

# Questão 6
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Botão de Alerta</title>
    <style>
        /* Centralizando o conteúdo da página */
        body {
            display: flex;
            justify-content: center; /* Centraliza horizontalmente */
            align-items: center;     /* Centraliza verticalmente */
            height: 100vh;           /* Faz o body ocupar a tela toda */
            margin: 0;  
            text-align: center;
        }

        /* Estilo do botão */
        button {
            font-size: 40px;         /* Tamanho da fonte do botão */
            padding: 20px 40px;      /* Tamanho do botão */
            background-color: #ff4d4d; /* Cor de fundo vermelha */
            color: rgb(0, 0, 0);            /* Cor do texto */
            border: none;            /* Remove a borda */
            border-radius: 10px;     /* Bordas arredondadas */
            cursor: pointer;        /* Cursor de "mãozinha" para mostrar que é clicável */
        }

        button:hover {
            background-color: #e60000; /* Cor mais escura ao passar o mouse */
        }
    </style>
</head>
<body>

    <button id="meuBotao">Não clique aqui</button>

    <script>
        // Seleciona o botão pelo ID e adiciona um evento de clique
        document.getElementById("meuBotao").addEventListener("click", function() {
            alert("Olá, mundo! Você clicou onde não deveria, HÁ!"); // Exibe o alerta
        });
    </script>

</body>
</html>

O JavaScript interage com o evento de clique no botão e, quando o botão é clicado, executa a função que exibe o alerta. Essa interação é feita de maneira eficiente e limpa usando addEventListener.

# questão 7
a 7



<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulário com Validação</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        form {
            width: 300px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
        }

        label {
            font-weight: bold;
            display: block;
            margin-top: 10px;
        }

        input, textarea {
            width: 100%;
            padding: 8px;
            margin-top: 5px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        .error {
            color: red;
            font-size: 12px;
            margin-top: 5px;
        }

        button {
            width: 100%;
            padding: 10px;
            margin-top: 15px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #218838;
        }
    </style>
</head>
<body>

    <form id="meuFormulario">
        <label for="nome">Nome:</label>
        <input type="text" id="nome">
        <div class="error" id="erroNome"></div>

        <label for="email">E-mail:</label>
        <input type="text" id="email">
        <div class="error" id="erroEmail"></div>

        <label for="mensagem">Mensagem:</label>
        <textarea id="mensagem" rows="4"></textarea>
        <div class="error" id="erroMensagem"></div>

        <button type="submit">Enviar</button>
    </form>

    <script>
        // Pegando o formulário pelo ID e adicionando um evento de envio
        document.getElementById("meuFormulario").addEventListener("submit", function(event) {
            event.preventDefault(); // Impede o envio do formulário se houver erros

            // Pegando os valores dos campos e removendo espaços extras
            let nome = document.getElementById("nome").value.trim();
            let email = document.getElementById("email").value.trim();
            let mensagem = document.getElementById("mensagem").value.trim();

            // Pegando os elementos onde vamos exibir as mensagens de erro
            let erroNome = document.getElementById("erroNome");
            let erroEmail = document.getElementById("erroEmail");
            let erroMensagem = document.getElementById("erroMensagem");

            // Resetando mensagens de erro antes da validação
            erroNome.textContent = "";
            erroEmail.textContent = "";
            erroMensagem.textContent = "";

            let valido = true;

            // Validação do nome (não pode estar vazio e deve ter pelo menos 4 caracteres)
            if (nome === "") {
                erroNome.textContent = "O nome é obrigatório.";
                valido = false;
            } else if (nome.length < 4) {
                erroNome.textContent = "O nome deve ter pelo menos 4 caracteres.";
                valido = false;
            }

            // Validação do e-mail (não pode estar vazio e deve ter formato correto)
            if (email === "") {
                erroEmail.textContent = "O e-mail é obrigatório.";
                valido = false;
            } else if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
                erroEmail.textContent = "Formato de e-mail inválido.";
                valido = false;
            }

            // Validação da mensagem (não pode estar vazia)
            if (mensagem === "") {
                erroMensagem.textContent = "A mensagem não pode estar vazia.";
                valido = false;
            }

            // Se tudo estiver válido, enviamos o formulário (simulação)
            if (valido) {
                alert("Formulário enviado com sucesso!");
                document.getElementById("meuFormulario").reset(); // Limpa o formulário
            }
        });
    </script>

</body>
</html>

O JavaScript usa document.getElementById para pegar os campos do formulário e addEventListener("submit", function) para capturar o evento de envio. O event.preventDefault() impede o envio automático para que possamos validar os dados antes.

Pegamos os valores do nome, e-mail e mensagem com .value.trim(), removendo espaços extras. Criamos variáveis para exibir mensagens de erro e limpamos essas mensagens antes da validação.

A validação verifica se os campos estão vazios. No nome, exigimos pelo menos 4 caracteres. No e-mail, usamos uma expressão regular para validar o formato (exemplo@dominio.com). Se houver erro, exibimos mensagens e impedimos o envio.

Se todos os campos estiverem corretos, mostramos "Formulário enviado com sucesso!" com alert() e limpamos o formulário com reset(). Isso garante que os dados sejam enviados somente se estiverem válidos.


# questão 8 

<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SPA Simples</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        #container { margin-top: 20px; padding: 20px; border: 1px solid #ccc; }
        button { margin: 5px; padding: 10px; font-size: 16px; }
    </style>
</head>
<body>

    <h1>Minha SPA Simples</h1>
    <button onclick="mudarConteudo('home')">Home</button>
    <button onclick="mudarConteudo('sobre')">Sobre</button>
    <button onclick="mudarConteudo('contato')">Contato</button>

    <div id="container">
        <p>Bem-vindo! Escolha uma opção acima.</p>
    </div>

    <script>
        function mudarConteudo(pagina) {
            let container = document.getElementById("container");
            if (pagina === "home") {
                container.innerHTML = "<h2>Página Inicial</h2><p>Bem-vindo à nossa aplicação!</p>";
            } else if (pagina === "sobre") {
                container.innerHTML = "<h2>Sobre Nós</h2><p>Somos uma empresa inovadora...</p>";
            } else if (pagina === "contato") {
                container.innerHTML = "<h2>Contato</h2><p>Envie um e-mail para contato@exemplo.com</p>";
            }
        }
    </script>

</body>
</html>

# questão 9
A History API permite modificar a URL sem recarregar a página, essencial para SPAs.

pushState(state, title, url) → Adiciona uma nova entrada no histórico e altera a URL.
replaceState(state, title, url) → Substitui a entrada atual do histórico, sem adicionar uma nova.
window.onpopstate → Detecta quando o usuário usa "Voltar" ou "Avançar" no navegador.
Um sistema de rotas simples pode usar pushState() para mudar a URL e atualizar o conteúdo dinamicamente. O onpopstate garante que o conteúdo certo seja exibido ao voltar no histórico.

Compatibilidade: Navegadores antigos (ex.: IE9) não suportam pushState().
Fallback: Usar location.hash (#home, #sobre) para simular rotas.

Isso permite navegação fluida sem recarregar a página!

usei esse codigo 
<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SPA com History API</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        #container { margin-top: 20px; padding: 20px; border: 1px solid #ccc; }
        button { margin: 5px; padding: 10px; font-size: 16px; cursor: pointer; }
    </style>
</head>
<body>

    <h1>SPA com History API</h1>
    <button onclick="navegarPara('home')">Home</button>
    <button onclick="navegarPara('sobre')">Sobre</button>
    <button onclick="navegarPara('contato')">Contato</button>

    <div id="container">
        <h2>Bem-vindo!</h2>
        <p>Escolha uma opção acima.</p>
    </div>

    <script>
        function navegarPara(pagina) {
            let container = document.getElementById("container");

            // Atualiza o conteúdo da página dinamicamente
            if (pagina === "home") {
                container.innerHTML = "<h2>Página Inicial</h2><p>Bem-vindo à nossa aplicação!</p>";
            } else if (pagina === "sobre") {
                container.innerHTML = "<h2>Sobre Nós</h2><p>Somos uma empresa inovadora...</p>";
            } else if (pagina === "contato") {
                container.innerHTML = "<h2>Contato</h2><p>Envie um e-mail para contato@exemplo.com</p>";
            }

            // Atualiza a URL sem recarregar a página
            history.pushState({ pagina }, "", `/${pagina}`);
        }

        // Detecta quando o usuário volta no histórico
        window.onpopstate = function(event) {
            if (event.state && event.state.pagina) {
                navegarPara(event.state.pagina);
            }
        };
    </script>

</body>
</html>

# questão 10

10 Para otimizar o desempenho de uma SPA, você pode usar as técnicas de code splitting, lazy loading e módulos JavaScript nativos.

Code Splitting: Divide o código JavaScript em módulos menores, carregando apenas o que é necessário inicialmente, melhorando o tempo de carregamento inicial.
Lazy Loading: Carrega módulos e recursos apenas quando o usuário interage com a página ou função que os exige, economizando largura de banda e tempo de carregamento.
Módulos ES: Utiliza a funcionalidade nativa de módulos do JavaScript, permitindo importar e carregar apenas o código necessário de forma eficiente.
Essas técnicas funcionam em conjunto para reduzir o código carregado no início da aplicação e otimizar o tempo de resposta. O code splitting e lazy loading evitam que o código seja carregado de uma vez, enquanto os módulos ES organizam e carregam o código de forma assíncrona e eficiente. Como resultado, o tempo de carregamento é significativamente reduzido e a performance da aplicação é melhorada.

Essas abordagens garantem uma navegação mais fluida e um carregamento mais rápido, oferecendo uma experiência superior ao usuário.

#questão 11
*questão 11*
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Data e Hora Atual</title>
    </head>
    <body>
        <h1>Data e Hora Atual</h1>
        <p>Hora atual: <span id="horaAtual"></span></p>

<script>
    function exibirHora(){
        const data= new Date();
        const hora= data.toLocaleTimeString();
        document.getElementById('horaAtual').textContent=hora;
    }
    setInterval(exibirHora,1000);
</script>

    </body>
</html>

# questão 12

*questão 12*
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Menu Dropdown</title>
        <style>
            ul{
                list-style-type: none;
                padding: 0;
                margin: 0;
            }

            li {
                display: inline-block;
                position: relative;
            }
            ul.submenu {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                background-color: @f0f0f0;
                padding: 10px;
                border: 1px solid #ccc;
            }
li.active> ul.submenu{
    display: block;
}

li.hover >ul.submenu{
    display: block;
}

        </style>
    </head>
    <body>
        <h1>Menu Dropdown</h1>

        <ul>
<li id="menu1">
Menu Principal
<ul class="submenu">
<li>Subitem 1</li>
<li>Subitem 2</li>
<li>Subitem 3</li>
</ul>
</li>

        </ul>
<script>
    function detectTouchEvent(){
        if('ontouchstart' in window ||navigator.maxTouchPoints) {
            document.body.classList.add('touch');
            document.body.classList.remove('mouse');
        } else{
            document.body.classList.add('mouse');
            document.body.classList.remove('touch');
        }
    }
    detectTouchEvent();
const menuItem =document.getElementById('menu1');
if (document.body.classList.contains('touch')){
    menuItem.addEventListener('touchstart', function(){
        this.classList.toggle('active');
    });
}

if (document.body.classList.contains('mouse')){
    menuItem.addEventListener('mouseover', function() {
        this.classList.add('hover');
    });
    menuItem.addEventListener('mouseout',function(){
        this.classList.remove('hover');
    });
}

</script>

    </body>
</html>

# questão 13
*questão 13*
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Consumindo API com Fetch</title>
</head>
<body>
    <h1>Dados da API</h1>
    <div id="dados"></div>
    <div id="erro" style="color: red; display: none;"></div>

    <script>
        
        async function consumirAPI() {
            const url = 'https://jsonplaceholder.typicode.com/users'; // URL da API (exemplo)

            try {
                
                const resposta = await fetch(url);
                
                
                if (!resposta.ok) {
                    throw new Error(`Erro na requisição: ${resposta.status}`);
                }

               
                const dados = await resposta.json();
                
                
                exibirDados(dados);

            } catch (erro) {
                
                console.error('Erro:', erro);
                exibirErro(erro.message);
            }
        }

        
        function exibirDados(dados) {
            const container = document.getElementById('dados');
            container.innerHTML = ''; 

            dados.forEach(item => {
                const div = document.createElement('div');
                div.textContent = `${item.name} - ${item.email}`;
                container.appendChild(div);
            });
        }

        
        function exibirErro(mensagem) {
            const containerErro = document.getElementById('erro');
            containerErro.style.display = 'block';
            containerErro.textContent = `Erro ao carregar os dados: ${mensagem}`;
        }

        
        consumirAPI();
    </script>
</body>
</html>

Para usar a API d͏e modo simples, eu começaria criando uma funç͏ã͏o que u͏sa ͏o fet͏ch para pegar os dados da API. Esta f͏unç͏ão faria a ped͏ido e͏ esperaria ͏pela respos͏ta com await. Depois de pegar a resposta, ͏checava se o ͏status da pedido é 200 (bom). Se for, transformava ͏a re͏sposta em͏ JSON com . json(). Uma vez que os dados estavam prontos e͏u usaria ͏eles para mudar ͏o DOM, ajusta͏ndo os itens͏ necessários para mostrar as inf͏orma͏ções ao͏ usuário. Se não, se͏ houve ͏um erro na soli͏cita͏ção ou no fo͏rmat͏o do JSON eu pegaria esses problemas usando u͏m bloco try/catch. No caso ͏de erros de rede͏ poderia mostrar uma mensage͏m amigáve͏l ao usuário dizendo ͏q͏ue teve um problema de conexão. Para erros de format͏o do JSON uma men͏sagem erro também seria mostrada indica͏ndo que os dados não puderam se͏r processados certo. Dessa for͏ma a experiência dos usuár͏ios seria mais f͏irme com o tratamento certo para falhas

# questão 14

*questão 14*
O localStorage e ͏o sessionStorage são f͏ormas fáceis de guardar dados que ͏usam chave e v͏a͏lor, mas tem algumas diferenças. O loca͏lStora͏ge pode guardar mais ͏informação, até 5MB por site, enquanto͏ o sessionStorage também aguenta essa quantidad͏e, por͏ém os d͏ado͏s somem͏ q͏uando͏ você fecha a a͏ba do navegador. Ambos gu͏ardam as informações de modo durável ͏(c͏omo no caso do loc͏alStorage) ou tempo͏rá͏r͏i͏o (co͏mo no session͏Stor͏age), e não têm uma estrutura ͏compli͏cada. Já o IndexedDB é u͏ma solução maior e flexível, perm͏itindo s͏alvar grandes quantidade͏s de͏ dados (em gigabytes) com formato NoSQL, tendo suporte para índice͏s e bus͏cas ͏mais difíceis. 
Os dados no IndexedDB são duráveis e podem ser usados para mant͏er grandes quantidades de informações estruturadas ͏c͏omo arquivos ou ͏regist͏ros dos usuários. O localStorage e o sessionStorage são mais adequados para armazenar pequenas quantidades de dados temporários ou persistentes, como preferências do usuário, enquanto o IndexedDB é ideal para aplicações que precisam de maior capacidade de armazenamento e consultas mais complexas, como em sistemas de gerenciamento de dados offline ou armazenamentos de grande escala.

# questão 15
Para setar um S͏ervice Worker em uma app SP͏A, você deve reg͏istrar ele no JavaScrip͏t principal e usar o evento de instal͏ação p͏ara guardar em cache arquivos fixos (HTML, CSS, JS, imagens). No evento busca você intercepta ͏as pedidos para dar os arquivos do cache quando não tem conexão, assegurando uma vivência off͏line. Para͏ atualizar o cache com nova͏s versões dos ar͏quivos o event͏o͏ ativar dev͏e ser usado ͏para tirar fora os caches velhos e guardar os novos. O ma͏nifesto PWA define a vivência de instalar do app especificando͏ campos importantes como n͏ome, start_url, ícones display͏ e background_color permitindo que o a͏pp fusse͏ instalado no aparelho do usuário e trabalhar offline similar a u͏m app nativo.
