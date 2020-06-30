### Angular Setup and Fundations

To run the Angular server, run:
```
ng serve
```
The url is:
```url
localhost:4200
```
When opening the directory, the structure is like this:

![structure](/pictures/Structure.png)

We can see the index.html is the html file of the first website. In this file, most of the code of the website structure is inside this tag:
```html
<app-root><app-root>
```

This tag refers to another file in `app.component.html` in the app directory.

For the whole project, the start point is at `main.ts`:

![main](/pictures/main.ts.png)

In the last row it defines the first module is `AppModule`, which is in the file `app.module.ts`.

![appmodule](/pictures/appmodule.png)

In this file it exports the `AppModule` class and defines and loads several components. In this line:

```TypeScript
bootstrap: [AppComponent]
```

which means the first webpage must be `AppComponent`.
This component contains a css file, html file, test file(spec.ts) and ts file. The ts file is like a typical js file in web programming, which is like the backend of our webpage, defining the behaviors of the webpage.

A webpage may consist of several components, which have a structure like a **tree**. It means, a component can consist of other components, like parents and children.

However, everytime we define a component, we should ensure the `AppModule` can recognize this component, so we must add this component in the `declarations` of `app.module.ts`.

On top of generate a component by ourselves, we can automatically generate it:

1. change the current path to `src/app/`

2. run the following command:
```
ng g c Component_Name
```
