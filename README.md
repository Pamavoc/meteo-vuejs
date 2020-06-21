# METEO VUE-JS 

https://pamavoc-meteo-app.netlify.app

Quick meteo-app made in VueJS with Openweather API & bootstrap

<b>STRUCTURE OF THE APP</b>

We have a Meteo.vue component & App.vue component.
Meteo.vue is the children of App.vue.


<b>HOW IT WORKS</b>

- Meteo.vue component is imported to our App.vue component in the < script > so it's displayed with a < meteo > in our < template >
- Meteo.vue is where the logic & appearance are placed.
- We have a container with a form (to enter a city) & a container to display the result we retrieve from the API.
- In the first form we have an input with a method linked to it : @keypress.enter="goMeteo". 

- In our < script > of Meteo.vue, 
    > We have data() a function of an object whichg return some properties for the API (api_code, url_looking) & our future data (temps property). These informations are crucial to do the request to the api.
    > &  We have the method goMeteo() which is where the API call takes place
 
- With axios, an HTTP client based on Promises, we can do the request.
- On the .get we can choose the language we want for the data, it's in the link we use.
- After the request, we get an object and we just have to select the informations we want (console.log & chrome dev tool are here to help).
- To display the data we just received, we use our second container inside the < template > of Meteo.vue


<b>ROADMAP</b>

- v1.1: display more info

- v1.2: add a real UI

- v1.3: detect temperature and generate a gradient-background linked to it



## Project setup
```
npm install & add your personnal openweather API key to the .env_sample file
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
