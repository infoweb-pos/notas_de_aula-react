# Fundamentos - Elevando estado para compartilhar dados entre componentes

Objetivos:
(i) Rever eventos em HTML
(ii) Criar um componente React com 2 propriedades (string e function)

Resumo
1. Criar uma aplicação
- criar a aplicação com npm
- npm create vite@latest
  - npm vai verificar se existe o script vite e se esta atualizado
  - caso não exista, ou esteja desatualizado, perguntará se deseja baixar
  - responda Y
- defina o nome do projeto, que também será o nome do diretório (pasta)
- framework React e linguagem TypeScript
- projeto criado, agora temos de executar
- siga os comandos, acessar diretório, baixar bibliotecas, executar a aplicação
- npm i é igual a npm install
- antes de executar, lembre de abrir o vs code, onde iremos modificar os códigos
- agora sim, executar a aplicação e abrir no navegador
2. Criar um componente react botão
- aplicação funcionando, vamos limpar e criar o componente react para o botão
- abrir o arquivo App.tsx
- arquivo limpo
- criaremos agora um componente e adicionaremos na aplicação
3. Programa o onClick genérico
- antes de programar o click, vamos abrir o console do navegador
- vamos programar o evento onclick
- a cada click, aparece a mensagem no log
- vamos agora pro próximo
4. Criar uma propriedade com título do botão
- adicionar no componente o parâmetro props
- adicionar a propriedade titulo tanto no componente quanto na chamada do componente
- vamos agora adicionar mais 2 botões
- os clicks deram o mesmo resultado, e isso muitas vezes não é o que queremos num app de verdade
- próximo passo
5. Criar uma propriedade que recebe em seu valor uma função
- criada as 3 funções, passemos como parâmetro na chamada aos componentes
- agora vamos substituir a função de tratamento do onClick
- no lugar de onClick={tratarEvento}
- ficará onClick={funcao}
tudo testado
dúvidas, publicar :-D

referências:
- https://react.dev/learn
- PT-BR https://developer.mozilla.org/pt-BR/docs/Web/API/Element/click_event
- EN https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event
