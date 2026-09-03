# 📚 Resumo de Aula: Projetos com Frameworks Front-end

---

## 📌 1. Informações Gerais
* **Instituição:** SENAI[cite: 1].
* **Disciplina:** Frameworks Front-end[cite: 1].
* **Docente:** Prof. Me. Deivison S. Takatu[cite: 1].
* **Tema Central:** Conceitos, comparação, estrutura de pastas e criação de projetos com React, Vue, Angular e Next.js[cite: 1].

---

## 💡 2. Introdução aos Frameworks Front-end
* **Definição:** Conjunto de ferramentas, bibliotecas e convenções que padronizam o desenvolvimento de interfaces web, oferecendo uma estrutura pré-definida para acelerar a criação de aplicações complexas[cite: 1].
* **Vanilla JS vs. Frameworks:**
  * **Sem framework (Vanilla):** Código manual, manutenção difícil e repetição de código[cite: 1].
  * **Com framework:** Componentes reutilizáveis, gerenciamento de estado e atualizações eficientes da interface[cite: 1].
* **Vantagens Principais:** Produtividade aumentada, uso de melhores práticas, manutenção facilitada (Virtual DOM, Change Detection), suporte de comunidade e documentação extensa[cite: 1].

---

## 🔄 3. Diferenças entre Framework e Biblioteca
* **Framework:** Inverte o controle de fluxo (decide quando chamar os componentes) e exige uma estrutura rígida e predefinida[cite: 1]. Exemplos: Angular e Vue[cite: 1].
* **Biblioteca:** Mantém o controle de fluxo nas mãos do desenvolvedor (você decide quando chamá-la) e oferece maior flexibilidade sem imposições[cite: 1]. Exemplos: React e jQuery[cite: 1].

---

## ⚙️ 4. Características dos Frameworks Front-end
* **Estrutura de Código Organizada:** Separação clara entre HTML, CSS e JavaScript[cite: 1].
* **Componentização:** Encapsulamento de lógica e apresentação em blocos independentes e reutilizáveis[cite: 1].
* **Programação Reativa:** Atualização automática da UI quando ocorrem mudanças no estado da aplicação[cite: 1].
* **Ferramentas de Build e Bundling:** Recursos automatizados para minificar, transpilar e combinar arquivos[cite: 1].
* **Sistema de Rotas:** Suporte à criação de Single Page Applications (SPAs) com navegação fluida sem recarregar a página[cite: 1].
* **Integração com APIs:** Facilita chamadas assíncronas e sincronização de dados entre a interface e serviços externos[cite: 1].
* **Padrões de Acessibilidade e Testes:** Suporte nativo a testes unitários/integração e componentes pré-construídos com diretrizes inclusivas[cite: 1].

---

## 🌐 5. Visão Geral das Tecnologias

### React
* **Origem:** Desenvolvido pelo Facebook em 2013[cite: 1].
* **Natureza:** É uma biblioteca JavaScript focada em interfaces de usuário, embora seja frequentemente categorizada como framework[cite: 1].
* **Virtual DOM:** Representação em árvore em memória do DOM real[cite: 1]. O React atualiza primeiro a cópia, compara com o DOM real (*diffing*) e só aplica as diferenças necessárias[cite: 1].
* **Conceitos Fundamentais:**
  * **Hooks:** `useState` (gerenciamento de estado) e `useEffect` (efeitos colaterais/chamadas de API)[cite: 1].
  * **JSX:** Sintaxe que mistura expressões JS em `{}` e atributos em *camelCase* (`className`)[cite: 1].
  * **Gerenciamento de Estado:** Context API (estados menores) e Redux (estados complexos/globais)[cite: 1].

### Angular
* **Origem:** Desenvolvido pelo Google para aplicações de página única (SPA)[cite: 1].
* **Destaques:** Framework completo, suporte nativo ao TypeScript, arquitetura baseada em Programação Orientada a Objetos (POO) e MVC, injeção de dependência e CLI dedicada[cite: 1].
* **Conceitos Fundamentais:** Componentes (`@Component`), Módulos (`@NgModule`), Serviços (`@Injectable`), Data Binding (`[(ngModel)]`, `{{}}`) e Change Detection[cite: 1].

### Vue.js
* **Natureza:** Framework progressivo que se adapta gradualmente às necessidades do projeto[cite: 1].
* **Destaques:** Sistema de reatividade automático, curva de aprendizado suave e Single-File Components (`.vue`), que agrupam HTML, CSS e JS no mesmo arquivo[cite: 1].

### Next.js
* **Natureza:** Framework full-stack baseado em React[cite: 1].
* **Recursos Adicionais:** Roteamento baseado em estrutura de pastas/arquivos, renderização no servidor (SSR), Server Components, otimização de imagens/fontes e criação de APIs backend[cite: 1].

---

## 🛠️ 6. Comandos e Estruturas de Projeto

### Angular CLI
* **Instalar CLI globalmente:** `npm install -g @angular/cli`[cite: 1]
* **Criar projeto:** `ng new meu-app-angular`[cite: 1]
* **Iniciar servidor:** `ng serve` (acesso via `http://localhost:4200/`)[cite: 1]
* **Arquivos e Pastas:** `src/app` (código principal), `main.ts` (inicialização), `angular.json` (configuração do build) e `tsconfig.json` (regras TypeScript)[cite: 1].

### Vue.js (via Vite)
* **Criar projeto:** `npm create vue@latest`[cite: 1]
* **Instalar e rodar:** `cd meu-projeto-vue` ➔ `npm install` ➔ `npm run dev` (acesso via `http://localhost:5173/`)[cite: 1]
* **Arquivos e Pastas:** `src/` (`assets`, `components`, `App.vue`, `main.js`), `index.html` e `vite.config.js`[cite: 1].

### Next.js
* **Criar projeto:** `npx create-next-app@latest meu-projeto`[cite: 1]
* **Iniciar servidor:** `cd meu-projeto` ➔ `npm run dev` (acesso via `http://localhost:3000`)[cite: 1]
* **Arquivos e Pastas:** `app/` (diretório principal com App Router, layouts e `page.js`) e `public/` (recursos estáticos)[cite: 1].

---

## 🔍 7. Importação e Busca de Modelos
* **Modelos Open Source:** Utilizar repositórios e templates acelera o desenvolvimento[cite: 1].
* **Ferramentas de Pesquisa:**
  * **GitHub:** Pesquisa de repositórios usando o comando `git clone <url>`[cite: 1].
  * **Vercel:** Busca de templates com opção de download parcial[cite: 1].
  * **CodeSandbox:** Busca e execução de projetos modelos diretamente no navegador[cite: 1].

---

## 📝 8. Atividade Prática
* **Desafio em Grupo:** Desenvolver 4 projetos web sobre o mesmo tema, utilizando React, Vue, Angular e Next.js[cite: 1].
* **Lista de Entregas:**
  1. Projeto 01: React[cite: 1].
  2. Projeto 02: Vue[cite: 1].
  3. Projeto 03: Angular[cite: 1].
  4. Projeto 04: Next.js[cite: 1].
  5. Projeto 05: Cópia funcional de um repositório modelo[cite: 1].
* **Requisitos:** Versionamento contínuo com Git/GitHub, código responsivo e elaboração de uma análise comparativa ao final do desenvolvimento[cite: 1].