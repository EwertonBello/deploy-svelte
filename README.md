# Deploy Svelte
Fazendo deploy de um app default do Svelte no GitHub Pages<br/>
<Strong>Svelte: </Strong>(https://svelte.dev/)<br/>
<Strong>gh-pages: </Strong>(https://www.npmjs.com/package/gh-pages)<br/>
<Strong>Demo: </Strong>(https://ewertonbello.github.io/deploy-svelte/)

### Procedimento

1. Crie um repositório e vincule seu projeto a ele, na pasta do seu projeto faça:
    ```
    git init
    git add .
    git commit -m "primeiro commit"
    git remote add origin https://github.com/NomeDeUsuario/nome-do-repositorio.git
    git push -u origin master
    ```
2. Depois faça o build do seu projeto, `npm run build` ou `yarn build` se preferir utilizar o yarn.<br/>
Obs: Em caso de problemas com o livereload, atualize ele no `package.json` para a última versão e faça `npm install`, depois volte a fazer o build.

3. Feito o build, altere o arquivo `index.html` dentro da pasta `public`, alterando o caminho das importações de `/` para `./`.<br/>
Exemplo:
  ```
 	<link rel='icon' type='image/png' href='./favicon.png'>
	<link rel='stylesheet' href='./global.css'>
	<link rel='stylesheet' href='./bundle.css'>
      .
      .
	<script src='./bundle.js'></script>
  ```
4. Depois utilize o comando `npx gh-pages -d public` para fazer o deploy da pasta public do seu app no branch gh-pages, utilizando o pacote gh-pages.
