# 📚 Resumo de Aula: Criando APIs para o Front-end

---

## 📌 1. Informações Gerais
* **Instituição:** SENAI[cite: 3].
* **Disciplina:** Frameworks Front-end[cite: 3].
* **Docente:** Prof. Me. Deivison S. Takatu[cite: 3].
* **Tema Central:** Desenvolvimento de APIs RESTful com Express.js, implementação de rotas CRUD, persistência de dados em arquivo JSON, hospedagem no Render, conexão com front-end em React e documentação de requisições com o Postman[cite: 3].

---

## 🌐 2. Recapitulação de Conceitos Fundamentais
* **API REST:** Estilo arquitetural sem estado (*stateless*) onde requisições utilizam métodos HTTP padronizados para manipular recursos representados em formatos como JSON[cite: 3].
* **Endpoints:** URLs específicas que servem como ponto de comunicação entre o cliente e o servidor[cite: 3].
* **Express.js vs Node.js Puro:** O Express simplifica o roteamento e a manipulação de middlewares no Node.js, reduzindo a complexidade e quantidade de código necessárias[cite: 3].
* **CORS:** Mecanismo de segurança indispensável para controlar e permitir o acesso à API a partir de domínios externos no navegador[cite: 3].

---

## 🛠️ 3. Desenvolvimento de API RESTful com CRUD (`projeto-notas`)
A evolução do projeto de backend substitui retornos estáticos por uma aplicação capaz de gerenciar notas (criar, ler, atualizar e excluir), aplicando as operações de CRUD com persistência de dados em um arquivo local `data.json`[cite: 3].

### Rotas e Mapeamento HTTP

| Operação | Método | Rota | Funcionalidade |
| :--- | :--- | :--- | :--- |
| **Read (Listar)** | `GET` | `/api/notes` | Retorna todas as notas salvas no arquivo JSON[cite: 3]. |
| **Read (Buscar)** | `GET` | `/api/notes/:id` | Retorna uma nota específica filtrada por seu ID[cite: 3]. |
| **Create (Criar)** | `POST` | `/api/notes` | Cria uma nova nota gerando um ID único (`Date.now().toString()`)[cite: 3]. |
| **Update (Editar)**| `PUT` | `/api/notes/:id` | Atualiza os dados de uma nota existente pelo ID[cite: 3]. |
| **Delete (Excluir)**| `DELETE` | `/api/notes/:id` | Remove uma nota do arquivo com base no ID[cite: 3]. |

### Configuração e Implementação Passo a Passo

1. **Instalação das Dependências:**
   ```bash
   npm install express body-parser
   ```[cite: 3]
   * *`body-parser`:* Middleware utilizado para permitir que o Express leia o corpo das requisições no formato JSON[cite: 3].

2. **Estrutura Básica do Arquivo de Dados (`data.json`):**
   ```json
   [
     {
       "id": "1",
       "titulo": "Lembretes",
       "texto": "Comprar leite e pão",
       "criadoEm": "2026-04-28T10:00:00Z"
     }
   ]
   ```[cite: 3]

3. **Código Principal do Servidor (`server.js`):**
   ```javascript
   const express = require('express');
   const bodyParser = require('body-parser');
   const fs = require('fs');

   const app = express();
   const PORT = 3000;
   const FILE = 'data.json';

   // Middlewares
   app.use(bodyParser.json());
   app.use((req, res, next) => {
     res.header('Access-Control-Allow-Origin', '*');
     next();
   });

   // Funções auxiliares para manipulação do arquivo JSON
   function readNotes() {
     try {
       const data = fs.readFileSync(FILE);
       return JSON.parse(data);
     } catch {
       return [];
     }
   }

   function saveNotes(notes) {
     fs.writeFileSync(FILE, JSON.stringify(notes, null, 2));
   }

   // Rota GET - Listar notas
   app.get('/api/notes', (req, res) => {
     const notes = readNotes();
     res.json(notes);
   });

   // Rota POST - Criar nova nota
   app.post('/api/notes', (req, res) => {
     const notes = readNotes();
     const novaNota = {
       id: Date.now().toString(),
       titulo: req.body.titulo,
       texto: req.body.texto
     };
     notes.push(novaNota);
     saveNotes(notes);
     res.json(novaNota);
   });

   // Rota PUT - Editar nota por ID
   app.put('/api/notes/:id', (req, res) => {
     const notes = readNotes();
     const index = notes.findIndex(n => n.id === req.params.id);
     if (index >= 0) {
       notes[index].titulo = req.body.titulo;
       notes[index].texto = req.body.texto;
       saveNotes(notes);
       res.json(notes[index]);
     } else {
       res.status(404).json({ erro: 'Nota não encontrada' });
     }
   });

   // Rota DELETE - Remover nota por ID
   app.delete('/api/notes/:id', (req, res) => {
     const notes = readNotes();
     const novasNotas = notes.filter(n => n.id !== req.params.id);
     saveNotes(novasNotas);
     res.json({ mensagem: 'Nota removida' });
   });

   // Inicialização do servidor
   app.listen(PORT, () => {
     console.log(`Servidor rodando em http://localhost:${PORT}`);
   });
   ```[cite: 3]

---

## 🚀 4. Workflow de Deploy e Integração
1. **Publicar Backend (Render):** Subir o código do servidor para o GitHub e realizar o deploy no Render[cite: 3].
2. **Conectar Front-end (React):** Substituir as URLs das chamadas `http://localhost:3000/api/notes` pela URL pública gerada no Render[cite: 3].
3. **Publicar Front-end (Vercel):** Enviar a aplicação React para o GitHub e publicar na plataforma Vercel[cite: 3].

---

## 💭 5. Análise Crítica e Questões Arquiteturais
* **Persistência em Arquivo JSON:** Adequada para prototipagem rápida e estudos, porém inadequada para produção devido ao risco de concorrência e corrupção de dados sob alto volume de acessos[cite: 3].
* **Desempenho e Escalabilidade:** Operações síncronas de leitura e escrita em arquivo (`fs.readFileSync` e `fs.writeFileSync`) travam a *Event Loop* do Node.js, degradando a performance em casos com milhares de requisições[cite: 3].
* **Organização de Código:** Manter todas as rotas e regras de negócio dentro de um único arquivo (`server.js`) dificulta a manutenção, tornando recomendável a separação em padrões como MVC (Controllers, Routes e Models)[cite: 3].

---

## 📄 6. Documentação de APIs com Postman
* **Definição:** Ferramenta para criação, teste, documentação e monitoramento de requisições HTTP[cite: 3].
* **Recursos Principais:**
  * **Coleções (Collections):** Agrupamento e organização de requisições por projeto para compartilhamento[cite: 3].
  * **Variáveis de Ambiente:** Facilidade na alternância entre rotas locais (`localhost`) e URLs em produção[cite: 3].
  * **Mock Servers:** Simulação de APIs antes de implementar o código backend[cite: 3].
  * **Newman CLI:** Execução de testes de API automatizados diretamente em pipelines CI/CD[cite: 3].

---

## 📝 7. Atividades Práticas

### Atividade 01
* Atualizar o repositório da disciplina no GitHub com as alterações recentes[cite: 3].
* Confirmar o envio dos arquivos e disponibilizar o link público através do formulário de entrega (`https://forms.gle/L7iL7jx1RzyiXBnk9`)[cite: 3].

### Atividade 02
1. **Backend:** Construir a API CRUD em Express com persistência em JSON e realizar o deploy no Render[cite: 3].
2. **Front-end:** Criar a interface gráfica em React consumindo a API no Render para gerenciar as notas e hospedá-la na Vercel[cite: 3].
3. **Postman:** Criar e configurar uma coleção completa documentando as rotas CRUD e seus códigos de resposta HTTP[cite: 3].
4. **Entrega:** Compilar documento em PDF com capturas de tela do código, da aplicação funcionando, links dos repositórios GitHub, link do deploy na Vercel e o link da coleção do Postman (submissão via plataforma CANVA)[cite: 3].