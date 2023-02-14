# Curso React-Redux

<hr>
<p align="center">
  <img src="<p align="center">
  <img src="https://waftengine.org/public/blog/1B5EE4D5D773F8A-RR.jpg"/>
</p>"/>
</p>
<hr>

Introdução ao React Redux
React Redux é a camada oficial de bindings do React UI para Redux . Ele permite que seus componentes React leiam dados de uma loja Redux e enviem ações para a loja para atualizar o estado.

Instalação
React Redux 8.x requer React 16.8.3 ou posterior / React Native 0.59 ou posterior , para usar React Hooks.

Usando criar aplicativo
A maneira recomendada de iniciar novos aplicativos com React e Redux é usando o modelo oficial Redux+JS ou modelo Redux+TS para Create React App , que aproveita o Redux Toolkit e a integração do React Redux com os componentes React.

# Redux + Plain JS template

npx create-react-app my-app --template redux

# Redux + TypeScript template

npx create-react-app my-app --template redux-typescript
Um aplicativo
Para usar o React Redux com seu aplicativo React, instale-o como uma dependência:

# If you use npm:

npm install react-redux

# Or if you use Yarn:

yarn add react-redux
Você também precisará instalar o Redux e configurar uma loja Redux em seu aplicativo.

O React-Redux v8 é escrito em TypeScript, então todos os tipos são incluídos automaticamente.

Visão geral da API
Provider​
O React Redux inclui um <Provider />componente, que disponibiliza a loja Redux para o restante do seu aplicativo:

import React from 'react'
import ReactDOM from 'react-dom/client'

import { Provider } from 'react-redux'
import store from './store'

import App from './App'

// As of React 18
const root = ReactDOM.createRoot(document.getElementById('root'))
root.render(
<Provider store={store}>
<App />
</Provider>
)
ganchos
O React Redux fornece um par de ganchos React personalizados que permitem que seus componentes React interajam com a loja Redux.

useSelectorlê um valor do estado da loja e se inscreve nas atualizações, enquanto retorna o método useDispatchda loja para permitir que você envie ações.dispatch

import React from 'react'
import { useSelector, useDispatch } from 'react-redux'
import {
decrement,
increment,
incrementByAmount,
incrementAsync,
selectCount,
} from './counterSlice'
import styles from './Counter.module.css'

export function Counter() {
const count = useSelector(selectCount)
const dispatch = useDispatch()

return (
<div>
<div className={styles.row}>
<button
className={styles.button}
aria-label="Increment value"
onClick={() => dispatch(increment())} > +
</button>
<span className={styles.value}>{count}</span>
<button
className={styles.button}
aria-label="Decrement value"
onClick={() => dispatch(decrement())} > -
</button>
</div>
{/_ omit additional rendering output here _/}
</div>
)
}
Aprendendo React Redux
Aprenda a transmissão ao vivo
O mantenedor do Redux, Mark Erikson, apareceu no programa "Learn with Jason" para explicar como recomendamos o uso do Redux hoje. O programa inclui um aplicativo de exemplo codificado ao vivo que mostra como usar o Redux Toolkit e os ganchos React-Redux com Typescript, bem como as novas APIs de busca de dados RTK Query.

Consulte a página de notas do programa "Learn Modern Redux" para obter uma transcrição e links para a fonte do aplicativo de exemplo.

Ajuda e Discussão
O canal #redux da comunidade Reactiflux Discord é nosso recurso oficial para todas as questões relacionadas ao aprendizado e uso do Redux. Reactiflux é um ótimo lugar para sair, fazer perguntas e aprender - junte-se a nós!

Você também pode fazer perguntas no Stack Overflow usando a tag #redux .

Traduções de Documentos
