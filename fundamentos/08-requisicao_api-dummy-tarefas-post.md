# DummyAPI - Criando novas tarefas na API
- **Tema**: Fundamentos de React
- **Subtema**: Fundamentos - Requisições a API
- **código-fonte**: [github]() [zip]()

## Objetivos
- Adicionar uma página web a partir de lista de tarefas recebidos de requisições a API DummyJson

## Resumo
A partir do projeto iniciado no github, e registrado no releasse, montar uma 2a página com a lista de tarefas.

## Sumário
1. [Pegar projeto inicial]()
2. [Criar a página `src/paginas/PaginaTarefasNova.tsx` com o componente `PaginaTarefasNova`]()
3. []()



### 1. Pegar projeto inicial
**Fork**
1. Fork do [repositório github](https://github.com/infoweb-pos/2023-webapp-08-pratica_de_lab-dummy-01.git).
2. Clonar seu repositório remoto para o computador `git clone https://github.com/...`.
3. Mudar a _banch_ para `tarefas`, `git checkout tarefas`.
4. Abrir VSCode com a pasta do projeto localmente.
5. Abrir o terminal no VSCode e executar `npm install`.
6. Executar no terminal, após a instalação das bibliotecas, `npm run dev`.

**Baixar arquivo zipado**
1. baixar o [zip](https://github.com/infoweb-pos/2023-webapp-08-pratica_de_lab-dummy-01/archive/refs/tags/pagina-tarefas.zip).
2. Descompactar o arquivo zip localmente no seu computador
3. Abrir VSCode com a pasta do projeto localmente.
4. Abrir o terminal no VSCode e executar `npm install`.
5. Executar no terminal, após a instalação das bibliotecas, `npm run dev`.


### 2. Criar a página `src/paginas/PaginaTarefasNova.tsx` com o componente `PaginaTarefasNova`
1. Criar arquivo `src/pagina/PaginaTarefasNova.tsx`.
2. Criar um componente `PaginaTarefasNova` e exportar.

**arquivo** `src/pagina/PaginaTarefasNova.tsx`
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


### 3. Importar e usar `PaginaTarefasNova` em `App`
1. Abrir o arquivo `srv/App.tsx`.
2. Limpar os comentários da atividade passada.
3. Importar o componente `PaginaTarefasNova`.
4. Substituir no JSX `<PaginaTarefas />` por `<PaginaTarefasNova />`.
5. Apagar a importação do componente `PaginaTarefas`.

**arquivo** `srv/App.tsx`
```javascript
import './App.css'
import PaginaTarefasNova from './paginas/PaginaTarefasNova';

const App = () => {

  return (
    <>
      <PaginaTarefasNova />
    </>
  );
}

export default App

```


### 4. 
1. 

**arquivo** `src/pagina/PaginaTarefasNova.tsx`
```javascript
```



## Linnks
- [Dummy JSON](https://dummyjson.com/)
  - [Adicionar tarefas](https://dummyjson.com/docs/todos/#add)
