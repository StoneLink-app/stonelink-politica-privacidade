Olá\! Como StoneLink Architect, preparei a versão do manual da marca com exemplos práticos de como aplicar sua identidade visual usando HTML e CSS.

A abordagem a seguir utiliza **CSS Custom Properties (variáveis)**, que é uma prática moderna e altamente recomendada. Ela permite definir sua paleta de cores e fontes em um único lugar, facilitando a manutenção e a implementação de temas, como o modo claro e escuro.

-----

# Manual da Marca Stonelink (Exemplos em HTML/CSS)

Este guia define os padrões visuais da marca e demonstra como aplicá-los em um ambiente web.

## 1\. Logotipo

Os arquivos de logotipo de referência são:

  * `LOGO plano sem fundo - 01.png`
  * `LOGO plano sem fundo - 02.png`
  * `Logotipos.pdf`

## 2\. Paleta de Cores

As cores da marca são baseadas em tons de verde e cinza, remetendo a rochas e natureza.

### Cores Primárias e de Destaque

| Cor | Hexadecimal |
| :--- | :--- |
| **Verde Principal** | `#5CA997` |
| **Azul** | `#2964C2` |
| **Vermelho (Erro)**| `#FF2C2F` |

### Cores Neutras

| Cor | Hexadecimal |
| :--- | :--- |
| **Branco** | `#FFFFFF` |
| **Cinza Claro** | `#E8E8E8` |
| **Cinza Médio** | `#D2D2D2` |
| **Cinza Escuro 1** | `#4C4C4C` |
| **Cinza Escuro 2** | `#333333` |
| **Preto** | `#000000` |

## 3\. Tipografia

  * **Fonte Principal:** SF Pro Display / Kohinoor Bangla.
  * **Hierarquia de Texto:**

| Uso Semântico | Tag HTML | Tamanho | Peso (Weight) |
| :--- | :--- | :--- | :--- |
| Título Principal | `<h1>` | 37px | Bold (700) |
| Título Secundário | `<h2>` | 25px | Bold (700) |
| Título de Seção | `<h3>` | 16px | Bold (700) |
| Título de Card | `<h4>` | 14px | Medium (500) |
| Corpo de Texto | `<p>` | 14px | Regular (400) |

-----

## 4\. Aplicação com HTML e CSS

Abaixo está um arquivo HTML completo (`exemplo.html`) que demonstra como estruturar seu CSS para aplicar a identidade visual da marca, incluindo o suporte automático para modo claro e escuro.

### Exemplo de Código (`exemplo.html`)

Copie e cole este código em um arquivo `exemplo.html` e abra-o em um navegador para ver o resultado.

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exemplo de Manual de Marca - Stonelink</title>
    <style>
        /* * ARQUITETURA DO CSS
         * 1. Definição de variáveis de tema (cores, fontes) para o Modo Claro.
         * 2. Sobrescrita das variáveis de cores para o Modo Escuro.
         * 3. Estilos globais e de componentes usando essas variáveis.
        */

        :root {
            /* -- Paleta de Cores (Modo Claro) -- */
            --cor-primaria: #5CA997;
            --cor-secundaria: #2964C2;
            --cor-erro: #FF2C2F;
            --cor-fundo: #FFFFFF;
            --cor-superficie: #F7F7F7; /* Um cinza muito claro para cards */
            --cor-texto-principal: #000000;
            --cor-texto-secundario: #4C4C4C;
            --cor-borda: #E8E8E8;
            --cor-texto-em-primaria: #FFFFFF;
            
            /* -- Tipografia -- */
            --fonte-principal: "SF Pro Display", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        /* Sobrescreve as variáveis de cor quando o sistema do usuário está em modo escuro */
        @media (prefers-color-scheme: dark) {
            :root {
                --cor-fundo: #333333;
                --cor-superficie: #4C4C4C;
                --cor-texto-principal: #FFFFFF;
                --cor-texto-secundario: #D2D2D2;
                --cor-borda: #5b5b5b;
            }
        }

        /* --- Estilos Globais --- */
        body {
            background-color: var(--cor-fundo);
            color: var(--cor-texto-principal);
            font-family: var(--fonte-principal);
            line-height: 1.6;
            margin: 0;
            padding: 2rem;
            transition: background-color 0.3s, color 0.3s;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
        }

        /* --- Estilos de Tipografia --- */
        h1 { font-size: 37px; font-weight: 700; color: var(--cor-primaria); }
        h2 { font-size: 25px; font-weight: 700; }
        h3 { font-size: 16px; font-weight: 700; }
        h4 { font-size: 14px; font-weight: 500; }
        p { font-size: 14px; font-weight: 400; color: var(--cor-texto-secundario); }
        .texto-principal { color: var(--cor-texto-principal); }

        /* --- Estilos de Componentes --- */
        .card {
            background-color: var(--cor-superficie);
            border: 1px solid var(--cor-borda);
            border-radius: 8px;
            padding: 1.5rem;
            margin-top: 2rem;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            transition: background-color 0.3s, border-color 0.3s;
        }

        .button {
            display: inline-block;
            border: none;
            border-radius: 8px;
            padding: 12px 24px;
            font-size: 16px;
            font-weight: 700;
            cursor: pointer;
            text-decoration: none;
            transition: opacity 0.2s;
        }
        .button:hover {
            opacity: 0.85;
        }

        .button-primary {
            background-color: var(--cor-primaria);
            color: var(--cor-texto-em-primaria);
        }
        
        .button-secondary {
            background-color: transparent;
            color: var(--cor-primaria);
            border: 2px solid var(--cor-primaria);
        }
        
        .error-text {
            color: var(--cor-erro);
            font-size: 12px;
            font-weight: 500;
        }

    </style>
</head>
<body>

    <div class="container">
        <h1>Título Principal (H1)</h1>
        <p>Este é um parágrafo de corpo de texto padrão, descrevendo o conteúdo da página ou seção.</p>

        <h2>Título Secundário (H2)</h2>
        <p class="texto-principal">Este parágrafo usa a cor de texto principal, para dar mais destaque que o texto secundário padrão.</p>
        
        <div class="card">
            <h3>Título de Seção (H3) dentro de um Card</h3>
            <h4>Subtítulo ou Título de Item (H4)</h4>
            <p>Conteúdo dentro de um card, que usa a cor de superfície. Ele se adapta automaticamente ao modo claro ou escuro.</p>
            <p class="error-text">Esta é uma mensagem de erro.</p>
        </div>
        
        <div style="margin-top: 2rem;">
            <a href="#" class="button button-primary">Botão Primário</a>
            <a href="#" class="button button-secondary" style="margin-left: 1rem;">Botão Secundário</a>
        </div>
    </div>

</body>
</html>
```

### Como Usar

1.  **Salvar o Arquivo:** Salve o código acima como `index.html`.
2.  **Hospedar:** Faça o upload deste arquivo para o seu repositório do GitHub Pages (`stonelink-politica-privacidade`) ou para o Firebase Hosting.
3.  **Testar:** Abra a URL gerada no seu navegador. Tente alternar o modo de aparência do seu sistema operacional (de claro para escuro) e veja a página se adaptar automaticamente.

Este arquivo serve como um excelente "guia vivo" para qualquer desenvolvedor web que precise implementar a identidade visual da Stonelink.