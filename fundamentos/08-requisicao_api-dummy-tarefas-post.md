# DummyAPI - Criando novas tarefas na API
- **Tema**: Fundamentos de React
- **Subtema**: Fundamentos - Requisições a API
- **código-fonte**: [github]() [zip]()

## Objetivos
- Adicionar uma página web a partir de lista de tarefas recebidos de requisições a API DummyJson

## Resumo
A partir do projeto iniciado no github, e registrado no releasse, montar uma 2a página com a lista de tarefas.

## Sumário
1. [Pegar projeto inicial](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas-post.md#1-pegar-projeto-inicial)
2. [Criar a página `src/paginas/PaginaTarefasNova.tsx` com o componente `PaginaTarefasNova`](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/08-requisicao_api-dummy-tarefas-post.md#2-criar-a-p%C3%A1gina-srcpaginaspaginatarefasnovatsx-com-o-componente-paginatarefasnova)
3. [Importar e usar `PaginaTarefasNova` em `App`]()
4. [Montar página com texto para criar nova tarefa]()
5. [Criar estado com texto e conectar ao html da página]()
6. [Criar uma função para o evento onClick que construa o objeto json]()



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
			<h3>Tarefa nova</h3>
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


### 4. Montar página com texto para criar nova tarefa
1. Abrir o arquivo `src/pagina/PaginaTarefasNova.tsx`.
2. Inserir o html para um texto e um botão no JSX.

**arquivo** `src/pagina/PaginaTarefasNova.tsx`
```javascript
const PaginaTarefasNova = () => {
    return (
        <div className="card">
            <h2>Lista de tarefas</h2>
			<h3>Tarefa nova</h3>
            <div>
                <label>
                    Tarefa:&nbsp;
                    <input type="text"></input>
                </label>
                <button>Criar nova tarefa</button>
            </div>
        </div>
    );
}

export default PaginaTarefasNova;

```


### 5. Criar estado com texto e conectar ao html da página
1. Ainda no arquivo `src/pagina/PaginaTarefasNova.tsx`.
2. Criar estado `tarefa` e a função `setTarefa` com valor inicial de texto em branco.
3. Colocar no html `input` a propriedade `value={tarefa}`.
4. Colocar no html `input` a propriedade `onChange`. Apesar do erro no VS Code, irá funcionar.

**arquivo** `src/pagina/PaginaTarefasNova.tsx`
```javascript
import { useState } from "react";

const PaginaTarefasNova = () => {
	const [tarefa, setTarefa] = useState("");

	return (
		<div className="card">
			<h2>Lista de tarefas</h2>
			<h3>Tarefa nova</h3>
			<div>
				<label>
					Tarefa:&nbsp;
					<input
						type="text"
						value={tarefa}
						onChange={(evento: React.FormEvent<HTMLInputElement>) =>
							setTarefa(evento.target.value)
						}
					></input>
				</label>
				<button>Criar nova tarefa</button>
			</div>
		</div>
	);
};

export default PaginaTarefasNova;

```

### 6. Criar uma função para o evento onClick que construa o objeto json
1. Ainda no arquivo `src/pagina/PaginaTarefasNova.tsx`.
2. 

**arquivo** `src/pagina/PaginaTarefasNova.tsx`
```javascript
```


## Linnks
- [Dummy JSON](https://dummyjson.com/)
  - [Adicionar tarefas](https://dummyjson.com/docs/todos/#add)
