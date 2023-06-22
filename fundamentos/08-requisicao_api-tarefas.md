# Usando dados a partir de requisições a API
- **Tema**: Fundamentos de React
- **Subtema**: Fundamentos - Requisições a API
- **código-fonte**: 

## Objetivos
- Montar dados da interface a partir de dados recebidos de requisições a API

## Resumo
Será criado um projeto javascript de uma aplicação web com o framework React e a 
linguagem de programação TypeScript usando o aplicativo npm e o script vite.
O aplicativo web será encapsulado no componente React `App` que conterá componentes: AppNavBar com um título; 
e AppTarefas, com um botão e uma lista de tarefas.
O botão de AppTarefas será o responsável por atualizar a lista de tarefas a partir de requisição a API.

## Sumário
1. Criar o projeto, adicionar bibliotecas e limpar o código
2. Criar o componente `AppNavBar` com o título da aplicação e adicionar instância em `App`
3. Criar o componente `AppTarefas` com uma lista de tarefas e adicionar instância em `App`
4. Transferir dados da lista para estado `tarefas` de `AppTarefas`
5. Montas o estado `tarefas` do componente `AppTarefas` a partir de requisião a API

### 1. Criar o projeto, adicionar bibliotecas e limpar o código
1. Abrir o terninal de comandos
2. Criar projeto novo com React e TypeScript
3. Entrar no diretório do projeto, instalar bibliotecas e executar aplicativo
4. Executar o visual studio code e abrir diretório do projeto
5. Editar o arquivo `src/App.tsx`
6. Abrir o navegador e acessar a url http://localhost:5173/

**terminal de comandos**
```console
$ npm create vite@latest
✔ Project name: … 08-01-requisicao_api-tarefas
✔ Select a framework: › React
✔ Select a variant: › TypeScript

Scaffolding project in /home/minora/minora/2023-pos/08-01-requisicao_api-tarefas...

Done. Now run:

  cd 07-02-elevacao_de_estado-tarefas
  npm install
  npm run dev

$ cd 08-01-requisicao_api-tarefas

[08-01-requisicao_api-tarefas] $ npm install axios
added 209 packages, and audited 210 packages in 15s

39 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

[08-01-requisicao_api-tarefas] $ npm run dev
 VITE v4.3.9  ready in 400 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
  ➜  press h to show help

```

**arquivo** `src/App.tsx`
```javascript
import './App.css'

const App = () => {

  return (
    <>
    </>
  )
}

export default App

```

### 2. Criar o componente `AppNavBar` com o título da aplicação e adicionar instância em `App`

1. Criar uma constante para o componente `AppNavBar`
2. Adicioanar uma instância do componente `AppNavBar` em `App`

**arquivo** `src/App.tsx`
```javascript
import "./App.css";

const AppNavBar = () => {
	return (
		<div className="card">
			<h1>Lista de tarefas (apenas leitura)</h1>
		</div>
	);
};

const App = () => {
	return (
		<>
			<AppNavBar />
		</>
	);
};

export default App;

```

### 3. Criar o componente `AppTarefas` com uma lista de tarefas e adicionar instância em `App`

### 4. Transferir dados da lista para estado `tarefas` de `AppTarefas`

### 5. Montas o estado `tarefas` do componente `AppTarefas` a partir de requisião a API



## Linnks
- Ferramentas e bibliotecas
  - [axios js](https://axios-http.com/)
- Tutoriais
  - [Consumindo uma API com React.JS e Axios](https://www.devmedia.com.br/consumindo-uma-api-com-react-js-e-axios/42900)
  - [Guia inicial do axios js](https://axios-http.com/ptbr/docs/intro)
- Vídeos tutoriais
  - [React, Material UI 5 e Typescript: #20 - Como configurar o axios no React](https://youtu.be/t0RjS2aNgus)
