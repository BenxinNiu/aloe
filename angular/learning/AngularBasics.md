# Angular Bsics 

Angular 2 released in 2016
Angular 3 was skipped
call `enableProdMode()` to enable production mode

## 1. Install CLI
`npm install -g @angular/cli`

## 2. Updating CLI
`npm uninstall -g angular-cli @angular/cli`
`npm cache verify`
`npm install -g @angular/cli`

## 3. server in different port
`ng serve --port ANOTHERPORT`

## 4. useful CLI commands
`ng generate component name` or `ng g c name`
`ng generate service name`

## 5. install bootstrap
1. `npm install --save bootstrap@3` (--save will save locally in the project)
2. make angular aware of bootstrap, go to `angular.json` and edit `styles` under `architect` json. "node_modules/bootstrap/dist/css/bootstrap.min.css"

## 6. module introductions
Angular is split up in different modules. to add a module, edit the `app.moudle.ts` file `imports` array.
example: `import {FormsModule} from @angular/forms`

Angular start up process:
starts `main.ts` which imports `AppModule` and pass the list of components to be loaded as arguments:   

``` typescript
import {MyComponent} from '' // don't have to add extension, it is added by web pack
@NgModule({
  declarations: [
    MyComponent
  ], // tell Angular which components are declared

  imports: [],

  providers: [],

  bootstrap: [AppCompoment] // tells angular what component to be loaded during bootstrap
  })  
```  

keep in mind, Angular is a JS framework that modifies DOM at run time   

## 7. Component introductions

Component is just a class that Angular can instantiate, for example:    
``` typescript
// Add class decorator
import { Component } from '@angular/core';

@Component({
  selector: 'my-component-name' // make sure its unique selector name
  templateUrl: '' // this points to the html file (template) or use template to define inline html (one of them has to be present!!!!)
  styleUrls: [] // this points to the style file (you can have multiple and option to do inline)
  }) // @Component takes a js object for configuration
export class MyComponent implement OnInit {

}
```

## 8. Component selector as attribute or class
the selector property in the @Component decorator can be alternatively defined as attribute or class and their corresponding usage in the template are as follows:    

selector: '[my-component]'  (put in square bracket to select as attribute)  
```html 
<div my-component></div>
```    

selector: '.my-component' (select as class)
```html
<div class="my-component"></div>     
```

## 9. Data binding

Three ways of data binding: 
1. String interpolation `{{data}}`

2. Property Binding `[property]="data"`

3. Event Binding `(event)="expression"`

4. Two way binding `[(ngModel)] = "data"`

3 and 4 are reacting to user input. 1 and 2 are output data to DOM

## 10. String Interpolation
use double bracket. write TS expression within, as long as it results in a string

## 11. Property Binding
Can also call a method like in string interpolation    
square bracket indicate we wanna bind this property for example, a button has `disable` property which can be binded like this:

```html
<button class="btn btn-primary" [disabled]="myPropertyName"></button>
<p [innerText]=""></p>
```

## 12. String Interpolation Vs Property Binding
> Use string Interpolation when wanna output something to the template    
> Use property bindind when you wanna change the property of certain HTML elements    

## 13. Event Binding
example:    
`button` element has `onclick` property, but to use Angular convention:
```html
<button (click)="method_name()"></button>
```

### 14. Passing and Using Data with Event Binding
``` html
<button (input)="method_name($event)">
```
data associated with the emmited event is avalible in `$event`

## 15. Important: FormsModule is Required for Two-Way-Binding!
Important: For Two-Way-Binding to work, you need to enable the `ngModel`  directive. This is done by adding the `FormsModule`  to the imports[]  array in the AppModule.

You then also need to add the import from @angular/forms  in the app.module.ts file:

import { FormsModule } from '@angular/forms';

## 16. Two way Data-binding
``` html
<input [(ngModel)]="propertyName">
```

## 17. Directives

They are instructions in the DOM!   
Components are directive with template

exmaple:
```typescript
@Directive({
  selector: '[directiveName]'
})
export class MyDirectiveName {

}
```

## 18. ngIf Directive
native Angular directive

```html
<p *ngIf="you expression">
```
**Important**, the `*` is required because `ngIf` is a structural directive which means it changes the DOM structure

## 19. Enhancing ngIf with an Else condition

use `ng-template` which shipped with Angular to mark a DOM to indicate it shows conditionally

example:    
```html
<p *ngIf="flag; else tagName"></p>
<ng-template #tagName>
<p>alternative content</p>
</ng-template>
```

## 20. Styling Elements Dynamically with ngStyle
One of the built-in Angular directive

Unlike structual directives, attribute directives don't add or remoce elemetns, they only change the lement they were placed on.

``` html
<p [ngStyle]="{backgroundColor: getColorMethod()}">
```

```typescript
getColorMethod() {
  return this.flag ? 'red' : 'black'
}
```
we are binding the property of a directive here

## 21. Applying CSS Classes Dynamically with ngClass
``` html
<p [ngStyle]="{backgroundColor: getColorMethod()}"
   [ngClass]="{className: status==='online'}"
>
```

## 22. Outputing Lists with ngFor
``` typescript
<my-component *ngFor="let component of components"></my-component>
```