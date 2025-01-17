# Documentação do Projeto RetroDiscos
 
## HTML

### Estrutura do Documento HTML

- O documento HTML é estruturado de acordo com as melhores práticas para web moderna, utilizando elementos semânticos.

- Utiliza-se cabeçalho (`<header>`), seções (`<section>`), e rodapé (`<footer>`) para organização do conteúdo.
 
### Meta Tags e Charset

- Utilização das meta tags `<meta charset="UTF-8">` para definir o conjunto de caracteres e `<meta name="viewport" content="width=device-width, initial-scale=1.0">` para configuração da escala inicial em dispositivos móveis.
 
### Estilização Inline

- Uso mínimo de estilização inline, por exemplo, para manter a cor do link do logo no cabeçalho.
 
### Links Externos

- Inclusão de link externo para a fonte 'Cinzel' do Google Fonts.
 
### Seções

- Utilização de seções `<section>` com IDs para navegação interna e ancoragem (`#inicio`, `#galeria`, `#sobre`, `#contato`).
 
### Grid de Produtos

- Os produtos na seção de galeria são organizados em uma grade (`<div class="grid">`) com itens representando discos de vinil.
 
### Interatividade

- Implementação de botões 'Adicionar ao Carrinho' com eventos JavaScript (`<button class="add-to-cart">`) em cada item da galeria.
 
## CSS
 
### Reset CSS

- Utilização de um reset CSS básico para normalizar o estilo dos elementos.
 
### Estilização Global

- Definição de estilos globais para elementos como `<body>`, `<header>`, `<nav>`, `<ul>`, `<li>`, entre outros, utilizando um esquema de cores coerente e tipografia consistente.
 
### Responsividade

- Design responsivo com uso de media queries não explicitamente mostradas no código fornecido, mas pressuposta pela estrutura e pelo uso de `width: 100%` no cabeçalho fixo.
 
### Animações e Efeitos

- Uso de transições (`transition`) para efeitos de hover nos links do cabeçalho e nos botões 'Adicionar ao Carrinho'.

- Efeito de sombra (`box-shadow`) e transformação (`transform`) nos itens da galeria ao passar o mouse.
 
## JavaScript
 
### Manipulação do DOM

- Uso do evento `DOMContentLoaded` para garantir que o JavaScript seja executado após o carregamento completo da página.

- Seleção de elementos e manipulação do conteúdo do carrinho de compras através da contagem de itens adicionados.
 
### Interatividade

- Implementação de um evento de clique nos botões 'Adicionar ao Carrinho' para incrementar a contagem no ícone do carrinho e exibir um alerta com o nome do disco adicionado.
 
### Boas Práticas

- Utilização de `event.preventDefault()` para evitar o comportamento padrão dos botões de formulário.


#### CODIGO EM HTML 
  
  - Foi usado Css e Java Script para a pagina inicial do site aqui vão os codigos em partes separadas:

```<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sepultura - Arise (1991)</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Cinzel', serif;
            color: #333;
            line-height: 1.6;
            background: #f7f7f7;
        }

        header {
            background: #8106d3c7;
            color: #000000;
            padding: 20px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        header .logo {
            font-size: 28px;
            font-weight: bold;
            margin-left: 20px;
        }

        header nav ul {
            list-style: none;
            display: flex;
        }

        header nav ul li {
            margin: 0 20px;
        }

        header nav ul li a {
            color: #fff;
            text-decoration: none;
            font-size: 18px;
            transition: color 0.3s;
        }

        header nav ul li a:hover {
            color: #f39c12;
        }

        header .cart {
            display: flex;
            align-items: center;
            margin-right: 20px;
        }

        header .cart img {
            width: 24px;
            height: 24px;
        }

        header .cart-count {
            background: #000000;
            border-radius: 50%;
            padding: 5px 10px;
            color: #fff;
            margin-left: 10px;
            font-weight: bold;
        }

        .content {
            padding: 100px 20px; /* Add padding to account for fixed header */
            text-align: center;
        }

        .content img {
            width: 100%;
            max-width: 400px;
            height: auto;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }

        .content h1 {
            font-size: 32px;
            margin-bottom: 20px;
        }

        .content p {
            font-size: 18px;
            margin-bottom: 20px;
        }

        .content .price {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 20px;
        }

        .content .add-to-cart {
            background: #f39c12;
            border: none;
            color: #fff;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .content .add-to-cart:hover {
            background: #e67e22;
        }

        footer {
            background: #222;
            color: #fff;
            text-align: center;
            padding: 20px 0;
            position: relative;
            bottom: 0;
            width: 100%;
        }

        .social-media {
            margin: 20px 0;
        }

        .social-media a {
            color: #fff;
            text-decoration: none;
            font-size: 24px;
            margin: 0 10px;
            transition: color 0.3s;
        }

        .social-media a:hover {
            color: #ffee00;
        }
    </style>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const cartCount = document.querySelector('.cart-count');
            const addToCartButton = document.querySelector('.add-to-cart');
            
            addToCartButton.addEventListener('click', (event) => {
                event.preventDefault();
                const currentCount = parseInt(cartCount.textContent);
                cartCount.textContent = currentCount + 1;
                alert('"Sepultura - Arise (1991)" foi adicionado ao carrinho!');
            });
        });
    </script>
</head>
<body>
    <header>
        <div class="logo"><a href="site.html" style="color: inherit; text-decoration: none;">RetroDiscos</a></div>
        <nav>
            <ul>
                <li><a href="site.html#inicio">Início</a></li>
                <li><a href="site.html#sobre">Sobre</a></li>
                <li><a href="site.html#galeria">Galeria</a></li>
                <li><a href="site.html#contato">Contato</a></li>
            </ul>
            <div class="cart">
                <img src="imagens/carrinho-removebg-preview.png" alt="Carrinho de Compras">
                <span class="cart-count">0</span>
            </div>
        </nav>
    </header>
    <div class="content">
        <img src="imagens/sepultura.jpg" alt="Sepultura - Arise (1991)">
        <h1>Sepultura - Arise (1991)</h1>
        <p>"Arise" é o quarto álbum de estúdio da banda brasileira de heavy metal Sepultura, lançado em 1991. Este álbum é conhecido por sua mistura de thrash metal com influências de música brasileira, trazendo faixas como "Arise", "Dead Embryonic Cells" e "Under Siege (Regnum Irae)".</p>
        <p class="price">R$ 80,00</p>
        <button class="add-to-cart">Adicionar ao Carrinho</button>
    </div>
    <footer>
        <div class="social-media">
            <a href="https://www.facebook.com" target="_blank">Facebook</a>
            <a href="https://www.instagram.com" target="_blank">Instagram</a>
            <a href="https://x.com/home" target="_blank">Twitter</a>
            <a href="https://www.youtube.com" target="_blank">YouTube</a>
        </div>
        <p>&copy; 2024 RetroDiscos. Design By Rafael Damasceno.</p>
    </footer>
</body>
</html>
````

### Codigo em CSS: 

















### Codigo em JavaScript: 

````document.addEventListener('DOMContentLoaded', () => {
    const cartCount = document.querySelector('.cart-count');
    const addToCartButtons = document.querySelectorAll('.add-to-cart');

    addToCartButtons.forEach(button => {
        button.addEventListener('click', (event) => {
            event.preventDefault();
            const currentCount = parseInt(cartCount.textContent);
            cartCount.textContent = currentCount + 1;
            alert(`"${button.getAttribute('data-disco')}" foi adicionado ao carrinho!`);
        });
    });
});
````


 
 