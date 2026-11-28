# Aula 09 â€” Projeto React 02

**Disciplina:** Frameworks Front-end  
**Foco:** estado, formulÃ¡rios, efeitos, consumo de APIs e navegaÃ§Ã£o em aplicaÃ§Ãµes React.

---

## Estado e `useState`

O **state** guarda informaÃ§Ãµes que podem mudar durante o uso do componente. Diferentemente de uma variÃ¡vel comum, sua atualizaÃ§Ã£o solicita uma nova renderizaÃ§Ã£o da interface.

```jsx
const [contador, setContador] = useState(0);
```

`useState` retorna o valor atual e uma funÃ§Ã£o para atualizÃ¡-lo. O novo estado deve representar a mudanÃ§a de forma previsÃ­vel, permitindo que a tela acompanhe as aÃ§Ãµes do usuÃ¡rio.

## FormulÃ¡rios controlados

Em React, um formulÃ¡rio pode ser controlado pelo estado. A propriedade `value` recebe o valor guardado, enquanto `onChange` atualiza esse valor conforme a pessoa digita.

```jsx
const [nome, setNome] = useState("");

<input value={nome} onChange={(evento) => setNome(evento.target.value)} />
```

O evento `onSubmit` trata o envio. `event.preventDefault()` impede o recarregamento automÃ¡tico da pÃ¡gina e permite validar os dados ou executar uma chamada Ã  API dentro do fluxo React.

## `useEffect` e sincronizaÃ§Ã£o

Efeitos sÃ£o aÃ§Ãµes que conectam o componente a sistemas externos, como tÃ­tulo da aba, temporizadores, eventos do navegador e serviÃ§os HTTP. O `useEffect` recebe uma funÃ§Ã£o e, opcionalmente, uma lista de dependÃªncias.

```jsx
useEffect(() => {
  document.title = titulo;
}, [titulo]);
```

O efeito Ã© executado novamente quando uma dependÃªncia muda. Quando o efeito cria um recurso, deve retornar uma funÃ§Ã£o de limpeza para remover eventos, cancelar temporizadores ou liberar conexÃµes quando necessÃ¡rio.

## Consumo de APIs

O `fetch` realiza requisiÃ§Ãµes HTTP de forma assÃ­ncrona. Uma busca normalmente verifica `response.ok`, converte a resposta com `response.json()` e guarda os dados em estado. O `useEffect` Ã© adequado para iniciar essa busca na montagem do componente.

```jsx
useEffect(() => {
  async function carregar() {
    const resposta = await fetch(url);
    if (!resposta.ok) throw new Error("Falha na consulta");
    setDados(await resposta.json());
  }

  carregar();
}, []);
```

TambÃ©m Ã© necessÃ¡rio considerar carregamento, estado vazio, erros de rede, CORS, autenticaÃ§Ã£o e limites do serviÃ§o. Para enviar dados, uma requisiÃ§Ã£o `POST` informa o mÃ©todo, o cabeÃ§alho `Content-Type` e o corpo convertido com `JSON.stringify()`.

## React Router

O React Router associa caminhos da URL a componentes sem recarregar todo o documento. `BrowserRouter` envolve a aplicaÃ§Ã£o, `Routes` agrupa as rotas e `Route` define cada caminho.

```jsx
<BrowserRouter>
  <Routes>
    <Route path="/" element={<Inicio />} />
    <Route path="/sobre" element={<Sobre />} />
    <Route path="/tarefa/:id" element={<Detalhe />} />
  </Routes>
</BrowserRouter>
```

`Link` realiza a navegaÃ§Ã£o interna; `useParams` lÃª parÃ¢metros como `:id` e hooks de navegaÃ§Ã£o podem conduzir o usuÃ¡rio por cÃ³digo. O roteamento separa telas como inÃ­cio, detalhes e sobre em uma aplicaÃ§Ã£o de pÃ¡gina Ãºnica.

## Atividade prÃ¡tica â€” Gerenciador de tarefas

Foi desenvolvido um gerenciador de tarefas com React 18, TypeScript, Vite e React Router DOM. A pÃ¡gina inicial busca tarefas da API JSONPlaceholder e mantÃ©m os dados, o formulÃ¡rio e o status de conclusÃ£o com `useState`.

O formulÃ¡rio usa campo controlado, `onChange` e `preventDefault`. Um `useEffect` executa a busca ao montar a tela, enquanto a interface trata carregamento, conteÃºdo e estados vazios. Rotas apresentam a lista, os detalhes de uma tarefa (`/tarefa/:id`) e a pÃ¡gina sobre. Assim, a atividade integra estado, formulÃ¡rios, efeitos, API e navegaÃ§Ã£o em um fluxo Ãºnico.

**RepositÃ³rio da atividade:** [Senai-Tarefas-Router](https://github.com/paulopoppes-hash/Senai-Tarefas-Router)

## SÃ­ntese

A aula amplia a base de React para aplicaÃ§Ãµes reais: o estado torna a interface interativa, formulÃ¡rios capturam dados, efeitos sincronizam o componente com o mundo externo, APIs fornecem dados e o Router organiza vÃ¡rias telas em uma experiÃªncia de navegaÃ§Ã£o sem recarregamento.

