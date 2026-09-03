# DOCUMENTAÇÃO DE RESUMO DE AULA — VANILLA JAVASCRIPT

## PROJETO PRÁTICO: JOGO DOS SETE ERROS

---

## 1. INFORMAÇÕES GERAIS

- **Título da Aula:** Introdução ao Vanilla JavaScript e Aplicação Prática
- **Tema Central:** Fundamentos do JavaScript Nativo e Manipulação de DOM
- **Projeto Desenvolvido:** Jogo dos Sete Erros Interativo
- **Tecnologias Utilizadas:** HTML5, CSS3 e Vanilla JavaScript (ES6+)

---

## 2. CONCEITO: O QUE É VANILLA JAVASCRIPT?

### Definição

"Vanilla JS" não é um framework nem uma biblioteca nova. É o termo utilizado para se referir ao JavaScript puro/nativo, sem nenhuma camada de abstração externa, como React, Vue, Angular, jQuery, etc.

### Origem do Termo

A analogia vem do sorvete de baunilha ("vanilla ice cream"), que representa o sabor básico, padrão e sem adicionais.

### Vantagens do Uso de JavaScript Puro

- **Alta Performance:** execução rápida, sem necessidade de carregar bibliotecas externas ou arquivos pesados.
- **Aprendizado Sólido:** compreensão real do funcionamento do navegador, da árvore DOM e da execução assíncrona/eventos.
- **Zero Dependências:** funciona nativamente em qualquer navegador moderno.
- **Facilidade de Transição:** quem domina o JavaScript puro aprende qualquer framework moderno com muito mais facilidade.

---

## 3. CONCEITOS TEÓRICOS APRENDIDOS

### Manipulação da Árvore DOM (Document Object Model)

- Seleção de elementos HTML a partir da página via script.
- Leitura e modificação do conteúdo textual e estrutural dos elementos.

### Event Listeners (Escutadores de Eventos)

- Captura de interações do usuário, especificamente o evento de clique (`click`).
- Execução de funções de callback no momento exato da interação.

### Manipulação Dinâmica de Estilos e Classes

- Adição e remoção de classes CSS dinamicamente para alterar o estado visual dos elementos na tela sem recarregar a página.

### Gestão de Estado e Lógica Condicional

- Criação de variáveis de contagem para acompanhar o progresso do usuário.
- Uso de estruturas condicionais (`if/else`) para determinar regras de negócio e condições de vitória.

---

## 4. ARQUITETURA E FUNCIONAMENTO DO PROJETO

### Jogo dos Sete Erros

#### Objetivo da Aplicação

Apresentar duas imagens quase idênticas e permitir que o jogador encontre as **7 diferenças**, clicando sobre a imagem modificada.

Ao encontrar todos os erros, o jogo deve contabilizar e exibir uma mensagem de vitória.

### Divisão de Responsabilidades

#### 1. HTML — Estrutura

- Contém o título do jogo e o placar/contador.
- Agrupa as duas imagens:
  - Original
  - Modificada
- Define áreas invisíveis de clique ("hotspots") posicionadas estrategicamente sobre cada um dos 7 erros da imagem modificada.

#### 2. CSS — Aparência e Posicionamento

- Define o layout lado a lado para comparação das imagens.
- Utiliza o sistema de posicionamento `relative/absolute` para fixar os pontos invisíveis de clique exatamente nas coordenadas dos erros.
- Estiliza os marcadores de erro, como um círculo vermelho com transparência, que aparece após o clique do usuário.
- Controla a visibilidade da mensagem de vitória.

#### 3. JavaScript — Regras de Negócio e Interatividade

- Captura todos os pontos de erro ("hotspots") da página.
- Adiciona um evento de clique a cada ponto.
- Quando um ponto válido é clicado:

  1. Adiciona uma classe CSS para tornar o marcador visualmente visível.
  2. Desativa novos cliques naquele mesmo ponto para evitar duplicação.
  3. Incrementa o contador de erros encontrados no placar.
  4. Avalia se o contador atingiu o total de 7 erros.

- Exibe a mensagem de vitória assim que a condição **7/7** for atingida.

---

## 5. PRINCIPAIS APRENDIZADOS E BOAS PRÁTICAS

### Posicionamento Absoluto Relativo ao Container

Para alinhar os cliques sobre uma imagem, o container pai deve ter posição `relative` e as áreas de clique devem ter posição `absolute`.

Exemplo:

```css
.container {
    position: relative;
}

.hotspot {
    position: absolute;
}
