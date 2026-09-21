# Desgn-Menu-CEF-Live-Russia
<div align="center">

# 🎮 Design Menu CEF  Live Russia

### Interfaces modernas em HTML, CSS e JavaScript para integração com CEF/WebView

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-orange?style=for-the-badge)
![HTML5](https://img.shields.io/badge/HTML5-interface-E34F26?style=for-the-badge\&logo=html5\&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-vanilla-F7DF1E?style=for-the-badge\&logo=javascript\&logoColor=black)
![CEF](https://img.shields.io/badge/CEF-WebView-4285F4?style=for-the-badge\&logo=googlechrome\&logoColor=white)
![Live Russia](https://img.shields.io/badge/Live%20Russia-UI-red?style=for-the-badge)

<br>

**Interfaces CEF modernas, leves e preparadas para comunicação direta entre o jogo e o frontend.**

[📂 Arquivos](#-estrutura-do-projeto) •
[✨ Recursos](#-principais-recursos) •
[🔌 Integração CEF](#-integração-com-cef) •
[🚀 Como testar](#-como-testar) •
[🗺️ Roadmap](#️-roadmap)

</div>

---

## 📖 Sobre o projeto

O **Design Menu CEF — Live Russia** é um projeto voltado para criação e prototipagem de interfaces modernas utilizando **HTML, CSS e JavaScript**, com estrutura preparada para funcionamento dentro de ambientes **CEF/WebView**.

O objetivo é substituir menus tradicionais por interfaces mais completas, organizadas e visualmente modernas, mantendo uma comunicação simples entre o frontend e os sistemas do servidor.

O projeto atualmente contém interfaces para:

* 🎒 Sistema de acessórios;
* 🏠 Compra e gerenciamento de imóveis;
* 🔨 Leilão de propriedades;
* 🏦 Imóveis vinculados à CEF;
* 💳 Pagamentos utilizando dinheiro ou saldo bancário;
* 🔌 Comunicação entre interface e servidor através de eventos CEF.

---

# ✨ Principais recursos

## 🎨 Interface moderna

Os menus utilizam um estilo inspirado em interfaces modernas de jogos:

* Design em estilo **glass / dark UI**;
* Cards modernos;
* Barra lateral de navegação;
* Painéis de detalhes;
* Toasts de confirmação;
* Estados visuais de sucesso e erro;
* Botões destacados;
* Interface limpa e organizada;
* Layout otimizado para uso dentro do jogo.

---

## 📱 Interface adaptável

O projeto utiliza unidades responsivas e dimensionamento automático para funcionar em diferentes resoluções.

A interface foi construída pensando principalmente em:

* Desktop;
* resoluções utilizadas pelo jogo;
* CEF;
* WebView;
* telas em formato horizontal/paisagem.

---

## ⚡ Sem frameworks pesados

Os menus são construídos utilizando:

```text
HTML5
CSS3
JavaScript Vanilla
SVG
CEF API
```

Não é necessário utilizar:

```text
React
Vue
Bootstrap
jQuery
Tailwind
Node.js
```

Isso ajuda a manter a interface leve para execução dentro do jogo.

---

## 📦 Arquivo único

Cada menu utiliza sua própria estrutura HTML contendo:

```text
HTML
CSS
JavaScript
SVG
```

no mesmo arquivo.

Isso facilita:

* implantação;
* testes;
* transporte do projeto;
* manutenção;
* integração com CEF.

---

# 📂 Estrutura do projeto

```text
Desgn-Menu-CEF-Live-Russia/
│
├── README.md
│
├── acs-menu.html
│   └── Menu de acessórios
│
└── menu-leilao.html
    └── Sistema de imóveis / vendas / leilões / CEF
```

---

# 🎒 Menu de Acessórios

Arquivo:

```text
acs-menu.html
```

Interface destinada à visualização, seleção e compra de acessórios.

## Categorias disponíveis

O protótipo possui suporte para categorias como:

```text
Cabeça
Rosto
Costas
Pulso
Pescoço
```

E diferentes formatos de acessórios:

```text
Boné
Chapéu
Óculos
Máscara
Mochila
Bolsa
Relógio
Pulseira
Corrente
Cordão
```

---

## ⭐ Sistema de raridade

Os acessórios podem possuir diferentes níveis de raridade:

```text
Comum
Raro
Épico
```

Permitindo destacar itens especiais dentro da interface.

---

## 🎨 Sistema de cores

Os itens podem possuir múltiplas opções de cores.

Exemplo:

```text
Preto
Branco
Vermelho
Azul
Verde
Ouro
Prata
Marrom
Cinza
```

Também podem ser enviados valores diretamente em hexadecimal:

```text
#ff0000
#ffffff
#4287f5
```

---

## 👕 Preview de acessórios

A interface possui evento específico para solicitar uma pré-visualização do item no personagem antes da compra.

Exemplo:

```javascript
window.cef.emit(
    'acessorios:preview',
    id,
    cor
);
```

Isso permite que o servidor implemente uma experiência semelhante a lojas modernas de jogos.

---

# 💰 Sistema de compra

O sistema suporta diferentes formas de pagamento.

### 💵 Dinheiro

```text
dinheiro
```

### 💳 CEF

```text
cef
```

Antes da compra, a interface pode validar visualmente:

* saldo disponível;
* existência de conta CEF;
* nível necessário;
* quantidade de slots disponíveis;
* estoque;
* item já adquirido.

---

# 🏠 Menu de Imóveis

Arquivo:

```text
menu-leilao.html
```

Interface desenvolvida para gerenciamento e negociação de propriedades.

O sistema possui três áreas principais.

---

## 🏡 Venda de casas

Permite apresentar propriedades disponíveis para compra direta.

Informações que podem ser exibidas:

```text
ID
Preço
Proprietário
Área
Quartos
Vagas
Bairro
Modalidade
```

---

## 🔨 Leilão de imóveis

Permite criar uma experiência de leilão dentro do jogo.

O jogador pode:

* visualizar propriedades;
* conferir o valor atual;
* visualizar informações do imóvel;
* enviar um lance;
* acompanhar a modalidade;
* receber retorno do servidor após a operação.

---

## 🏦 Imóveis CEF

Área destinada a propriedades ligadas ao sistema CEF.

Pode ser utilizada para sistemas como:

* imóveis retomados;
* venda direta;
* financiamento;
* licitação;
* imóveis especiais;
* eventos econômicos.

---

# 🔍 Ordenação

Os menus possuem opções para ordenar os elementos.

Exemplo:

```text
Padrão
Menor preço
Maior preço
```

Isso facilita a navegação quando existe uma quantidade maior de itens.

---

# 🔌 Integração com CEF

O projeto detecta automaticamente se está sendo executado dentro de um ambiente com suporte a:

```javascript
window.cef
```

Exemplo:

```javascript
var IN_CEF = !!(
    window.cef &&
    window.cef.emit
);
```

Quando o CEF está disponível, os eventos são enviados normalmente para o jogo.

Quando não está disponível, a interface entra automaticamente em **modo de desenvolvimento**.

---

# 🧪 Modo de desenvolvimento

Os arquivos podem ser abertos diretamente em um navegador.

Exemplo:

```text
Google Chrome
Microsoft Edge
Firefox
```

Caso `window.cef` não esteja disponível, o projeto utiliza dados de demonstração.

Os eventos enviados também podem ser visualizados pelo console.

Exemplo:

```javascript
console.log('[cef.emit]', evento);
```

Isso facilita muito o desenvolvimento do frontend sem precisar iniciar o jogo toda vez.

---

# 🔄 Eventos — Acessórios

## Interface → Servidor

### Comprar acessório

```text
acessorios:buy
```

Estrutura:

```javascript
acessorios:buy(
    id,
    cor,
    pagamento
)
```

Exemplo:

```javascript
window.cef.emit(
    'acessorios:buy',
    12,
    'preto',
    'cef'
);
```

---

### Visualizar acessório

```text
acessorios:preview
```

Estrutura:

```javascript
acessorios:preview(
    id,
    cor
)
```

---

### Fechar interface

```text
acessorios:close
```

Exemplo:

```javascript
window.cef.emit(
    'acessorios:close'
);
```

---

# 📡 Eventos recebidos — Acessórios

## Dados

```text
acessorios:data
```

Estrutura esperada:

```json
{
  "player": {
    "nome": "Jogador_Exemplo",
    "dinheiro": 12000,
    "banco": 85000,
    "cef": true,
    "nivel": 8,
    "slots": 2,
    "slotsMax": 5
  },
  "itens": []
}
```

---

## Resultado

```text
acessorios:result
```

Pode ser utilizado pelo servidor para informar:

```text
Compra realizada
Saldo insuficiente
Nível insuficiente
Sem espaço disponível
Item indisponível
Erro na operação
```

---

# 🔄 Eventos — Imóveis

## Interface → Servidor

### Comprar imóvel

```text
houses:buy
```

Estrutura:

```javascript
houses:buy(
    id,
    modo
)
```

---

### Dar lance

```text
houses:bid
```

Estrutura:

```javascript
houses:bid(
    id,
    valor
)
```

---

### Fechar menu

```text
houses:close
```

---

# 📡 Eventos recebidos — Imóveis

## Atualizar propriedades

```text
houses:data
```

Estrutura básica:

```json
{
  "player": {
    "nome": "Jogador_Exemplo",
    "cef": true,
    "saldo": 500000
  },
  "tabs": {
    "venda": [],
    "leilao": [],
    "cef": []
  }
}
```

Cada propriedade pode utilizar:

```json
{
  "id": 412,
  "preco": 185000,
  "dono": "CEF",
  "area": 120,
  "quartos": 3,
  "vagas": 2,
  "bairro": "Centro",
  "tag": "Venda direta"
}
```

---

## Resultado da operação

```text
houses:result
```

Utilizado para informar ao frontend se determinada ação foi concluída.

Exemplo conceitual:

```javascript
window.cef.on(
    'houses:result',
    function(ok, mensagem) {
        // resposta do servidor
    }
);
```

---

# 🎯 Foco CEF

Os arquivos foram estruturados para evitar dependências desnecessárias.

Atualmente o projeto trabalha sem:

```text
CDN
Google Fonts
localStorage
frameworks externos
bibliotecas JavaScript externas
```

Isso reduz problemas de carregamento dentro do CEF e torna o projeto mais independente.

---

# 🚀 Como testar

## 1. Clone o projeto

```bash
git clone https://github.com/Dev-Clayton/Desgn-Menu-CEF-Live-Russia.git
```

---

## 2. Entre na pasta

```bash
cd Desgn-Menu-CEF-Live-Russia
```

---

## 3. Abra um dos arquivos

### Menu de acessórios

```text
acs-menu.html
```

### Menu de imóveis

```text
menu-leilao.html
```

Basta abrir o arquivo diretamente no navegador.

---

# 🎮 Integração no jogo

Para utilização real, carregue o HTML através do sistema CEF/WebView utilizado pelo seu projeto.

O backend deverá implementar os eventos utilizados pelo frontend.

Fluxo simplificado:

```text
┌──────────────────┐
│      JOGADOR     │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│    MENU CEF      │
│ HTML/CSS/JS      │
└────────┬─────────┘
         │
         │ window.cef.emit()
         ▼
┌──────────────────┐
│ SERVIDOR / SCRIPT│
└────────┬─────────┘
         │
         │ window.cef.on()
         ▼
┌──────────────────┐
│ ATUALIZAÇÃO DA UI│
└──────────────────┘
```

---

# 🛡️ Validação

> ⚠️ **Importante**

A interface nunca deve ser responsável pela validação definitiva de compras, saldo, propriedade ou inventário.

O frontend pode mostrar as condições ao jogador, porém o **servidor deve validar novamente todas as informações**.

Sempre valide no backend:

```text
Saldo
Preço
ID
Estoque
Nível
Slots
Propriedade
Permissões
Valor de lance
Método de pagamento
```

Nunca confie apenas nos dados enviados pelo HTML.

---

# 🖼️ Screenshots

Uma melhoria recomendada para o repositório é criar:

```text
docs/
└── screenshots/
    ├── acessorios.png
    └── imoveis.png
```

Depois, as imagens podem ser adicionadas aqui:

```markdown
![Menu de acessórios](docs/screenshots/acessorios.png)

![Menu de imóveis](docs/screenshots/imoveis.png)
```

Isso deixa a página inicial do GitHub muito mais visual e profissional.

---

# 🗺️ Roadmap

Algumas ideias para futuras versões:

* [ ] Sistema completo de animações;
* [ ] Skeleton Loading;
* [ ] Busca por acessórios;
* [ ] Filtros avançados;
* [ ] Favoritos;
* [ ] Histórico de compras;
* [ ] Sistema de confirmação de compra;
* [ ] Preview 3D de acessórios;
* [ ] Paginação;
* [ ] Novas raridades;
* [ ] Sons de interface;
* [ ] Sistema de financiamento completo;
* [ ] Histórico de leilões;
* [ ] Cronômetro de leilão;
* [ ] Atualização em tempo real dos lances;
* [ ] Novos menus CEF;
* [ ] Sistema centralizado de design;
* [ ] Temas configuráveis;
* [ ] Melhor integração com resoluções diferentes;
* [ ] Documentação para integração com Pawn/backend.

---

# 🧩 Filosofia do projeto

O objetivo não é apenas criar telas bonitas.

A proposta é desenvolver interfaces que sejam:

```text
✔ bonitas
✔ rápidas
✔ leves
✔ intuitivas
✔ organizadas
✔ fáceis de integrar
✔ compatíveis com CEF
✔ fáceis de manter
```

---

# 🤝 Contribuições

Sugestões, melhorias e correções são bem-vindas.

Você pode:

1. Fazer um **Fork**;
2. Criar uma branch;
3. Implementar sua melhoria;
4. Criar um **Pull Request**.

Exemplo:

```bash
git checkout -b feature/nova-interface
```

Depois:

```bash
git commit -m "feat: adiciona nova interface CEF"
```

---

# 🐛 Encontrou um problema?

Utilize a área de **Issues** do GitHub para relatar:

* bugs;
* problemas visuais;
* incompatibilidades;
* problemas no CEF;
* sugestões;
* melhorias de UX/UI.

Ao relatar um bug, informe sempre que possível:

```text
Resolução utilizada
Sistema operacional
Versão do CEF/WebView
Arquivo afetado
Descrição do problema
Passos para reproduzir
Screenshot ou vídeo
```

---

# 👨‍💻 Desenvolvedor

<div align="center">

### Dev Clayton

Desenvolvimento de interfaces, sistemas web e projetos voltados para jogos.

[![GitHub](https://img.shields.io/badge/GitHub-Dev--Clayton-181717?style=for-the-badge\&logo=github)](https://github.com/Dev-Clayton)

</div>

---

# ⚠️ Aviso

Este repositório é focado em **design, prototipagem e desenvolvimento de interfaces CEF/WebView**.

Elementos demonstrativos, valores, usuários, propriedades, itens e saldos presentes nos arquivos podem ser utilizados apenas para testes da interface até que sejam substituídos por informações reais enviadas pelo servidor.

---

<div align="center">

## ⭐ Gostou do projeto?

Considere deixar uma **Star ⭐** no repositório.

Isso ajuda a acompanhar o desenvolvimento e incentiva a criação de novas interfaces.

### 🎮 Design Menu CEF — Live Russia

**Interface • Performance • Integração • Experiência**

</div>
