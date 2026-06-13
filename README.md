# TrieDS — Sistema de Autocomplete com Árvore Trie

Projeto acadêmico desenvolvido para a disciplina de **Estrutura de Dados** do curso de **Tecnologia em Sistemas para Internet (TSI)**.

O sistema demonstra, de forma visual e interativa, o funcionamento de uma **Árvore Trie** aplicada a um mecanismo de sugestão de palavras (autocomplete), com análise de complexidade Big-O integrada ao painel.

---

## 📋 Sumário

- [Sobre o Projeto](#sobre-o-projeto)
- [O que é uma Árvore Trie?](#o-que-é-uma-árvore-trie)
- [Funcionalidades](#funcionalidades)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Estrutura de Arquivos](#estrutura-de-arquivos)
- [Como Executar](#como-executar)
- [Implementação em C](#implementação-em-c)
- [Complexidade (Big-O)](#complexidade-big-o)
- [Equipe](#equipe)

---

## Sobre o Projeto

O **TrieDS** é um painel (dashboard) web que permite ao usuário:

- **Inserir palavras** em uma Árvore Trie dinamicamente
- **Buscar sugestões** em tempo real conforme o prefixo digitado
- **Visualizar** todas as palavras cadastradas no dicionário atual
- **Consultar** a tabela de complexidade das operações da estrutura

O projeto possui duas frentes: a interface web interativa (HTML/CSS/JS) e a implementação estrutural do algoritmo em linguagem **C**.

---

## O que é uma Árvore Trie?

Uma **Trie** (do inglês *retrieval*) é uma estrutura de dados em árvore utilizada para armazenar e recuperar strings de forma eficiente. Cada nó da árvore representa um caractere, e o caminho da raiz até um nó folha forma uma palavra completa.

```
Exemplo com as palavras: "casa", "caso", "cama"

        (raiz)
          |
          c
          |
          a
         / \
        s   m
       / \   \
      a   o   a ✓
      ✓   ✓
```

Sua maior vantagem está na busca por prefixo: ao digitar `"ca"`, a Trie retorna imediatamente todas as palavras que começam com esse prefixo, percorrendo apenas os nós relevantes.

---

## Funcionalidades

- **Inserção dinâmica** — adiciona palavras à Trie pelo painel e exibe tags visuais em tempo real
- **Autocomplete por prefixo** — sugestões atualizadas a cada tecla digitada
- **Limpar busca** — botão para resetar o campo de busca instantaneamente
- **Tabela de complexidade** — exibe o Big-O das operações diretamente no painel
- **Design responsivo** — layout adaptado para desktop, tablet e mobile

---

## Tecnologias Utilizadas

| Camada | Tecnologia | Função |
|---|---|---|
| Estrutura | HTML5 | Marcação semântica da interface |
| Estilo | CSS3 / SCSS | Estilização e responsividade |
| Lógica (Web) | JavaScript (ES6+) | Manipulação do DOM e integração com a Trie |
| Algoritmo | C | Implementação da Trie e operações |
| Ícones | Font Awesome 6 | Ícones da interface |
| Pré-processador | Sass | Organização de variáveis, mixins e breakpoints |

---

## Estrutura de Arquivos

```
projeto-trie/
│
├── css/
│   └── main.css              # CSS compilado (gerado pelo Sass)
│
├── js/
│   ├── trie.js               # Implementação da Árvore Trie em JavaScript
│   └── main.js               # Gerenciamento de eventos e integração com a Trie
│
├── scss/
│   ├── _variables.scss       # Variáveis globais (cores, breakpoints)
│   ├── _mixins.scss          # Mixins de responsividade (media queries)
│   └── main.scss             # Arquivo principal que orquestra os módulos SCSS
│
├── index.html                # Página principal da aplicação
├── .gitignore                # Arquivos ignorados pelo Git
└── README.md                 # Documentação do projeto
```

---

## Como Executar

### Interface Web

Não há dependências de servidor. Basta abrir o arquivo diretamente no navegador:

```bash
# Clone o repositório
git clone https://github.com/NevesByte/Upload-em-processamento

# Acesse a pasta do projeto
cd projeto-trie

# Abra o arquivo principal no navegador
# Windows
start index.html

# macOS
open index.html

# Linux
xdg-open index.html
```

> **Observação sobre o SCSS:** o arquivo `css/main.css` já está incluído no repositório e pronto para uso. Se quiser recompilar o SCSS após alguma alteração, é necessário ter o [Node.js](https://nodejs.org/) e o compilador Sass instalados:
> ```bash
> npm install -g sass
> sass scss/main.scss css/main.css --watch
> ```

---

## Implementação em C

Além da interface web, o projeto conta com a implementação da Árvore Trie em **linguagem C**, conforme os requisitos da disciplina de Estrutura de Dados.

### Compilação

```bash
gcc trie.c -o trie
./trie
```

### Operações implementadas

```c
// Inserir uma palavra na Trie
void inserir(Trie *trie, const char *palavra);

// Buscar todas as palavras com um determinado prefixo
void buscarPrefixo(Trie *trie, const char *prefixo);

// Verificar se uma palavra existe na Trie
int buscar(Trie *trie, const char *palavra);
```

### Exemplo de uso

```c
Trie *trie = criarTrie();

inserir(trie, "estrutura");
inserir(trie, "dados");
inserir(trie, "trie");
inserir(trie, "arvore");

// Saída esperada: "arvore"
buscarPrefixo(trie, "ar");
```

---

## Complexidade (Big-O)

| Operação | Tempo (Pior Caso) | Espaço |
|---|---|---|
| Inserção | `O(m)` | `O(m × n)` |
| Busca por prefixo | `O(m)` | `O(1)` |
| Verificação de palavra | `O(m)` | `O(1)` |

> `m` = tamanho da palavra (número de caracteres)
> `n` = número total de palavras inseridas na Trie

A Trie se destaca em buscas por prefixo justamente por percorrer apenas os nós do caminho correspondente, sem comparar com todas as palavras do dicionário.

---

## Equipe

Desenvolvido por:

- **Mariana Alice** 
- **Victor Fernandes** 
- **Yasmim Vitória**

---

<p align="center">
  Projeto acadêmico — Estrutura de Dados · TSI · 2026
</p>
