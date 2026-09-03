# 📚 Resumo de Aula: Consumindo APIs no Front-end

---

## 📌 1. Informações Gerais
* **Instituição:** SENAI[cite: 2].
* **Disciplina:** Frameworks Front-end[cite: 2].
* **Docente:** Prof. Me. Deivison S. Takatu[cite: 2].
* **Tema Central:** Conceitos de APIs, protocolo HTTP, endpoints, formato JSON, criação de APIs com Express.js e hospedagem na nuvem com Render[cite: 2].

---

## 🌐 2. Conceitos de API e Arquitetura REST
* **API (Application Programming Interface):** Conjunto de protocolos, rotinas e ferramentas que define como diferentes componentes de software devem interagir e se comunicar[cite: 2].
* **REST (Representational State Transfer):** Estilo arquitetural para desenvolvimento de sistemas distribuídos na web[cite: 2].
* **Princípios do REST:**
  * Comunicação cliente-servidor sem estado (*stateless*)[cite: 2].
  * Uso padronizado dos métodos HTTP[cite: 2].
  * Recursos identificados por URIs[cite: 2].
  * Representação de dados por formatos estruturados (como JSON)[cite: 2].

---

## 📡 3. O Protocolo HTTP e Métodos
* **Definição:** Protocolo de comunicação da Web que estabelece as regras de troca de mensagens entre o cliente (navegador) e o servidor[cite: 2].
* **Principais Conceitos:**
  * **Modelo Cliente-Servidor:** O cliente realiza requisições e o servidor responde[cite: 2].
  * **Stateless:** Cada requisição é independente; o servidor não memoriza chamadas anteriores[cite: 2].
  * **Baseado em Texto:** Mensagens estruturadas em formato legível por humanos[cite: 2].

### Métodos HTTP Principais

| Método | Finalidade | Características Técnicas |
| :--- | :--- | :--- |
| **`GET`** | Recuperar informações do servidor[cite: 2]. | Seguro (não altera dados) e idempotente (múltiplas chamadas geram o mesmo resultado)[cite: 2]. |
| **`POST`** | Criar novos recursos no servidor[cite: 2]. | Não idempotente (chamadas repetidas criam múltiplos recursos)[cite: 2]. |
| **`PUT`** | Substituir completamente um recurso existente[cite: 2]. | Serve para atualização completa[cite: 2]. |
| **`PATCH`** | Atualizar parcialmente um recurso[cite: 2]. | Alteração pontual de dados[cite: 2]. |
| **`DELETE`** | Remover um recurso específico[cite: 2]. | Idempotente (remover um recurso já apagado não gera erro)[cite: 2]. |

---

## 🔄 4. Fluxo de Execução de uma Requisição
1. **Front-end / Navegador:** O usuário interage com a interface (clique ou carregamento)[cite: 2].
2. **Requisição HTTP:** O navegador dispara uma chamada (`GET`, `POST`, `PUT`, `DELETE`) para o backend[cite: 2].
3. **Servidor Express.js:** O backend recebe a requisição, identifica a rota e executa a lógica[cite: 2].
4. **Banco de Dados / API Externa:** O servidor consulta, grava ou atualiza informações[cite: 2].
5. **Resposta JSON:** O servidor retorna os dados processados em formato JSON[cite: 2].
6. **Atualização da Tela:** O front-end recebe os dados e atualiza a interface para o usuário[cite: 2].

---

## 🧩 5. Endpoints e Formato JSON

### Endpoint
* URL específica que dá acesso a um recurso ou funcionalidade dentro de uma API, servindo de ponto de comunicação entre cliente e servidor[cite: 2].
* **Exemplo:** `https://github.com/awesomeapibrasil/awesomeapi-cep`[cite: 2].
* **Repositórios Públicos:** Plataformas como `freepublicapis.com` ajudam a encontrar APIs abertas para integração e estudo[cite: 2].

### JSON (JavaScript Object Notation)
* Formato leve de troca de dados, fácil de ler/escrever por humanos e simples de interpretar (*parsear*) por máquinas[cite: 2].
* Baseia-se em duas estruturas principais:
  * **Objetos:** Coleções de pares chave/valor `{}`[cite: 2].
  * **Arrays:** Listas ordenadas de valores `[]`[cite: 2].

---

## ⚙️ 6. Criando APIs com Node.js e Express.js

### Servidor Backend vs. Web Service
* **Servidor Backend:** Sistema que processa requisições, gerencia dados no banco, aplica regras de negócio e fornece APIs[cite: 2].
* **Web Service:** Serviço web acessível via HTTP/HTTPS que permite a comunicação entre sistemas heterogêneos (diferentes linguagens/plataformas)[cite: 2].

### Express.js
* Framework para Node.js que simplifica a criação de rotas, manipulação de middlewares e construção de servidores web leves e rápidos[cite: 2].
* **Vantagens sobre o Node.js puro:** Reduz consideravelmente a quantidade de código necessário para criar rotas e tratar requisições[cite: 2].
* **CORS (Cross-Origin Resource Sharing):** Mecanismo de segurança indispensável que controla o acesso à API entre domínios diferentes[cite: 2].

### Passo a Passo de Criação
1. **Inicializar projeto e instalar dependências:**
   ```bash
   npm install express
   npm install cors
   ```[cite: 2]
2. **Estrutura básica (`api.js`):**
   ```javascript
   import express from 'express';
   import cors from 'cors';

   const app = express();
   app.use(cors());

   app.get('/', (req, res) => {
     res.json({
       date: new Date().toLocaleString('pt-BR'),
       status: 'API no Render funcionando!'
     });
   });

   const PORT = process.env.PORT || 3000;
   app.listen(PORT, () => {
     console.log(`Servidor rodando na porta ${PORT}`);
   });
   ```[cite: 2]
3. **Executar o servidor localmente:**
   ```bash
   node api.js
   ```[cite: 2]

---

## ☁️ 7. Hospedagem na Nuvem com Render
* **Render:** Plataforma de nuvem para hospedagem de aplicações Node.js e APIs[cite: 2]. Oferece deploy contínuo integrado ao GitHub, certificado SSL gratuito e plano inicial gratuito[cite: 2].
* **Etapas para Deploy:**
  1. Realizar o commit e subir o código para o GitHub[cite: 2].
  2. Acessar `dashboard.render.com` e criar um novo **Web Service** conectado ao repositório[cite: 2].
  3. Definir o comando de build (`node`) e o comando de inicialização (`node api.js`)[cite: 2].
  4. Concluir o deploy e utilizar a URL pública gerada (`seu-projeto.onrender.com`)[cite: 2].

---

## 📝 8. Atividades Práticas

### Atividade 01
* Pesquisar 10 projetos no GitHub que consumam APIs[cite: 2].
* Clonar e analisar os projetos identificando o framework e a API utilizada[cite: 2].
* Gerar uma tabela em Markdown resumindo os projetos analisados[cite: 2].

### Atividade 02
1. Criar uma API com Express que possua uma rota para retornar data e hora atuais[cite: 2].
2. Fazer o deploy da API no Render[cite: 2].
3. Desenvolver uma aplicação Front-end em repositório separado que consuma a API hospedada e exiba a data e hora na tela[cite: 2].
4. Entregar um documento estruturado contendo prints do código, aplicação rodando, dashboards (Render/Vercel) e os links dos repositórios GitHub[cite: 2].