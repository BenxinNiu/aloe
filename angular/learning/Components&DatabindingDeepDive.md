## Components & Data binding Deep Dive

## 1. Binding to Custom Properties
By default, properties in a component are only accessible within the component. You have to be explicit about which property you want to be binded from parent component.       

Add a decorator to the property, for example: 

``` typescript
import {Component, OnInit, Input} from '@angular/core' 
@Component({
  selector: 'my-component-name' 
  templateUrl: '' 
  styleUrls: [] 
  }) 
export class MyComponent implement OnInit {

    @Input() // here is how you do it
    element: {type:string, name:string};

    constructor() {}

    ngOnInit() {
    }
}
```

## 2. Assigning an Alias to Custom Properties

``` typescript
@Input('myAlias')
element: {type:string, name:string};
```
now the `myAlias` is known to the outside component to enable binding, instead of `element`

## 3. Binding to Custom Events
Emitting an event to parent component. Used when communication from child to parent component is needed: 

``` typescript
import {Component, OnInit, Output, EventEmitter} from '@angular/core' 
@Component({
  selector: 'my-component-name' 
  templateUrl: '' 
  styleUrls: [] 
  }) 
export class MyComponent implement OnInit {

    @Output() // here is how you do it
    myCustomEvent = new EventEmitter<IDataType>();

    constructor() {}

    trigger() {
        let data: IDataType = {name: 'ben'}
        this.myCustomEvent.emit(data);
    }
    ngOnInit() {
    }
}
```
Then, in the parent component, you can bind to this event like all others: 

```html
<my-component-name (myCustomEvent)=""></my-component-name>
```

Like `@Input()`, you can also add an alias as an argument. 

## 4. Summary 
Gneral rul of thumb:        
> Use `@Input` to enable communication from parent to child       
Use @Output to enable communication from child to parent.   
If the distance between hierachy levels are to great ot too close, consider using `Service`

## 5. Understanding View Encapsulation
By default, Angular enforces CSS styles to be applied to the component that it belongs to (style encapsulation). 
This is how Angular emulates `shadow DOM` (Not all broswer uses shadow DOM support)

## 6. How to override encapsulation
In the `@Component` decorator, add `encapsulation` proerty (import from @angular/core): 

``` typescript
@Compoennt({
selector: '',
templateUrl: ''.
styleUrls: [].
encapsulation: ViewEncapsulation.None
})
...
// ViewEncapsulation.Emulated is by default
// ViewEncapsulation.Native use the Shadow DOM technology
```

## 7. Using Local References in Templates
Can only be used in the template, not ts code. example: 

```html
<!-- This is how u use Local References in Templates -->
<input type="text" class="form-control" #localReferenceName>
<button class="btn btn-primary" (click)=tirgger(localReferenceName)></button>
```