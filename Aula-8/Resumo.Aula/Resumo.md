# Aula 08 â€” Projeto React

**Disciplina:** Frameworks Front-end  
**Foco:** JSX, componentes, props, Virtual DOM, listas e renderizaÃ§Ã£o condicional.

---

## React e JSX

React Ã© uma biblioteca para criar interfaces a partir de componentes. Com **JSX**, a estrutura visual Ã© escrita prÃ³xima da lÃ³gica JavaScript, usando expressÃµes entre chaves para exibir dados.

```jsx
function Saudacao({ nome }) {
  return <h1>OlÃ¡, {nome}!</h1>;
}
```

JSX deve retornar uma estrutura vÃ¡lida, usa `className` em vez de `class` e permite incorporar expressÃµes JavaScript na interface.

## Componentes e props

Um componente Ã© uma funÃ§Ã£o que retorna elementos de interface. Separar uma pÃ¡gina em componentes menores favorece reutilizaÃ§Ã£o, legibilidade e manutenÃ§Ã£o. As **props** sÃ£o parÃ¢metros recebidos pelo componente: elas levam dados do componente pai para o filho e nÃ£o devem ser alteradas pelo filho.

```text
App â†’ CardÃ¡pio â†’ PratoCard
             â””â†’ Filtro de categoria
```

## Virtual DOM, listas e condiÃ§Ãµes

O **Virtual DOM** Ã© uma representaÃ§Ã£o em memÃ³ria da interface. Quando dados mudam, o React compara as alteraÃ§Ãµes e atualiza no DOM real apenas o necessÃ¡rio.

ColeÃ§Ãµes sÃ£o renderizadas com `map()`. Cada item precisa de uma `key` estÃ¡vel para que o React identifique adiÃ§Ãµes, remoÃ§Ãµes e reordenaÃ§Ãµes corretamente.

```jsx
{pratos.map((prato) => (
  <PratoCard key={prato.id} prato={prato} />
))}
```

A **renderizaÃ§Ã£o condicional** adapta a tela ao estado dos dados. Pode mostrar, por exemplo, uma lista quando hÃ¡ resultados ou uma mensagem quando ela estÃ¡ vazia. `if`, retorno antecipado e operador ternÃ¡rio sÃ£o alternativas para expressar essas situaÃ§Ãµes.

## Atividade prÃ¡tica â€” CardÃ¡pio digital

Foi desenvolvido um cardÃ¡pio digital com React 18, TypeScript e Vite. A aplicaÃ§Ã£o separa a interface em componentes funcionais, recebe dados de pratos por props e renderiza os itens com `map()` e `key` baseada no ID.

O usuÃ¡rio pode filtrar categorias e montar um carrinho. A interface usa renderizaÃ§Ã£o condicional para informar quando uma categoria nÃ£o possui pratos; `useState` mantÃ©m o filtro selecionado e os itens do carrinho. A atividade evidencia como componentes, dados e estados colaboram para formar uma interface interativa.

**RepositÃ³rio da atividade:** [Senai-Cardapio-React](https://github.com/paulopoppes-hash/Senai-Cardapio-React)

## SÃ­ntese

Nesta aula, React foi apresentado como uma forma declarativa de construir interfaces. JSX descreve a tela, componentes dividem responsabilidades, props transportam dados e o Virtual DOM atualiza a interface de forma eficiente. Listas com `key` e condiÃ§Ãµes completam a base para interfaces dinÃ¢micas.

