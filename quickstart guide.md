# Vue.js
## quickstart guide
There are lots of different version of Vue. There are a small difference to install vue-cli and create vue project between different version of vue-cli.

Here, I will discuss this topic for two different version.

### currently latest stable version of vue-cli
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

##### example
Take my project named `app-project` for example.

<img width="518" alt="image" src="https://github.com/user-attachments/assets/b90c6117-fa5c-4862-94d5-4520af559e00" />

The web page will display the result of `main.js`. So let's dive in `main.js`
 
In my project, I will see the following code snippets `main.js`.

```
import { createApp } from 'vue'
import App from './App.vue'

createApp(App).mount('#app')
```

According to the API docs, one can know these infos.

+ `createApp` function is a function that create a component as an App. The component will hold the whole web page by default.

+ `mount` function indicates what style will be used. Here, it will use style named `#app`

> ![TIP]
> Recall about css knowledge.
>
> css can be categorized by `class` attr, `id` attr and the html tag itself.
>
> + name of a `class` attr must be start with `#` and followed by one or more of alpha number and dash `-`.
>
> + name of a `id` attr must be start with `.` and followed by one or more of alpha number and dash `-`.
> 
> For more details, see [style in `CSS`](https://www.w3schools.com/html/html_css.asp) 

#### reference
##### guide reference
See [`Overview of Vue-cli (official docs)`](https://cli.vuejs.org/guide/)

### currently latest version of vue-cli + vite
> [!WARNING]
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
