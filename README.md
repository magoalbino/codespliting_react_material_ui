# Teste com codesplitting

carregamento inicial:
- Login: chunk 3.4mb -> tempo de loading: 2s
- Dashboard: 2.3s

Depois de adicionar apenas o lazy() e o Suspense:
- Login: chunk 743kb -> tempo de loaging: 430ms
- Dashboard: 1.6s

Com prefetch do Layout e preload do Login e do Dashboard:
- Login: 450ms (aumentou um pouco pq ele carrega o pré load do Layout)
- Dashboard: 1.3s

bundle Analyzer:
<pre>npm run build -- --stats && npx webpack-bundle-analyzer build/bundle-stats.json -m static -r build/bundle-stats.html -O</pre>

import React, { lazy, Suspense } from "react";

Trocar:
<pre>import Dashboard from "../../pages/dashboard";</pre>
para:
<pre>const Dashboard = lazy(() => import("../../pages/dashboard"));</pre>

e na renderização (no caso, dentro do switch mas antes das Routes):
<Suspense fallback={<>Loading...</>}>




<img src="https://storage.googleapis.com/golden-wind/experts-club/capa-github.svg" />

# Melhorando a performance de aplicações React utilizando Code Splitting


O tempo de carregamento é um fator importante no engajamento dos usurios, mais da metade dos usuários relatam que abandonam sites que levam mais de três segundos para carregar.

Nessa aula iremos demonstrar algumas estratégias para diminuir o tempo de carregamento do nosso sistema, utilizando o Lazy e o Suspense do React e o Magic Comments do Webpack.


## Requisitos:
 - NodeJs v14


## Como rodar:
 - `npm install`
 - `npm start`


## Como analisar o bundle:
 - `npm run build:analize`
 - `npm run build -- --stats && npx webpack-bundle-analyzer build/bundle-stats.json -m static -r build/bundle-stats.html -O`


## Referência:

 - [Template](https://github.com/flatlogic/react-material-admin)
 - [React: Code Splitting](https://reactjs.org/docs/code-splitting.html)
 - [Webpack: Bundle Analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer)
 - [Webpack: Bundle Analyzer + Create React App](https://github.com/facebook/create-react-app/issues/3518#issuecomment-454144586)
 - [Webpack: Magic Comments](https://webpack.js.org/api/module-methods/#magic-comments)
 - [Webpack: Preloading/Prefetching](https://webpack.js.org/guides/code-splitting/#prefetchingpreloading-modules)
 - [Artigo: JavaScript Start-up Optimization](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/javascript-startup-optimization)


## Expert

| [<img src="https://avatars.githubusercontent.com/u/3427262?v=4" width="75px;"/>](https://github.com/paulopaquielli) |
| :-: |
|[Paulo Duarte](https://github.com/paulopaquielli)|
