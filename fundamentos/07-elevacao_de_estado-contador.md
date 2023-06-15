# Compartilhando estado entre componentes com elevação de estado (lifiting state)
- **Tema**: Fundamentos de React
- **Subtema**: Fundamentos - Compartilhar estado entre componentes com elevação de estado
- **código-fonte**: [github](https://github.com/infoweb-pos/07-01-elevacao_de_estado-contador) [zip](https://github.com/infoweb-pos/07-01-elevacao_de_estado-contador/archive/refs/tags/2023.zip)

## Objetivos
- Criar componentes que compartilham estado do componente pai

## Resumo
Será criado um projeto javascript de uma aplicação web com o framework React e a 
linguagem de programação TypeScript usando o aplicativo npm e o script vite.
O aplicativo web será encapsulado no componente React `App` que conterá um título 
e 3 botões.
O título será usando `html` enquanto que os botões serão componentes React nomeados 
como `MeuBotao`.
Ao final espera que o componente `App` tenha um contador que é compartilhado 
com as instâncias de `MeuBotao` além de um contador individual por instância 
de `MeuBotao`.

## Sumário
1. [Criar o projeto e limpar o código](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/07-elevacao_de_estado-contador.md#1-criar-o-projeto-e-limpar-o-c%C3%B3digo)
2. [Criar o componente MeuBotao e adicionar 3 instâncias no Aplicativo](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/07-elevacao_de_estado-contador.md#2-criar-o-componente-meubotao-e-adicionar-3-inst%C3%A2ncias-no-aplicativo)
3. [Personalizar o título de MeuBotao](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/07-elevacao_de_estado-contador.md#3-personalizar-o-t%C3%ADtulo-de-meubotao)
4. [Adicionar contador ao MeuBotao como estado](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/07-elevacao_de_estado-contador.md#4-adicionar-contador-ao-meubotao-como-estado)
5. [Elevar o estado contador de MeuBotao para o Aplicativo](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/07-elevacao_de_estado-contador.md#5-elevar-o-estado-contador-de-meubotao-para-o-aplicativo)
6. [Incrementar o contador do componente App](https://github.com/infoweb-pos/react-notas_de_aula/blob/main/fundamentos/07-elevacao_de_estado-contador.md#6-incrementar-o-contador-do-componente-app)

### 1. Criar o projeto e limpar o código

1. Abrir o terninal de comandos
2. Criar projeto novo com React e TypeScript
3. Entrar no diretório do projeto, instalar bibliotecas e executar aplicativo
4. Executar o visual studio code e abrir diretório do projeto
5. Editar o arquivo `src/App.tsx`
6. Abrir o navegador e acessar a url http://localhost:5173/

**terminal de comandos**
```console
$ npm create vite@latest
✔ Project name: … 07-01-elevacao_de_estado-contador
✔ Select a framework: › React
✔ Select a variant: › TypeScript

Scaffolding project in /home/minora/minora/2023-pos/07-01-elevacao_de_estado-contador...

Done. Now run:

  cd 07-01-elevacao_de_estado-contador
  npm install
  npm run dev

$ cd 07-01-elevacao_de_estado-contador

[07-01-elevacao_de_estado-contador] $ npm install
added 209 packages, and audited 210 packages in 15s

39 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

[07-01-elevacao_de_estado-contador] $ npm run dev
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
      <h1>Aplicativo exemplo de elevação de estado</h1>
    </>
  )
}

export default App
```

### 2. Criar o componente MeuBotao e adicionar 3 instâncias no Aplicativo
1. Criar o componente MeuBotao com um `button` html com um texto padrão
2. Adicionar 3 instâncias do componente MeuBotao no componente App

**arquivo** `src/App.tsx`
```javascript
import './App.css'

const  MeuBotao = () => {
  return (
    <button>Meu componente botão</button>
  );
}

const App = () => {
  return (
    <>
      <h1>Aplicativo exemplo de elevação de estado</h1>
      <MeuBotao />
      <MeuBotao />
      <MeuBotao />
    </>
  )
}

export default App;

```

### 3. Personalizar o título de MeuBotao
1. Adicionar a propriedade `titulo` nas instâncias de MeuBotao
2. Adicionar `props: any` no componente MeuBotao
3. Substituir a string fixa `Meu componente botão` de button por `{props.titulo}`

**arquivo** `src/App.tsx`
```javascript
import "./App.css";

const MeuBotao = (props: any) => {
	return <button>{props.titulo}</button>;
};

const App = () => {
	return (
		<>
			<h1>Aplicativo exemplo de elevação de estado</h1>
			<MeuBotao titulo={"Contador de bom dia"} />
			<MeuBotao titulo={"Contador de boa tarde"} />
			<MeuBotao titulo={"Contador de boa noite"} />
		</>
	);
};

export default App;
```

### 4. Adicionar contador ao MeuBotao como estado
1. Adicionar o estado `contador` no componente MeuBotao 
2. Adicionar uma função anônima no evento `onClick` para incrementar contador
3. Substituir a função anônima por uma variável constante no evento `onClick`

**arquivo** `src/App.tsx` **1a versão com função anônima para tratar o onClick**
```javascript
import { useState } from "react";
import "./App.css";

const MeuBotao = (props: any) => {
	const [contador, setContador] = useState(0);

	return (
		<button onClick={() => setContador(contador + 1)}>
			{props.titulo} {contador}
		</button>
	);
};

const App = () => {
	return (
		<>
			<h1>Aplicativo exemplo de elevação de estado</h1>
			<MeuBotao titulo={"Contador de bom dia"} />
			<MeuBotao titulo={"Contador de boa tarde"} />
			<MeuBotao titulo={"Contador de boa noite"} />
		</>
	);
};

export default App;
```

**arquivo** `src/App.tsx` **2a versão com substituição da função anônima por uma variável constante no onClick**
```javascript
import { useState } from "react";
import "./App.css";

const MeuBotao = (props: any) => {
	const [contador, setContador] = useState(0);
	const tratarOnClick = () => setContador(contador + 1);

	return (
		<button onClick={tratarOnClick}>
			{props.titulo} {contador}
		</button>
	);
};

const App = () => {
	return (
		<>
			<h1>Aplicativo exemplo de elevação de estado</h1>
			<MeuBotao titulo={"Contador de bom dia"} />
			<MeuBotao titulo={"Contador de boa tarde"} />
			<MeuBotao titulo={"Contador de boa noite"} />
		</>
	);
};

export default App;
```

### 5. Elevar o estado contador de MeuBotao para o Aplicativo
1. Adicionar o estado `contador` ao componente `App`
2. Adicionar a propriedade `contador={contador}` nas instâncias de MeuBotao em `App`
3. Adicionar `props.contador` no título de `button` no componente MeuBotao

**arquivo** `src/App.tsx`
```javascript
import { useState } from "react";
import "./App.css";

const MeuBotao = (props: any) => {
	const [contador, setContador] = useState(0);
	const tratarOnClick = () => setContador(contador + 1);

	return (
		<button onClick={tratarOnClick}>
			{props.titulo} {contador} ({props.contador})
		</button>
	);
};

const App = () => {
	const [contador, setContador] = useState(0);

	return (
		<>
			<h1>Aplicativo exemplo de elevação de estado</h1>
			<MeuBotao
				titulo={"Contador de bom dia"}
				contador={contador}
			/>
			<MeuBotao
				titulo={"Contador de boa tarde"}
				contador={contador}
			/>
			<MeuBotao
				titulo={"Contador de boa noite"}
				contador={contador}
			/>
		</>
	);
};

export default App;
```

### 6. Incrementar o contador do componente App
1. Criar uma constante com a função de incrementar contador de `App`, `contarEmApp`
2. Adicionar `contar={contarEmApp}` nas instâncias de MeuBotao em `App`
3. Adicionar `props.contar` no evento `onMouseMove` em `button` no componente MeuBotao

**arquivo** `src/App.tsx`
```javascript
import { useState } from "react";
import "./App.css";

const MeuBotao = (props: any) => {
	const [contador, setContador] = useState(0);
	const tratarOnClick = () => setContador(contador + 1);

	return (
		<button onClick={tratarOnClick} onMouseMove={props.contar}>
			{props.titulo} {contador} ({props.contador})
		</button>
	);
};

const App = () => {
	const [contador, setContador] = useState(0);
	const contarEmApp = () => setContador(contador + 1);

	return (
		<>
			<h1>Aplicativo exemplo de elevação de estado</h1>
			<MeuBotao
				titulo={"Contador de bom dia"}
				contador={contador}
				contar={contarEmApp}
			/>
			<MeuBotao
				titulo={"Contador de boa tarde"}
				contador={contador}
				contar={contarEmApp}
			/>
			<MeuBotao
				titulo={"Contador de boa noite"}
				contador={contador}
				contar={contarEmApp}
			/>
		</>
	);
};

export default App;
```


## Links
- React
  - Learn React
    - [Quick start - Sharing data between components](https://react.dev/learn#sharing-data-between-components)
    - [Sharing State Between Components](https://react.dev/learn/sharing-state-between-components)
  - Aprendendo React
    - [Elevando o State](https://pt-br.legacy.reactjs.org/docs/lifting-state-up.html)
- MDN (Mozilla Developer Network) Eventos
  - PT-BR https://developer.mozilla.org/pt-BR/docs/Web/API/Element/click_event
  - EN https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event
 
