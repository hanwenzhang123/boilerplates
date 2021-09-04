# Create a New React App
https://reactjs.org/docs/create-a-new-react-app.html
> create app\
> go to project folder\
> install dependencies\
> start live server
```
npx create-react-app my-app
cd my-app
npm start
```
```
npm install
npm start
```
# Deploying a React App on GitHub
```
npm install gh-pages --save-dev
```
```json
"http://{username}.github.io/{repo-name}"

"homepage": "http://hanwenzhang123.github.io/my-app"

"scripts": {
  //...
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build"
}
```
```
npm run deploy
```
# Documentations
[React Docs](https://reactjs.org/docs/hello-world.html)\
[React Tutorial](https://reactjs.org/tutorial/tutorial.html)\
[W3 School](https://www.w3schools.com/react/default.asp)\
[Life Cycle](https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram)\
[CodeSandBox](https://codesandbox.io/s/new)
[Redux Docs](https://redux.js.org/)
 
