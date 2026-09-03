# ⚛️ Resumo de Aula: Fundamentos e Arquitetura do React.js

---

## 📌 1. Visão Geral e Propósito
* **Definição:** O React.js é uma biblioteca JavaScript *open-source* criada pela Meta (Facebook) focada na criação de **interfaces de usuário (UI)**.
* **Foco de Atuação:** Atua estritamente na camada de visualização (*View*) da aplicação.
* **Modelo SPA:** Utilizado na construção de **Single Page Applications**, onde a navegação e atualização das telas ocorrem sem recarregar a página no navegador.

---

## 🏗️ 2. Arquitetura e Funcionamento

### Paradigma Declarativo
* **Imperativo (JS Tradicional):** Instrução passo a passo de como manipular o DOM (`document.querySelector`, `appendChild`).
* **Declarativo (React):** O desenvolvedor descreve o estado final da interface em relação aos dados, e o React trata de atualizar o navegador automaticamente.

### Virtual DOM (VDOM)
1. Cópia leve da árvore DOM mantida em memória RAM.
2. Quando ocorrem alterações de dados, uma nova versão do VDOM é criada.
3. O algoritmo de reconciliação (*Diffing*) compara a versão nova com a anterior.
4. O React altera no DOM real **apenas os nós que foram modificados**, otimizando o desempenho.

### Fluxo de Dados Unidirecional
* As informações transitam em um único sentido: **do componente pai para o componente filho**.

---

## 🧩 3. Conceitos Fundamentais

### 3.1 Componentização
* A interface é dividida em blocos autônomos, reutilizáveis e isolados.
* **Padrão Atual:** Componentes funcionais (funções JS que retornam estrutura visual).
* **Nomenclatura:** Devem sempre começar com letra maiúscula (ex: `Header`, `Button`).

### 3.2 JSX (JavaScript XML)
* Extensão de sintaxe que permite escrever marcação estilo HTML dentro de arquivos JavaScript.
* Compilado internamente para chamadas `React.createElement()`.
* **Interpolação:** Uso de chaves `{}` para inserir código/variáveis JavaScript dentro do JSX.
* **Diferenças do HTML Nativo:**
  * `class` vira `className`
  * `for` vira `htmlFor`
  * Eventos utilizam *camelCase* (`onClick`, `onChange`, `onSubmit`).

### 3.3 Props (Propriedades)
* Parâmetros e dados repassados de um componente pai para um componente filho.
* **Regra de Ouro:** São estritamente de **apenas leitura** (imutáveis no componente receptor).

### 3.4 Estado (*State*)
* Dados mutáveis que representam a memória interna do componente.
* A alteração de um estado é o gatilho que força a **re-renderização** do componente na tela.

---

## ⚓ 4. Tabela de Hooks Principais

| Hook | Função Técnica |
| :--- | :--- |
| **`useState`** | Gerencia o estado local e dispara a atualização da interface. |
| **`useEffect`** | Controla efeitos colaterais (chamadas de API, timers, subscrições). |
| **`useContext`** | Acessa dados globais sem a necessidade de passar *props* por múltiplos níveis (*prop drilling*). |
| **`useRef`** | Armazena valores mutáveis que não disparam re-renderização ou acessa elementos diretamente da DOM. |
| **`useMemo`** | Memoriza resultados de cálculos custosos para otimização. |
| **`useCallback`** | Memoriza definições de funções entre renderizações. |

---

## 🌐 5. Modos de Renderização e Ecossistema

### Modos de Renderização
* **CSR (Client-Side Rendering):** Renderização total no navegador do cliente (padrão do React puro).
* **SSR (Server-Side Rendering):** HTML pré-renderizado no servidor a cada requisição (ex: Next.js).
* **SSG (Static Site Generation):** Páginas estáticas geradas previamente durante a etapa de compilação (*build*).

### Ferramentas Complementares
* **Vite / Rspack:** Ferramentas de *build* e servidor de desenvolvimento.
* **React DOM:** Pacote responsável por integrar o React ao ambiente dos navegadores.
* **React Native:** Framework para criação de aplicativos móveis nativos (iOS e Android) utilizando a mesma sintaxe do React.