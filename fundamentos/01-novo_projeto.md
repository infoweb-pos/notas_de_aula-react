# Criar um projeto novo, executar e ver resultado no navegador
- **Tema**: Fundamentos de React
- **Subtema**: Fundamentos - Criar um novo projeto

## Objetivos
- Criar um novo projeto javascript para uma aplicação web react usando o script vite

## Sumário
1. Criar um projeto novo
2. Executar o aplicativo web
3. Testar o aplicativo no navegador

### 1. Criar um projeto novo
1. Instalar o `node`, e `vs code`
2. Abrir o terminal de comandos
3. Executar o comando `npm create vite@latest`
   - Caso o script `vite` não esteja instalado ou esteje instalado uma versão desatualizada, o npm irá perguntar se deseja baixar o script, RESPONDA _y_ 
   - Aqui o aplicativo `npm` esta sendo executado para baixar e executar o script `vite`
   - O `npm` que verifica se está o script esta instalado e se a versão é a atualizada
   - tudo estando ok, ele transfere a execução para o script
   - o script `vite` que pergunta o nome do projeto, framework e linguagem do projeto
   - o script `vite` após as respostas, realiza
     - cria um diretório com o nome do projeto
     - copia uma série de arquivos de acordo com o framework e linguagem selecionados
   - o script `vite` finaliza informando quais os comandos necessário para executar a aplicação
5. Informar nome do projeto
6. Informar o framework e linaguagem utilizada, react e typescript respectivamente

### 2. Executar o aplicativo web
Ainda no terminal, executar os comandos que o script `vite` recomenda
1. `cd nome_do_projeto`
   - acessa o diretório (pasta) do projeto
3. `npm install`
   - executa o aplicativo `npm` com a opção `install`
   - a opção `install` tem alguns sinônimos como o `i`. Para ver mais opções, executar `npm i --help`
   - este comando com esta opção baixa as bibliotecas especificadas no arquivo `package.json`
5. `npm run dev`
   - executa o aplicativo `npm` com a opção `run` que executa um script definido no arquivo `package.json`
   - o script neste comando é o `dev` que executa a aplicação web react em modo desenvolvimento
   - se tudo estiver correto, ao final da execução o script `dev` informa o endereço de acesso da aplicação web react

### 3. Testar o aplicativo no navegador
1. a partir do terminal de comando, clicar com o botão direito no endereço informado pelo script `dev` e pedir para abrir o link
   - pode usar a tecla CTRL e clicar com o botão esquerdo
   - em ambos os casos, o terminal de comandos irá abrir o navegador padrão do sistema operacional e acessar o endereço da aplicação
   - caso deseje usar um outro navegador, pode copiar o endereço e acessar normalmente no navegador

## Links
- tutoriais
  - [Learn React - Quick start](https://react.dev/learn)
  - depreciado [Introdução a React](https://pt-br.legacy.reactjs.org/docs/getting-started.html)
- ferramentas
  - [Node](https://nodejs.org/en)
  - [React](https://react.dev/)
  - [TypeScript](https://www.typescriptlang.org/)
  - [Vite](https://vitejs.dev/)
  - [Visual Studio Code](https://code.visualstudio.com/)
