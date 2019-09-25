# Project with Nextjs - React - FetchApi

What is?

Es un framework sencillo para crear aplicaciones React con SSR.

SSR:

Server side rendering, nos permite crear el HTML desde el servidor, esto permite que sea más rápido, ya que los recursos son de parte del servidor.

El SSR se recomienda para aplicaciones escalables.

Mejoramiento del SEO.

### Características de Nextjs

- Code splitting y Lazy Loading a los components, es decir, seperara el código de tus componentes, algo similar a lo que realiza webpack, por ejemplo si tienes 50% del código se usa en un componente se pondrá en otro archivo para no cargar tanto la página.

- Routing en base de los archivos
- URL's Limpias : /nosotro.js = /nosotros
- Soporte para Css
- Hot reload

# First step with Nextjs

### Enlazando páginas

En React podíamos usar Router, en nextjs ya cuenta con la función Link.

Lo importas 

```js
import Link from 'next/link';
```

Y hemos creado una carpeta en la cual almacenamos todos nuestros componentes, creamos un componente con los enlaces y ya con ese componente lo reutilizamos.


### Agregando css 

En nextjs podemos agregar estilos en nuestros componentes mediante una etiqueta llamada `<style jsx>` con un parametro jsx, estos estilo se aislarán en el archivo que los apliques, es decir, si aplicas estilos a un componente, en algún otro componente no te afectará.

Existe muchas maneras de aplicar css en nextjs, usa la que más te convenga.

```js
<style jsx>
    h1{
        color: red;
    }
</style>
```

### MasterPage

Si deseamos agregar alguna librería de estilo como bootstrap, podemos crear una masterpage, para poder usar los estilos en todos los otros componentes.

Primero importamos head de next
Esto nos permitira tener un **head** donde añadir los enlaces a las librerías como bootstrap:
```js
import Head from 'next/head';
```

y creamos nuestro componente MasterPage

```js
const MasterPage = (props) => (
    <div>
        <Head>
            <title>Bitcoin</title>
        </Head>

        {/*Importante*/}
        {props.children}
    </div>
);

export defaul MasterPage;
```

Ese `{props.children}` que tenemos en nuestra MasterPage es lo que nos permite imprimir las etiquetas que esten dentro del componente `<MasterPage>Todolo que este acá dentro vendría siendo el {props.childre} </MasterPage>`.