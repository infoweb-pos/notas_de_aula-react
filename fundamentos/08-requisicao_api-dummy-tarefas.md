# DummyAPI - Usando dados de lista de tarefas a partir de requisições a API
- **Tema**: Fundamentos de React
- **Subtema**: Fundamentos - Requisições a API
- **código-fonte**: [github](https://github.com/infoweb-pos/2023-webapp-08-pratica_de_lab-dummy-01/tree/tarefas) [zip]()

## Objetivos
- Adicionar uma página web a partir de lista de tarefas recebidos de requisições a API DummyJson

## Resumo

## Sumário
1. [Pegar projeto inicial](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas.md#1-pegar-projeto-inicial)
2. [Criar a página `src/paginas/PaginaTarefas.tsx` com o componente `PaginaTarefas`](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas.md#2-criar-a-p%C3%A1gina-srcpaginaspaginatarefastsx-com-o-componente-paginatarefas)
3. [Importar e usar `PaginaComponente` em `App`](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas.md#3-importar-e-usar-paginacomponente-em-app)
4. [Montar o html de 1 tarefa na página `PaginaTarefas`](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas.md#4-montar-o-html-de-1-tarefa-na-p%C3%A1gina-paginatarefas)
5. [Criar um componente interno `TarefaItem`](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas.md#5-criar-um-componente-interno-tarefaitem)
6. [Mudar de constante `tarefa` para estado `tarefas`](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas.md#6-mudar-de-constante-tarefa-para-estado-tarefas)
7. [Mudar de 1 tarefa para mapa da lista de tarefas do estado `tarefas`](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas.md#7-mudar-de-1-tarefa-para-mapa-da-lista-de-tarefas-do-estado-tarefas)
8. [Inicializar estado com requisição a API DummyJson](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas.md#8-inicializar-estado-com-requisi%C3%A7%C3%A3o-a-api-dummyjson)

### 1. Pegar projeto inicial
**Fork**
1. Fork do [repositório github](https://github.com/infoweb-pos/2023-webapp-08-pratica_de_lab-dummy-01.git).
2. Clonar seu repositório remoto para o computador `git clone https://github.com/...`.
3. Abrir VSCode com a pasta do projeto localmente.
4. Abrir o terminal no VSCode e executar `npm install`.
5. Executar no terminal, após a instalação das bibliotecas, `npm run dev`.

**Baixar arquivo zipado**
1. baixar o [zip](https://github.com/infoweb-pos/2023-webapp-08-pratica_de_lab-dummy-01/archive/refs/tags/pagina-inicial.zip).
2. Descompactar o arquivo zip localmente no seu computador
3. Abrir VSCode com a pasta do projeto localmente.
4. Abrir o terminal no VSCode e executar `npm install`.
5. Executar no terminal, após a instalação das bibliotecas, `npm run dev`.

### 2. Criar a página `src/paginas/PaginaTarefas.tsx` com o componente `PaginaTarefas`
1. Criar arquivo `src/pagina/PaginaTarefas.tsx`.
2. Criar um componente `PaginaTarefas` e exportar.

**arquivo** `src/pagina/PaginaTarefas.tsx`
```javascript
const PaginaTarefas = () => {
	return (
		<div className="card">
			<h2>Lista de tarefas</h2>
		</div>
	);
};

export default PaginaTarefas;

```

### 3. Importar e usar `PaginaComponente` em `App`
1. Abrir o arquivo `srv/App.tsx`.
2. Limpar os comentários da atividade passada.
3. Importar o componente `PaginaTarefas`.
4. Substituir no JSX `<AppUsuarios />` por `<PaginaTarefas />`.
5. Apagar a importação do componente `AppUsuarios`.

**arquivo** `srv/App.tsx`
```javascript
import './App.css'
import PaginaTarefas from './paginas/PaginaTarefas';

const App = () => {

  return (
    <>
      <PaginaTarefas />
    </>
  );
}

export default App

```

### 4. Montar o html de 1 tarefa na página `PaginaTarefas`
1. Abrir o arquivo `src/pagina/PaginaTarefas.tsx`.
2. Criar uma constante `tarefa` com um objeto _json_.
3. Criar um html do tipo checkbox para a constante `tarefa`.

**arquivo** `src/pagina/PaginaTarefas.tsx`
```javascript
const PaginaTarefas = () => {
	const tarefa = {
		id: 1,
		todo: "codificar requisições a api dummy json",
		completed: false,
		userId: 1,
	};

	return (
		<div className="card">
			<h2>Lista de tarefas</h2>
			<div className="card">
				<label>
					<input
						type="checkbox"
						name={`${tarefa.id}`}
						checked={tarefa.completed}
					/>
					{tarefa.todo}
				</label>
			</div>
		</div>
	);
};

export default PaginaTarefas;

```

### 5. Criar um componente interno `TarefaItem`
1. Ainda editando o arquivo `src/pagina/PaginaTarefas.tsx`.
3. Criar o componente interno `TarefaItem`.
4. Criar a interface `propsTarefa` e tipar o `props` do componente `TarefaItem`.
5. Copiar o html de tarefa do JSX da `PaginaTarefa` para `TarefaItem`.
6. Substituir no JSX de `TarefaItem` de `tarefa.id` por `props.id`.
7. Substituir no JSX de `TarefaItem` de `tarefa.todo` por `props.titulo`.
8. Substituir no JSX de `TarefaItem` de `tarefa.completed` por `props.feito`.
9. Substituir no JSX de `PaginaTarefa` os códigos html pelo componente `TarefaItem`.

**arquivo** `src/pagina/PaginaTarefas.tsx`
```javascript
interface propsTarefa {
	id: number;
	titulo: string;
	feito: boolean;
}

const TarefaItem = (props: propsTarefa) => {
	return (
		<div className="card">
			<label>
				<input
					type="checkbox"
					name={`${props.id}`}
					checked={props.feito}
				/>
				{props.titulo}
			</label>
		</div>
	);
};

const PaginaTarefas = () => {
	const tarefa = {
		id: 1,
		todo: "codificar requisições a api dummy json",
		completed: false,
		userId: 1,
	};

	return (
		<div className="card">
			<h2>Lista de tarefas</h2>
			<TarefaItem
				id={tarefa.id}
				titulo={tarefa.todo}
				feito={tarefa.completed}
			/>
		</div>
	);
};

export default PaginaTarefas;

```

### 6. Mudar de constante `tarefa` para estado `tarefas`
1. Ainda editando o arquivo `src/pagina/PaginaTarefas.tsx`.
2. Criar o estado `tarefas` e inicializar com uma lista vazia.
3. Copiar o valor de `tarefa` como o item 1 do estado `tarefas` no valor inicial.
4. No JSX de `PaginaTarefa`, onde tiver `tarefa` modificar para `tarefas[0]`.
5. Apagar a constante `tarefa`.

**arquivo** `src/pagina/PaginaTarefas.tsx`
```javascript
import { useState } from "react";

interface propsTarefa {
	id: number;
	titulo: string;
	feito: boolean;
}

const TarefaItem = (props: propsTarefa) => {
	return (
		<div className="card">
			<label>
				<input
					type="checkbox"
					name={`${props.id}`}
					checked={props.feito}
				/>
				{props.titulo}
			</label>
		</div>
	);
};

const PaginaTarefas = () => {
	const [tarefas] = useState([
		{
			id: 1,
			todo: "codificar requisições a api dummy json",
			completed: false,
			userId: 1,
		},
	]);

	return (
		<div className="card">
			<h2>Lista de tarefas</h2>
			<TarefaItem
				id={tarefas[0].id}
				titulo={tarefas[0].todo}
				feito={tarefas[0].completed}
			/>
		</div>
	);
};

export default PaginaTarefas;

```

### 7. Mudar de 1 tarefa para mapa da lista de tarefas do estado `tarefas`
1. Ainda editando o arquivo `src/pagina/PaginaTarefas.tsx`.
2. No JSX de `PaginaTarefas`, acima de `<TarefaItem ...`, inserir `{tarefas.map(tarefa => )}`.
3. Mover o código de `<TarefaItem...` para dentro do mapenamento `{tarefas.map(tarefa => )}`.
4. Soliciar ao VSCode para formatar o arquivo.
5. Em `<TarefaItem...`, substituir `tarefas[0]` por `tarefa`.
6. Em `<TarefaItem...`, por ser uma lista, adicionar a propriedade `key={tarefa.id}`.

**arquivo** `src/pagina/PaginaTarefas.tsx`
```javascript
import { useState } from "react";

interface propsTarefa {
	id: number;
	titulo: string;
	feito: boolean;
}

const TarefaItem = (props: propsTarefa) => {
	return (
		<div className="card">
			<label>
				<input
					type="checkbox"
					name={`${props.id}`}
					checked={props.feito}
				/>
				{props.titulo}
			</label>
		</div>
	);
};

const PaginaTarefas = () => {
	const [tarefas] = useState([
		{
			id: 1,
			todo: "codificar requisições a api dummy json",
			completed: false,
			userId: 1,
		},
	]);

	return (
		<div className="card">
			<h2>Lista de tarefas</h2>
			{tarefas.map((tarefa) => (
				<TarefaItem
					key={tarefa.id}
					id={tarefa.id}
					titulo={tarefa.todo}
					feito={tarefa.completed}
				/>
			))}
		</div>
	);
};

export default PaginaTarefas;

```

### 8. Inicializar estado com requisição a API DummyJson
1. Ainda editando o arquivo `src/pagina/PaginaTarefas.tsx`.
2. Colocar o valor `[]` no valor inicial do estado `tarefas`.
3. Colocar o método `setTarefas` para modificar valor do estado `tarefas`.
4. Vai reclamar do tipo em `tarefas.map`, criar nova _interface_ `jsonTarefa` conforme _json_ resultado da API.
5. Importar o `axios` e criar uma instância `api` com `axios.create`. Lembrar de colocar `baseUrl`.
6. Criar o código para inicializar o estado `tarefas`.
7. Apesar de funcionar, o VS Code reclama o tipo da chamada `get` esta sem tipo. Crie uma nova interface `jsonDeRespostaDoGet` e tipe a chamada `get`.

**arquivo** `src/pagina/PaginaTarefas.tsx`
```javascript
import axios from "axios";
import { useEffect, useState } from "react";

const api = axios.create({
	baseURL: "https://dummyjson.com/",
});

interface propsTarefa {
	id: number;
	titulo: string;
	feito: boolean;
}

interface jsonTarefa {
	id: number;
	todo: string;
	completed: boolean;
	userId: number;
}

interface jsonDeRespostaDoGet {
	todos: [];
	total: number;
	skip: number;
	limit: number;
}

const TarefaItem = (props: propsTarefa) => {
	return (
		<div className="card">
			<label>
				<input
					type="checkbox"
					name={`${props.id}`}
					checked={props.feito}
				/>
				{props.titulo}
			</label>
		</div>
	);
};

const PaginaTarefas = () => {
	const [tarefas, setTarefas] = useState([]);

	useEffect(() => {
		api.get<jsonDeRespostaDoGet>("/todos?limit=10").then((resposta) =>
			setTarefas(resposta.data.todos)
		).catch((erro: any) => console.error(erro));
	}, []);

	return (
		<div className="card">
			<h2>Lista de tarefas</h2>
			{tarefas.map((tarefa: jsonTarefa) => (
				<TarefaItem
					key={tarefa.id}
					id={tarefa.id}
					titulo={tarefa.todo}
					feito={tarefa.completed}
				/>
			))}
		</div>
	);
};

export default PaginaTarefas;

```


## Linnks
- [Dummy JSON](https://dummyjson.com/)
- Tipando `props` em React/Typescript
  - [Tipando props no React](https://www.ninjadevspace.com.br/post/tipando-props-react)
  - [Trabalhando com Componentização no React + Typescript.](https://medium.com/reactbrasil/trabalhando-com-componentiza%C3%A7%C3%A3o-no-react-typescript-e0aa8f5de5db)
  - Typescript - docs - JSX - [Function Component](https://www.typescriptlang.org/pt/docs/handbook/jsx.html#function-component)
- Inicializando estado num componente React
  - You Might Not Need an Effect - [Initializing the application](https://react.dev/learn/you-might-not-need-an-effect#initializing-the-application)
  - [Usando Effect Hook (Hook de Efeito)](https://pt-br.legacy.reactjs.org/docs/hooks-effect.html)
- axios e Typescript
  - [How to use Axios with TypeScript when using response interceptors (AxiosResponse issue)](https://github.com/axios/axios/issues/1510)
  - [Axios Response in TypeScript](https://www.delftstack.com/howto/typescript/axios-typescript/#google_vignette)
