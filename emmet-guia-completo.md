# Guia Completo do Emmet - Zen Coding

## O que é Emmet?
Emmet é uma ferramenta que permite escrever HTML e CSS de forma muito mais rápida usando abreviações. É integrado nativamente no VS Code.

## Como usar no VS Code
1. Digite a abreviação Emmet
2. Pressione **Tab** ou **Ctrl + Space** para expandir
3. Ou use **Ctrl + Shift + P** → "Emmet: Expand Abbreviation"

---

## 🔤 SÍMBOLOS PRINCIPAIS

### `>` - Elemento Filho (Child)
```
div>ul>li
```
**Resultado:**
```html
<div>
    <ul>
        <li></li>
    </ul>
</div>
```

### `+` - Elemento Irmão (Sibling)
```
div+p+bq
```
**Resultado:**
```html
<div></div>
<p></p>
<blockquote></blockquote>
```

### `^` - Subir um Nível (Climb-up)
```
div+div>p>span+em^bq
```
**Resultado:**
```html
<div></div>
<div>
    <p><span></span><em></em></p>
    <blockquote></blockquote>
</div>
```

### `*` - Multiplicação
```
ul>li*5
```
**Resultado:**
```html
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

### `()` - Agrupamento
```
div>(header>ul>li*2>a)+footer>p
```
**Resultado:**
```html
<div>
    <header>
        <ul>
            <li><a href=""></a></li>
            <li><a href=""></a></li>
        </ul>
    </header>
    <footer>
        <p></p>
    </footer>
</div>
```

---

## 🎯 ATRIBUTOS

### `.` - Classes CSS
```
div.container
p.text.highlight
```
**Resultado:**
```html
<div class="container"></div>
<p class="text highlight"></p>
```

### `#` - ID
```
div#header
form#contact.form
```
**Resultado:**
```html
<div id="header"></div>
<form id="contact" class="form"></form>
```

### `[]` - Atributos Customizados
```
td[title="Hello world!" colspan=3]
a[href="https://google.com" target="_blank"]
```
**Resultado:**
```html
<td title="Hello world!" colspan="3"></td>
<a href="https://google.com" target="_blank"></a>
```

### `{}` - Texto
```
a{Clique aqui}
p{Lorem ipsum}+a{link}
```
**Resultado:**
```html
<a href="">Clique aqui</a>
<p>Lorem ipsum</p><a href="">link</a>
```

---

## 🔢 NUMERAÇÃO

### `$` - Numeração
```
ul>li.item$*5
```
**Resultado:**
```html
<ul>
    <li class="item1"></li>
    <li class="item2"></li>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
</ul>
```

### `$$` - Numeração com Zeros à Esquerda
```
ul>li.item$$*3
```
**Resultado:**
```html
<ul>
    <li class="item01"></li>
    <li class="item02"></li>
    <li class="item03"></li>
</ul>
```

### `$@-` - Numeração Reversa
```
ul>li.item$@-*3
```
**Resultado:**
```html
<ul>
    <li class="item3"></li>
    <li class="item2"></li>
    <li class="item1"></li>
</ul>
```

### `$@3` - Começar de um Número Específico
```
ul>li.item$@3*3
```
**Resultado:**
```html
<ul>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
</ul>
```

---

## 📝 EXEMPLOS PRÁTICOS

### 1. Estrutura HTML Básica
```
html:5
```
ou
```
!
```
**Resultado:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

### 2. Menu de Navegação
```
nav.navbar>ul.nav-list>li.nav-item*4>a.nav-link{Item $}
```
**Resultado:**
```html
<nav class="navbar">
    <ul class="nav-list">
        <li class="nav-item"><a href="" class="nav-link">Item 1</a></li>
        <li class="nav-item"><a href="" class="nav-link">Item 2</a></li>
        <li class="nav-item"><a href="" class="nav-link">Item 3</a></li>
        <li class="nav-item"><a href="" class="nav-link">Item 4</a></li>
    </ul>
</nav>
```

### 3. Card Component
```
.card>.card-header>h3.card-title{Título}^.card-body>p.card-text{Conteúdo}^.card-footer>button.btn{Botão}
```
**Resultado:**
```html
<div class="card">
    <div class="card-header">
        <h3 class="card-title">Título</h3>
    </div>
    <div class="card-body">
        <p class="card-text">Conteúdo</p>
    </div>
    <div class="card-footer">
        <button class="btn">Botão</button>
    </div>
</div>
```

### 4. Grid de Cards
```
.container>.row>.col*3>.card>.card-body>h5.card-title{Card $}+p.card-text{Descrição do card $}+a.btn{Ver mais}
```

### 5. Formulário
```
form.contact-form>(.form-group>label{Nome}+input[type=text name=nome id=nome])+(.form-group>label{Email}+input[type=email name=email id=email])+(.form-group>label{Mensagem}+textarea[name=mensagem id=mensagem rows=5])+button[type=submit].btn{Enviar}
```

### 6. Tabela
```
table.table>thead>tr>th*4{Coluna $}^^tbody>tr*3>td*4{Dados $}
```

---

## 🎨 EMMET PARA CSS

### Propriedades Abreviadas
```
m10        → margin: 10px;
p5         → padding: 5px;
w100       → width: 100px;
h50        → height: 50px;
bg#fff     → background: #fff;
c#000      → color: #000;
fz16       → font-size: 16px;
fw700      → font-weight: 700;
ta-c       → text-align: center;
d-f        → display: flex;
jc-c       → justify-content: center;
ai-c       → align-items: center;
pos-r      → position: relative;
pos-a      → position: absolute;
bd1        → border: 1px;
bdr5       → border-radius: 5px;
lh1.5      → line-height: 1.5;
op0.5      → opacity: 0.5;
z10        → z-index: 10;
```

### Valores com Unidades
```
w100p      → width: 100%;
h100vh     → height: 100vh;
m10px      → margin: 10px;
p1em       → padding: 1em;
fz1.2rem   → font-size: 1.2rem;
```

---

## ⌨️ ATALHOS DO VS CODE

### Atalhos Principais
- **Tab** - Expandir abreviação
- **Ctrl + Space** - Sugestões do Emmet
- **Ctrl + Shift + P** → "Emmet: Expand Abbreviation"
- **Ctrl + Shift + P** → "Emmet: Wrap with Abbreviation"

### Comandos Úteis
1. **Emmet: Expand Abbreviation** - Expande a abreviação
2. **Emmet: Wrap with Abbreviation** - Envolve seleção com HTML
3. **Emmet: Remove Tag** - Remove tag mantendo conteúdo
4. **Emmet: Update Tag** - Atualiza nome da tag
5. **Emmet: Balance Outward** - Seleciona tag pai
6. **Emmet: Balance Inward** - Seleciona conteúdo da tag
7. **Emmet: Go to Matching Tag** - Vai para tag correspondente

### Configurações do VS Code
```json
{
    "emmet.includeLanguages": {
        "javascript": "javascriptreact",
        "typescript": "typescriptreact"
    },
    "emmet.triggerExpansionOnTab": true,
    "emmet.showExpandedAbbreviation": "always"
}
```

---

## 🚀 EXEMPLOS AVANÇADOS

### Estrutura Completa de Página
```
html:5>head>title{Minha Página}^body>header.header>nav.navbar>ul.nav-list>li.nav-item*4>a[href=#]{Menu $}^^^main.main>section.hero>h1{Título Principal}+p{Subtítulo}^section.content>.container>.row>.col*3>.card>.card-body>h3{Card $}+p{Descrição}+a.btn{Saiba mais}^^^^footer.footer>p{© 2024 Meu Site}
```

### Layout Flexbox
```
.container.flex>.sidebar>.nav>ul>li*5>a{Link $}^^.main-content>.header>h1{Título}^.content>article*3>h2{Artigo $}+p{Conteúdo do artigo}
```

### Grid CSS
```
.grid-container>.grid-item*9{Item $}
```
Com CSS:
```css
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

---

## 💡 DICAS PROFISSIONAIS

1. **Use parênteses** para agrupar elementos complexos
2. **Combine com CSS Grid/Flexbox** para layouts modernos
3. **Use numeração** para criar elementos repetitivos
4. **Pratique diariamente** - comece com estruturas simples
5. **Configure bem o VS Code** para melhor experiência
6. **Use em React/Vue** também funciona!

---

## 🔗 RECURSOS ADICIONAIS

- [Emmet Documentation](https://docs.emmet.io/)
- [Emmet Cheat Sheet](https://docs.emmet.io/cheat-sheet/)
- [VS Code Emmet](https://code.visualstudio.com/docs/editor/emmet)

---

**Dica Final:** Pratique um pouco todo dia! Comece com estruturas simples e vá aumentando a complexidade. Em pouco tempo você estará escrevendo HTML 10x mais rápido! 🚀
