# DummyAPI - Usando dados de lista de tarefas a partir de requisições a API
- **Tema**: Fundamentos de React
- **Subtema**: Fundamentos - Requisições a API
- **código-fonte**: [github]() [zip]()

## Objetivos
- Adicionar uma página web a partir de lista de tarefas recebidos de requisições a API DummyJson

## Resumo

## Sumário
1. [Pegar projeto inicial](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas.md#1-pegar-projeto-inicial)
2. [Criar a página `src/paginas/PaginaTarefas.tsx` com o componente `PaginaTarefas`](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas.md#2-criar-a-p%C3%A1gina-srcpaginaspaginatarefastsx-com-o-componente-paginatarefas)
3. [Importar e usar `PaginaComponente` em `App`](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas.md#3-importar-e-usar-paginacomponente-em-app)
4. [Montar o html de 1 tarefa na página `PaginaTarefas`]()
5. [Criar um componente interno `TarefaItem`]()
6. []()
7. []()

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

### 6. 
1. 

```javascript

```

### 7. 
1. 

```javascript

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
