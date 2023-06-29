# Usando dados a partir de requisições a API com métodos GET, POST, PUT, DELETE
- **Tema**: Fundamentos de React
- **Subtema**: Fundamentos - Requisições a API com métodos GET, POST, PUT, DELETE
- **código-fonte**: gtihub zip

## Objetivos
- Programar o ciclo do CRUD com requisições a API

## Resumo
Será criado um projeto javascript de uma aplicação web com o framework React e a 
linguagem de programação TypeScript usando o aplicativo npm e o script vite.
FIXME O aplicativo web será encapsulado no componente React `App` que conterá componentes: AppNavBar com um título; 
e AppTarefas, com um botão e uma lista de tarefas.
O botão de AppTarefas será o responsável por atualizar a lista de tarefas a partir de requisição a API.

## Sumário
1. Criar o projeto, adicionar bibliotecas e limpar o código
2. Criar o componente `AppNavBar` com o título da aplicação e adicionar instância em `App`
3. Criar o componente `AppTarefas` com uma lista de tarefas e adicionar instância em `App`
4. Criar o componente `AppTarefa` para edição de 1 tarefa e adicionar instância em `App`
5. 
6. 

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
✔ Project name: … 08-02-requisicao_api-tarefas
✔ Select a framework: › React
✔ Select a variant: › TypeScript

Scaffolding project in /home/minora/minora/2023-pos/08-02-requisicao_api-tarefas...

Done. Now run:

  cd 08-02-requisicao_api-tarefas
  npm install
  npm run dev

$ cd 08-02-requisicao_api-tarefas

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
1. Criar uma constante para o componente `AppNavBar`
2. Adicionar um botão e uma lista com as tarefas em `AppNavBar`
3. Adicioanar uma instância do componente `AppNavBar` em `App`

```javascript
import "./App.css";

const AppNavBar = () => {
	return (
		<div className="card">
			<h1>Lista de tarefas (apenas leitura)</h1>
		</div>
	);
};

const AppTarefas = () => {
	return (
		<div className="card">
			<button>Pegar tarefas</button>
			<ul>
				<li>
					Criar o projeto, adicionar bibliotecas e limpar o código
				</li>
				<li>
					Criar o componente AppNavBar com o título da aplicação e
					adicionar instância em App
				</li>
				<li>
					Criar o componente AppTarefas com uma lista de tarefas e
					adicionar instância em App
				</li>
				<li>
					Transferir dados da lista para estado tarefas de AppTarefas
				</li>
				<li>
					Montas o estado tarefas do componente AppTarefas a partir de
					requisião a API
				</li>
			</ul>
		</div>
	);
};

const App = () => {
	return (
		<>
			<AppNavBar />
			<AppTarefas />
		</>
	);
};

export default App;

```

### 4. Transferir dados da lista para estado `tarefas` de `AppTarefas`
1. Criar o estado `tarefas` em `AppTarefas` com valor inicial `[]`.
2. Para cada `li` copiar e colar como string no valor inicial do estado `tarefas`.
3. Substituir os `li` com valores estáticos por mapa gerada a partir do estado `tarefas`.

```javascript
import { useState } from "react";
import "./App.css";

const AppNavBar = () => {
	return (
		<div className="card">
			<h1>Lista de tarefas (apenas leitura)</h1>
		</div>
	);
};

const AppTarefas = () => {
	const [tarefas, setTarefas] = useState([
		"Criar o projeto, adicionar bibliotecas e limpar o código",
		"Criar o componente AppNavBar com o título da aplicação e adicionar instância em App",
		"Criar o componente AppTarefas com uma lista de tarefas e adicionar instância em App",
		"Transferir dados da lista para estado tarefas de AppTarefas",
		"Montas o estado tarefas do componente AppTarefas a partir de requisião a API",
	]);

	return (
		<div className="card">
			<button>Pegar tarefas</button>
			<ul>
				{tarefas.map((tarefa: string, indice: number) => (
					<li key={indice}>{tarefa}</li>
				))}
			</ul>
		</div>
	);
};

const App = () => {
	return (
		<>
			<AppNavBar />
			<AppTarefas />
		</>
	);
};

export default App;

```

### 5. Montas o estado `tarefas` do componente `AppTarefas` a partir de requisião a API
1. Criar a função de seta (_arrow function_) `tratarClique` com um "alô mundo" no log em `AppTarefas`.
2. Adicionar o evento `onClick={tratarClique}` no `button` em `AppTarefas`.
3. Importar e configurar o `axios` para acessar a URL https://infoweb-api.vercel.app/.
4. Colocar o "alô mundo" dentro da chamada `axios.get().then()`.
5. Substituir o "Alô mundo" pela resposta da chamada ao GET `console.info(response.data);`.
6. Criar uma nova lista mapeando apenas os títulos das tarefas recebidas em `response.data.data`.
7. Atribuir a nova lista ao estado `tarefas`, `setTarefas(lista)`.
8. Colocar valor inicial do estado `tarefas` com `[]`.

```javascript
import { useState } from "react";
import "./App.css";
import axios from "axios";

const api = axios.create({
	baseURL: "https://infoweb-api.vercel.app/",
});

const AppNavBar = () => {
	return (
		<div className="card">
			<h1>Lista de tarefas (apenas leitura)</h1>
		</div>
	);
};

const AppTarefas = () => {
	const [tarefas, setTarefas] = useState([]);

	const tratarClique = () => {
		api.get("tarefas").then((response) => {
			console.info(response.data);
			const lista = response.data.data.map((item: any) =>  item.titulo);
			console.info(lista);
			setTarefas(lista);
		});
	};
	return (
		<div className="card">
			<button onClick={tratarClique}>Pegar tarefas</button>
			<ul>
				{tarefas.map((tarefa: string, indice: number) => (
					<li key={indice}>{tarefa}</li>
				))}
			</ul>
		</div>
	);
};

const App = () => {
	return (
		<>
			<AppNavBar />
			<AppTarefas />
		</>
	);
};

export default App;

```


## Linnks
- Ferramentas e bibliotecas
  - [axios js](https://axios-http.com/)
- Tutoriais
  - [Consumindo uma API com React.JS e Axios](https://www.devmedia.com.br/consumindo-uma-api-com-react-js-e-axios/42900)
  - [Guia inicial do axios js](https://axios-http.com/ptbr/docs/intro)
- Vídeos tutoriais
  - [React, Material UI 5 e Typescript: #20 - Como configurar o axios no React](https://youtu.be/t0RjS2aNgus)
