# Vue.js
## quickstart guide
There are lots of different ways to run .vue or vue project.

Here, I will only discuss three ways:

+ embed vue plugin (development version) in `.html` file.
+ create a vue project with currently latest stable version of vue-cli.
+ create a vue project with currently latest version of Vue + Vite.

### embed vue plugin (development version) in `.html` file
To embed vue plugin (development version) in `.html` file, one just have to add `https://cdn.jsdelivr.net/npm/vue/dist/vue.js` in `<head>` tag

As follows.

```
<head>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
</head>
```

stated more in [`Vue.js 的基礎使用與雙花括號表達式`](https://ithelp.ithome.com.tw/articles/10239374)

### create a vue project with currently latest stable version of vue-cli
> [!WARNING]
> Here is the guide for currently latest stable version, the approach may probably change in the future release, for more details, see [Vue-cli (official docs)](https://cli.vuejs.org/)

#### installation
To install the latest stable version of vue-cli, do the following steps.

1. In command prompt, type these commands.

```
npm install @vue/cli
```

> [!NOTE]
> You can install it without npm command, but with other command, for more info, see [installation guide of vue-cli (official docs)](https://cli.vuejs.org/guide/)

##### demo
See [`How to install vue-cli with npm command in command prompt in Windows 11?`](https://youtu.be/WLC6VHPQqK4)

#### create new project and run the server
To create a new project, follow these steps.

1. In command prompt, type these commands.

```
vue create <your-project-name>
```

where 

`<your-project-name>` is the name of your project.

2. It will ask you some questions about configuration.

Answer these questions.

3. Then you will see your project is created.
4. After that, change your directory to your project's directory in command prompt. It can be done by typing these commands in command prompt.

```
cd <your-project-name>
```

5. To run the server, type these commands in command prompt.

```
npm run serve
```

> [!NOTE]
> NOTICE that do **NOT** type these commands.
>
> ```
> npm run server
> ```

6. Then it will compile and build the whole project then running the server. Should look like this if the server runs successfully.

<img width="881" alt="image" src="https://github.com/user-attachments/assets/8a1740d2-020d-4582-9be5-7e517af9398b" />

7. Either type `http://localhost:8080/` in web browser or click `http://localhost:8080/` link in command prompt (shown in above figure), then you will visit page with url `http://localhost:8080/`.
8. Congratulation, you can see web of your vue project.

##### example
Take my project named `app-project` for example.

1. In command prompt, type

```
vue create app-project
```

2. Then it will ask some questions.

I select the first option (`Vue3`)

3. Then, in command prompt, type

```
npm run serve
```

4. Then it will compile and build the whole project then running the server. Should look like this if the server runs successfully.

<img width="881" alt="image" src="https://github.com/user-attachments/assets/8a1740d2-020d-4582-9be5-7e517af9398b" />

5. click `http://localhost:8080/` link in command prompt (shown in above figure).

##### demo
See [`How to create vue project in command prompt in Windows 11?`](https://youtu.be/rrGlRKmhrMM)

#### modify the code of vue project
Before modifying the code of vue project, you have to know 

+ the hierarcy of project
+ how the server runs the code.

We will discuss these topic with following example.

Let me tell you answer about how to modifying the code vue project.

We have to modify template in `../src/App.vue` and template in `../src/component/HelloWorld.vue`. 

Why? 

Let me explain with following example.

##### example
Take my project named `app-project` for example.

<img width="518" alt="image" src="https://github.com/user-attachments/assets/b90c6117-fa5c-4862-94d5-4520af559e00" />

The web page will display the result of `../src/main.js`. So let's dive in `../src/main.js`
 
###### ../src/main.js
By default, it should look like this: 

```
import { createApp } from 'vue'
import App from './App.vue'

createApp(App).mount('#app')
```

According to the API docs, one can know these infos.

+ `createApp` function is a function that create a component as an App. The component will hold the whole web page by default.

+ `mount` function indicates what style will be used. Here, it will use style named `#app` in `<div class ="#app">`

> [!TIP]
> Recall about css knowledge.
>
> css can be categorized by `class` attr, `id` attr and the html tag itself.
>
> + name of a `class` attr must be start with `#` and followed by one or more of alpha number and dash `-`.
>
> + name of a `id` attr must be start with `.` and followed by one or more of alpha number and dash `-`.
> 
> For more details, see [style in `CSS`](https://www.w3schools.com/html/html_css.asp) 

###### `../src/App.vue`
Next, let's take a glance at definition of `App` in `../src/App.vue`.

By default, it should look like this:

```
<template>
  <div class ="#app">
    <HelloWorld msg="Welcome to Your Vue.js App"/> 
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

Here, there are a few code snippets that's worth to explain it.

+ The following code snippets.

```
<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>
```

define the component  
  
  - whose name is `App` (we can know it through name field is set to `App` (name: 'App',) between <script> and </script> tag in `../src/App.vue` file).
  - that uses these components: `HelloWorld` (we can know it through name field is set to `App` (components: {HelloWorld}) between <script> and </script> tag in `../src/App.vue` file) .

+ The following code snippets. 

```
<template>
  <div class ="#app">
    <HelloWorld msg="Welcome to Your Vue.js App"/> 
  </div>
</template>
```

Here is a template that the will be used at `createApp(App)` function call in `../src/main.js` file. 

The server will run the above template (we can know it through name field is set to `App` (name: 'App',) between <script> and </script> tag in `../src/App.vue` file) 

and then display output on web page.

> [!NOTE]
> `<HelloWorld>` component is defined in `./components/HelloWorld.vue`.
>
> You will know it at `import HelloWorld from './components/HelloWorld.vue'` between`<script>` and </script> tag in this file. 

+ The following code snippets.

```
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

defines the css style named `#app`.

> [!NOTE]
> It will be used in `<div>` tag at `<div class ="#app">` and which will be mounted in the `mount` method call at `createApp(App).mount('#app')` at `../src/main.js`

###### ../src/components/HelloWorld.vue
Let's dive into `../src/components/HelloWorld.vue`.

By default, it should look like this:

```
<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
```

Here's a few code snippets that is worthy to explain it.

+ The following code snippets:

```
<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>
```

define the component  
  
  - whose name is `HelloWorld`
  - that has these properties: `msg` with String type.

+ The following code snippets:

```
<template>
  <div class="hello">
    <!-- ... -->
  </div>
</template>
```

declares a template 
   
   - whose name is `HelloWorld` (we can know it through `name` field is set to `HelloWorld` (`name: 'HelloWorld',) in `../src/components/HelloWorld.vue`.).

##### summary
I summarize the execution of an server of vue project into several diagrams.

[`workflow 1 of vue project with @vue_cli command in command prompt.jpg`](https://github.com/40843245/Vue.js/blob/main/attachment/figure/workflow%201%20of%20vue%20project%20with%20%40vue_cli%20command%20in%20command%20prompt.jpg)

[`workflow 2 of vue project with @vue_cli command in command prompt.jpg`](https://github.com/40843245/Vue.js/blob/main/attachment/figure/workflow%202%20of%20vue%20project%20with%20%40vue_cli%20command%20in%20command%20prompt.jpg)
### create a vue project with currently latest version of Vue + Vite

> [!NOTE]
> Here is the guide for currently latest version (NOT stable) matched with vite, the approach may probably change in the future release, for more details, see [Vue-cli (official docs)](https://cli.vuejs.org/)

#### installation and create a new project
To install the latest version of vue-cli and vite (if it has NOT been installed yet) and create a new project, do the following steps.

1. In command prompt, type these commands.

```
npm create vue@latest
```

> [!NOTE]
> You can install it without npm command, but with other command, for more info, see [installation guide of vue-cli (official docs)](https://cli.vuejs.org/guide/)

##### demo
See [`How to create a new project with Vue + Vite in command prompt in Windows 11?`](https://youtu.be/b6k_sMTSw7E)

#### reference
##### guide reference
See [`Tooling#Vite (official docs)`](https://vuejs.org/guide/scaling-up/tooling.html#vite)
