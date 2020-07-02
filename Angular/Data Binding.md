### Data Binding

Communication between the TypeScript code(Back) and the HTML template(front)

1. Interpolate variables or return values of methods in the ts file.

```html
{{data}}
{{method()}}
```
2. Property binding and event binding:

```html
[property] = "data"
(event) = "method()"
```

#### Two-Way Data Binding

Sometimes we change the variables in ts file by using the front-end data. Here is an example:

```html
<input type="text" [(ngModel)]="variable_name">
```

In this case we assign the user input to the specific variable. Remember everytime we use 2-way data binding we should use: `[(ngModel)]="data"`.

#### ngif

```html
<div *ngif="flag"><div>
```

"flag" is a boolean variable in the ts file. If flag is true, this `<div>` will appear in the webpage.

#### ngfor

```html
<div *ngfor="let i of array">
  <div><span>Array element is: </span> <span>{{i}}<span>
  </div>
</div>
```

It can iterate over the array then display the `<div>` in the webpage.

There are also some syntax like `ngStyle`, `ngClass`.
