# DummyAPI - Usando dados de lista de usuários a partir de requisições a API
- **Tema**: Fundamentos de React
- **Subtema**: Fundamentos - Requisições a API
- **código-fonte**: [github](https://github.com/infoweb-pos/2023-webapp-08-pratica_de_lab-dummy-01) [zip](https://github.com/infoweb-pos/2023-webapp-08-pratica_de_lab-dummy-01/archive/refs/tags/pagina-inicial.zip)

## Objetivos
- Montar dados da interface web de lista de usuários a partir de dados recebidos de requisições a API DummyJson

## Resumo

## Sumário
1. [Criar o projeto, adicionar bibliotecas e limpar o código]()
2. [Criar o componente `AppNavBar` com o título da aplicação e adicionar instância em `App`]()
3. [Criar o componente `AppUsuarios` com uma lista de usuários e adicionar instância em `App`]()
4. [Transferir dados da lista para estado `usuarios` de `AppUsuarios`]()
5. [Montar o estado `usuarios` do componente `AppUsuarios` a partir de requisião a API]()
6. [Criar arquivo o arquivo `PaginaUsuarios.tsx` em `src/paginas` e copiar o componente `AppUsuarios`]()
7. [Usar o componente do arquivo `src/paginas/PaginaUsuarios.tsx` em `App`]()

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

  cd 08-01-requisicao_api-tarefas
  npm install
  npm run dev

$ cd 08-01-requisicao_api-tarefas

[08-01-requisicao_api-tarefas] $ npm install axios
added 218 packages, and audited 219 packages in 33s

40 packages are looking for funding
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
import "./App.css";

const App = () => {
	return <></>;
};

export default App;

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
			<h1>Dummy API</h1>
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

### 3. Criar o componente `AppUsuarios` com uma lista de usuários e adicionar instância em `App`
1. 

```javascript

```

### 4. Transferir dados da lista para estado `usuarios` de `AppUsuarios
1. 

```javascript

```

### 5. Montar o estado `usuarios` do componente `AppUsuarios` a partir de requisião a API
1. 

```javascript

```

### 6. Criar arquivo o arquivo `PaginaUsuarios.tsx` em `src/paginas` e copiar o componente `AppUsuarios`
1. 

```javascript

```

### 7. Usar o componente do arquivo `src/paginas/PaginaUsuarios.tsx` em `App`
1. 

```javascript

```

## Linnks
- [Dummy JSON](https://dummyjson.com/)
