# DummyAPI - Usando dados de lista de tarefas a partir de requisições a API
- **Tema**: Fundamentos de React
- **Subtema**: Fundamentos - Requisições a API
- **código-fonte**: [github]() [zip]()

## Objetivos
- Adicionar uma página web a partir de lista de tarefas recebidos de requisições a API DummyJson

## Resumo

## Sumário
1. [Pegar projeto inicial]()
2. [Criar a página `src/paginas/PaginaTarefas.tsx` com o componente `PaginaTarefas`]()
3. [Importar e usar `PaginaComponente` em `App`]()
4. []()
5. []()
6. [Criar arquivo o arquivo `PaginaUsuarios.tsx` em `src/paginas` e copiar o componente `AppUsuarios`]()
7. [Usar o componente do arquivo `src/paginas/PaginaUsuarios.tsx` em `App`]()

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

### 4. 
1. 

```javascript

```

### 5. 
1. 

```javascript

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
