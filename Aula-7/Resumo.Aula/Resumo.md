# Aula 07 â€” Frameworks CSS

**Disciplina:** Frameworks Front-end  
**Foco:** CSS, layouts responsivos e Tailwind CSS.

---

## CSS para construir interfaces

O CSS define a apresentaÃ§Ã£o da pÃ¡gina: cores, tipografia, dimensÃµes, espaÃ§amentos, alinhamentos e posicionamento. Uma regra segue a estrutura `seletor { propriedade: valor }`.

HÃ¡ trÃªs formas de aplicÃ¡-lo:

- **inline:** no atributo `style`, adequado apenas para ajustes pontuais;
- **interno:** na tag `<style>` de uma pÃ¡gina;
- **externo:** em arquivo `.css` importado com `<link>`, a opÃ§Ã£o mais reutilizÃ¡vel e indicada para projetos.

Classes permitem reutilizar estilos em vÃ¡rios elementos; IDs identificam elementos Ãºnicos. Entre as propriedades exploradas estÃ£o `color`, `background-color`, `font-family`, `font-size`, `display`, `position`, `width`, `height` e `text-align`.

## Box Model, Flexbox e responsividade

Todo elemento HTML ocupa uma caixa formada por:

```text
margin â†’ border â†’ padding â†’ content
```

- **content:** Ã¡rea do conteÃºdo;
- **padding:** espaÃ§o interno;
- **border:** contorno da caixa;
- **margin:** espaÃ§o externo em relaÃ§Ã£o a outros elementos.

O **Flexbox** organiza itens em uma dimensÃ£o, em linha ou coluna. Propriedades como `flex-direction`, `justify-content`, `align-items`, `flex-wrap` e `gap` tornam a distribuiÃ§Ã£o dos componentes mais previsÃ­vel. Combinado a larguras flexÃ­veis e pontos de quebra, ele ajuda a criar layouts que se adaptam a celular, tablet e desktop.

## Framework CSS e Tailwind

Um framework CSS reÃºne padrÃµes, componentes e recursos para acelerar a construÃ§Ã£o de interfaces consistentes. O Tailwind CSS segue a abordagem **Utility-First**: cada classe representa uma responsabilidade pequena e as classes sÃ£o compostas diretamente no HTML.

```html
<button class="bg-blue-600 text-white px-6 py-3 rounded-lg">
  Enviar
</button>
```

No exemplo, as utilitÃ¡rias definem cor, texto, espaÃ§amento e borda arredondada. O Tailwind pode ser usado rapidamente via CDN ou integrado ao processo de build com CLI. Prefixos como `md:` e `lg:` permitem aplicar estilos a partir de determinados tamanhos de tela.

## Atividade 01 â€” Loja virtual

A atividade implementa uma pÃ¡gina de loja virtual com HTML5 e CSS3. O projeto aplica o Box Model em 20 elementos, utiliza Flexbox para disposiÃ§Ã£o responsiva e exercita seletores, classes, IDs, cores, fontes, bordas e posicionamento.

**RepositÃ³rio:** [Senai-Loja-CSS](https://github.com/paulopoppes-hash/Senai-Loja-CSS)

## Atividade 02 â€” PortfÃ³lio com Tailwind

O portfÃ³lio foi construÃ­do com HTML5 e Tailwind CSS carregado por CDN. A interface reÃºne navegaÃ§Ã£o fixa, seÃ§Ã£o de destaque, grade responsiva de cards, tags de habilidades e rodapÃ©. O projeto usa mais de 30 classes utilitÃ¡rias para grid, flexbox, cores, tipografia, espaÃ§amentos, dimensÃµes, bordas, efeitos e responsividade, sem CSS customizado.

**RepositÃ³rio:** [Senai-Portfolio-Tailwind](https://github.com/paulopoppes-hash/Senai-Portfolio-Tailwind)

## SÃ­ntese

A aula conecta fundamentos de CSS a ferramentas que aumentam a produtividade. Com Box Model, Flexbox e responsividade, o layout fica organizado; com Tailwind, as decisÃµes visuais sÃ£o compostas por utilitÃ¡rias consistentes e adaptÃ¡veis.

