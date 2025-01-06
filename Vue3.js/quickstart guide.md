# Vue3
## quickstart guide
There are many ways to use Vue3.

1. embed CDN in `.html` file.
2. create a vue project with currently latest version of Vue + Vite.
   
### embed CDN in `.html` file
To embed CDN in `.html` file, add these in `.html`.

```
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
```

### create a vue project with currently latest version of Vue + Vite

> [!NOTE]
> Here is the guide for currently latest version (NOT stable) matched with vite, the approach may probably change in the future release, for more details, see [Vue-cli (official docs)](https://cli.vuejs.org/)

To install the latest version of vue-cli and vite (if it has NOT been installed yet) and create a new project, do the following steps.

1. In command prompt, type these commands.

```
npm create vue@latest
```

> [!NOTE]
> You can install it without npm command, but with other command, for more info, see [installation guide of vue-cli (official docs)](https://cli.vuejs.org/guide/)

2. Then it will ask you project name. Fill it.
3. Additionally, it will also ask you some questions, answer these questions.
4. Then you will create a new project.
5. Then change directory to your project name, to do so, type these commands.

```
cd <your-project-name>
```

6. Then, type these commands to install neccessary packages.

```
npm install
```

> [!NOTE]
> Be patient. It will take a few minutes, since there are lots of package needed to install.

7. Then type these commands.

```
npm run format
```

8. Finally, type these commands.

```
npm run dev
```

9. Then you will see a connection with url in terminal. Click it to visit the url to connect the server.

<img width="848" alt="image" src="https://github.com/user-attachments/assets/98977365-852a-4ab9-9fcf-94101e8ddab9" />

##### demo
See [`How to create a new project with Vue + Vite in command prompt in Windows 11?`](https://youtu.be/b6k_sMTSw7E)

#### modify code

It is easier to modify the code than Vue2.

It is clearer to define a new template in `.vue` file and use it. 

+ compose the UI on web page.
  
The Vue will build `.../src/App.vue` and run it, displaying output on UI on web page.

So, to compose the UI on web page, you just have to import components in `.../src/App.vue`, then compose components in `<template>` tag in `.../src/App.vue`.

+ change style of components

To change style of components, you just have to add style `<style>` tag in `.../src/App.vue`.

#### reference
##### guide reference
See [`Tooling#Vite (official docs)`](https://vuejs.org/guide/scaling-up/tooling.html#vite)
