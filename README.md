# angular-teacher
teach

# Angular Tutorial

[Data Binding](#data-binding)    
[Property Binding](#property-binding)    
[Native Event Binding](#native-event-binding)    
[Two Way Data Binding](#two-way-data-binding)    
[Custom Property Binding](#custom-property-binding)    
[Custom Event Binding](#custom-event-binding)    
[Routing](#Routing)    
[Adding Links](#adding-links)    
[Route Params](#route-params)    
[Routing](#Routing)    
[Directive Introduction](#directive-introduction)    
[ngFor](#ngfor)
[ng-template](#ngTemplate)
[import component](#import_component)
[get data from api](#get-data-from-api)
[add bootstrap](#add boostrap)
[add modal with bootstrap](#add_modal_with_bootstrap)
[angular deploy with node js](#angular-deploy-with-node-js)
[uninstall angular-cli](#uninstall-angular-cli)
[Optimize Your Angular App](#Optimize_Your_Angular_App)
[electron](#electron)



installation
to work with angular should install node js to your os.    

to check node version       
$ node -v    

to install angular cli globally    
$ npm install -g @angular/cli    

to check angular version     
$ ng --version    

to change angular version    
```shell
ng --version
npm uninstall -g @angular/cli
npm cache clean --force

npm install -g @angular/cli@7.2.12
ng --version
```


to start new project    
```shell
$ ng new <my-app-name>   
$ ng new --routing=true --style=scss
# --routing=true|false
# --style=css|scss|sass|less|styl
```

to open location in VSCODE in terminal
```shell
$ code .
```

to start already created project on root 
```shell
$ ng serve -o  # '-o' option for open starting project on browser 
```
  
to create new component    
```shell
$ ng generate component <component-name>    
$ ng g c <component-name>  # short form    
```     

to create new service    
```shell
$ ng generate service <service-name>    
$ ng g s  <service-name>   # short form      
```     

to create new class   
```shell
$ ng generate class <class-name>        
$ ng g c <class-name>    
```    

to terminate live development server    
ctr+c    

go to /src/app/app.component.html and delete detault code start customize code    
```html
   <h>Angular app </h>
```   

go to /src/app/app.component.ts and create variable    
```typescript
   export clsss AppComponnet{
      name = 'tutorial'
   }
```  
```html
   <h>Angular app {{name}} </h>
```  

# Folder struture    
node_modules : all dependences  
src : source files   
src/app : any component, module, service in this foleder   
src/assets : static assets (images, icons, textfile )
environments : for environment releted configeration    
favicon.ico : icon display on browser    
index.html : all code inject to this file by build angular cli    
main.ts : entry point / start file    
polyfill.ts : cross browser and version supporter. (fill the gap)    
styles.css : global css styles  
test.ts : setting our test env    
.editorconfig : setup rules of code styles for developer     
.gitignore : ignore for git stages   
angular.json(angularcli.json) :  all config of angular project(project name)   
karma.conf.js : test runner for test   
project.json : packges/dependency configuration.    
tsconfig.json : typescript configuration.      

  
# How Angular project is Executed    
go to /src/main.ts entry point and show what is bind to "bootstrapModule(AppModule)"   
go to where had "AppModule" file    
show "bootstrap" array. Basucally list all components which should be know to angular when analyzes index.html.    
go to array value of "app.component.ts" and show selector that angular going to add to html file while rendering.    
you can't see scripts files on index.html file because it's add using angular cli.    


we can use component.ts file class properties and method in view template(component.html) file.    

# Creating Custom Components example    
>styles.scss    
```scss
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
```    
create "container" component manually    
1. create folder call "container" inside app folder.   
2. create "container.component.ts" file and import "Component" from angular/core    
3. create component decorator with "selector", "templateUrl" and "styleUrls".    
4. create "ContainerComponent" class.    
5. copy component selector file name and add to the app.component.heml(template) file.   
6. add newly created comonent in "app.module.ts" file's 

create "nav" component using angular-cli.   
```bash
$ ng g c nav  # create on src/app/nav 
$ ng g c test/cd/compo  # create on src/app/test/cd/compo
```   
> nav.component.html    
```html
<div class="navbar">
    <div class="site-name">
        <h1>eShopping</h1>
    </div>
    <div class="ste-menu">
        <a href="#">HOME</a>
        <a href="#">ABOUT</a>
        <a href="#">CONTACT</a>
        <a href="#">CART</a>
        <a href="#">PRODUCTS</a>
    </div>
</div>
```    
> nav.component.scss   
```scss
.navbar{
    display: flex;
    background-color: #F58041;
}
.site-name{
    padding: 5px 30px;
    color: #E74C3C;
}
.site-menu{
    padding: 10px 30px;
    margin-left: 100px;
}
a{
    text-decoration: none;
    color: #212F3D;
    margin: 0px 10px;
}
```    
> header.component.html    
```html
<div class="header">
    <div class="site-image">
        <img src="/assets/shopping.jpg" height="240" width="320">
    </div>
    <div class="site-slogan">
        <h2>your one stop shop for everything</h2>
    </div>
</div>
```    
> header.component.scss    
```html
.header{
    height: 280px;
    padding: 30px 40px;
    display: flex;
    background-color: #fff;
}

.site-slogan{
    width: 420px;
    margin-left: 50px;
    text-align: center;
}

h2{
    font-size: 45px;
}
```
> container.component.html    
```html
<div class="wrapper">
    <app-nav></app-nav>
    <app-header></app-header>
</div>
```    
> container.component.scss    
```html
.wrapper{
    margin: 0 auto;
    width: 820px;
}
```

# Using Bootstrap in Angular 
```bash
$ npm install --save bootstrap # install latest    
$ npm install --save boostrap@4 # install specific version    
```    
add "bootstrap.min.css" file location in "angular.json" file before global style file   
after add this show browser inspect to see boostrap color file are added.   
```json
"styles": [
  "node_modules/bootstrap/dist/css/bootstrap.min.css",
  "src/styles.scss"
],  
```
# Different Selectors in Angular    

# Different Selectors in Angular 

change like html attribute.    

> container.component.html     
```html 
<div class="wrapper">
    <!-- <app-nav></app-nav> -->
    <div app-nav></div>  <!-- add here -->
    <app-header></app-header>
</div>
```

> container.component.html     
```typescript
@Component({
  selector: '[app-nav]', // change here..
  templateUrl: './nav.component.html',
  styleUrls: ['./nav.component.scss']
})
```  

change like class.
> container.component.html     
```html 
<div class="wrapper">
    <!-- <app-nav></app-nav> -->
    <div class="app-nav"></div>  <!-- add here -->
    <app-header></app-header>
</div>
```

> container.component.html     
```typescript
@Component({
  selector: '.app-nav', // change here..
  templateUrl: './nav.component.html',
  styleUrls: ['./nav.component.scss']
})
```  
   
show how we can cotomize selectors    
```typescript   

@Component({
  selector: 'app-root',
  templateUrl: '<h1>Angular app </h1>',
  styleUrls: ['./app.component.scss']
})

# You can specify more than one styles file in styleUrls it will apply only for this component.    

@Component({
  selector: 'app-root',
  template: `<h1>Angular app {{title}}</h1>`,
  styles: ['h1 { font-weight: normal; padding:10px }', 'div{padding:1px}']
})

@Component({
  selector: 'app-hero-controls',
  template: `
    <style>
      h1 {
        background-color: white;
        border: 1px solid #777;
      }
    </style>
    <h1>Controls</h1>
    <button type="button" (click)="activate()">Activate</button>
  `
})
# vscode not showing any error is misspelled html/css code here. 
# you can remove styles and add styles to template    

```   
show app.component.ts file "app-root" in index.html file and "app-root" on browser inspect.  


# Data binding      
Data binding in angular allows us to communicate between a component class and its corresponding view template.   

One way data binding is data flow only one direction. component class in corresponding view template or view template to component class.   
1. String interpolation {{data}}    (component class to view template)
2. Property binding [property] = data (component class to view template)
3. Event binding (data)="expression" (view template to component class)    

Two way data binding binds data from component class view template and view template to component class. This is combination of property binding and event binding.    


### data transfer from component to view template in same component   
show tree examle of Interpolation(one way binding)

>file.ts

```javascript
import { Component, OnInit } from '@angular/core';


@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
  styleUrls: ['./home.component.css']
})
export class HomeComponent implements OnInit {

  // String Interpolation
  public homeTitle:string = "this data from homeComponent class";
  public getTitle():string{
    return this.homeTitle;
  }

  constructor() { }

  ngOnInit(): void {
  }

}
```

>file.html  

```html
<!-- String Interpolation -->
<p>{{homeTitle}}</p>
<p>{{1+2+3}}</p>
<p>{{ getTitle() }}</p>

```

# Property Binding

### data transfer from file.ts to file.html in same component

"src" is the name of the <img> element property.    
property with [] make right side dynamic expression if not just static value.    

This thing can do with previous method too.    
```html
<input value="{{myString}}" />
```
But as a improvment here we are use '[property_name ]' to get this property name's value from file.ts.    
```html
<input [property_name ]="value_variable_located_in_ts_file" />
```

### property Binding
  * Native HTML properties: [value]="express"   
      ```html
         <input [value]="type some thing" />
         <div  [hidden]="true">test hidden attribute</div>
      ```
  * Custom-made properties: [myProp]="express"   
      ```html
         <input [count]="true" />
      ```
  * Built in angular directives: [ngClass]="express"  
    expression > "return values": String, Array, and Object 
    no deepwatch class
    is there one class static "[class]="className"" or "class="className"" with logic "[class.className]="express""    
    is there multiple class static  "[class]="class1 class2"" or "class="class1 class2"" or "[class]="['class1', 'class2']"" with logic "[class]="{foo: express, bar: express}""
    with deepwatch class
    is there one class static "[ngClass]="'className'""  with logic "[ngClass]="express""    
    is there multiple class static  "[ngClass]="'class1 class2'"" or "[ngClass]="['class1', 'class2']"" with logic "[ngClass]="{foo: express, bar: express}"" or [ngClass]="val > 10 ? 'red' : 'green'"
    no deepwatch sytle
    is there one sytle static "[sytle]="width: 100px;" or "sytle="width: 100px;"" or "[style]="{width: '100px'}" or [style.width.px]="100" with logic "[style.background-color]="express""    
    is there multiple sytle static "[sytle]="{width: '100px', height: '100px'"}" or "sytle="class1 class2"" or "[sytle]="['class1', 'class2']"" with logic "[sytle]="{foo: express, bar: express}""
    with deepwatch style
    is there one class static "[ngStyle]=""width: 100px;""  with logic "[ngStyle]="express""    
    is there multiple class static  "[ngStyle]="'"width: 100px; height: 100px;'"" or "[ngStyle]=""{width: '100px', height: '100px'}"" with logic "[ngStyle]="{foo: express, bar: express}"" or [ngStyle]="val > 10 ? 'red' : 'green'"

      ```html
         <div [ngClass]="className" >
         <div [ngClass]="'first second'">
         <div [ngClass]="['first', 'second']">
         <div [ngClass]="{first: true, second: true, third: true}">
         <div [ngClass]="{'first second': true}">
         <div [ngClass]="val > 10 ? 'red' : 'green'">{{ val }}<div>
         <div [ngClass]="control.isInvalid ? 'error' : ''" ><div> <!-- same 1-->
         <div [ngClass]="{ error: control.isInvalid }" ><div> <!-- same 1-->
         <div [class.error]="control.isInvalid" > <div><!-- same 1-->
         <div [ngClass]="getClassOf(val)">{{ val }}</div>
         <div [ngClass]="{ low: val >= 0 && val <=5, medium: val > 5 && val <= 10, high: val > 10}">{{ val }}</div>
         <div [class.sale]="onSale"></div> <!-- boolean | undefined | null -->
         <div [class]="my-class-1 my-class-2 my-class-3"></div> <!-- string  -->
         <div [class]="{foo: true, bar: false}"></div> <!-- string | boolean | undefined | null  -->
         <div [class]="['foo', 'bar']"></div> <!-- Array<string>  -->
         
         <div [ngStyle]="{'max-width.px': widthExp}"></div>
         
         <div [style.backgroundColor]="expression"></div> <!-- same 2-->
         <div [style.background-color]="expression"></div> <!-- same 2-->
         <div [style.width]="100px"></div> <!-- same 4-->
         <div [style.width.px]="100"></div> <!-- same 4-->
         <div [style]="'width: 100px; height: 100px; background-color: cornflowerblue;'"></div> <!-- same 3-->
         <div [style]="{width: '100px', height: '100px', backgroundColor: 'cornflowerblue'}"></div> <!-- same 3-->
      ```

       [class] and [style] bindings not support for deepwatch.(can do using with pipes)  
       [ngClass]="{'a b': true}" does work, but not [class]="{'a b': true}" 

  * send data to child component  
      ```html
        <app-item-detail [childItem]="parentItem"></app-item-detail>
      ```

  
  * think in style binding    
    1. static or variable or dynamic 
    2. single or multiple or function    

 
>file.ts

```javascript
import { Component, OnInit } from '@angular/core';


@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
  styleUrls: ['./home.component.css']
})
export class HomeComponent implements OnInit {
  myString = "Enter value here";

  constructor() { }

  ngOnInit(): void {
  }

}
```

>file.html  

```html
<input [value]=myString/>
```

# Two Way Data Binding

Two way data binding binds data from component class to view template and view template to component class. This is a combination fo property binding and event binding.     

<mark>import FormsModule in module.ts file</mark>    
 [()] syntax combines the brackets of property binding, [], with the parentheses of event binding, (), as follows.   

Two way data binding is combination of @Input() and @Output() biding.    


```javascript
@Component({
  selector: 'app-twowayparent',
  template: `
    <app-twowaychild [(size)]="fontSizePx"></app-twowaychild>
    <!-- <app-sizer [size]="fontSizePx" (sizeChange)="fontSizePx=$event"></app-sizer> -->
    <div [style.font-size.px]="fontSizePx">Resizable Text</div>
  `,
  styleUrls: ['./twowayparent.component.css']
})
export class TwowayparentComponent{
  fontSizePx = 16;
}
```

```javascript
@Component({
  selector: 'app-twowaychild',
  template: `
      <div>
          <button type="button" (click)="dec()" title="smaller">-</button>
          <button type="button" (click)="inc()" title="bigger">+</button>
          <span [style.font-size.px]="size">FontSize: {{size}}px</span>
      </div>
  `,
  styleUrls: ['./twowaychild.component.css']
})
export class TwowaychildComponent{
  @Input()  size!: number | string;
  @Output() sizeChange = new EventEmitter<number>();
  constructor() { }

  ngOnInit(): void {
  }

  dec() { this.resize(-1); }
  inc() { this.resize(+1); }

  resize(delta: number) {
    this.size = Math.min(40, Math.max(8, +this.size + delta));
    this.sizeChange.emit(this.size);
  }
}
```


# ngModel     
this is builtin data bind directive in angular     
hare space required ( "ninja.name" /> )*

```javascript
import { Component, OnInit } from '@angular/core';


@Component({
  selector: 'app-home',
  template: `
    <input type="text" [(ngModel)]="ninja.name" />
    <p>{{ninja.name}}</p>

    <!-- ngModel two data binding with radio button -->
    <input type="radio" value="one" name="school" [(ngModel)]="schoolType" (change)="selectType()" />
    <input type="radio" value="two" name="school" [(ngModel)]="schoolType" (change)="selectType()" />
    <input type="radio" value="three" name="school" [(ngModel)]="schoolType" (change)="selectType()" />

    <!-- ngModel two data binding with search mechanism. -->
    <span> Search : </span>
    <input type="text" [(ngModel)]="searchText">
    <ng-container *ngFor="let item of items">
        <div *ngIf="searchText === '' || item.toLowerCase().includes(searchText)" >
            {{item}}
        </div>
    </ng-container>
  `,
  styleUrls: ['./home.component.css']
})
export class HomeComponent  {

  public ninja = {
      name:"Yoshi",
      belt:"Black"
  };

  // ngModel two data binding with radio button
  public schoolType:string = '';
  public selectType():void{
    console.log("select type : ", this.schoolType);
  }

  // ngModel two data binding with search mechanism.
  public searchText:string ='';
  public items:string[]  = ["Sri Lanka", "Russia", "India"];



}
```


# Native Event Binding

### (Binding in same component)    
Event binding allows us to bind webpage events to a componsnts property or methods.    
Using event binding we can pass data from view to component.    

>file.ts

```javascript
import { Component, OnInit } from '@angular/core';


@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
  styleUrls: ['./home.component.css']
})
export class HomeComponent implements OnInit {

  alertMe(val){
    alert(val);
  };

  clickMessage = '';
  onClickMe() {
    this.clickMessage = 'You are my hero!';
  }

  values = '';
  onKey(event: KeyboardEvent) { // type of $event not same for everytime. type 'Event' also works here.  
    // Passing $event is a dubious practice because this is very big object.    
    // avoid this we can use template refernce variable.    
    this.values += (event.target as HTMLInputElement).value + ' | ';
  }

  onKeydown(event: Event):void{
    console.log("event :", event)
  }
  constructor() { }

  ngOnInit(): void {
  }

}
```

>file.html  

```html
<button (click)="alertMe('i am good person')" > Click Me</button>
<button type="button" (click)="onClickMe()">Click me!</button>
<input (keyup)="onKey($event)">
<!-- You can also use modifier keys, such as shift, alt, control, and the command -->
<!-- followgin code triger when click "shift+t" -->
<input (keydown.shift.t)="onKeydown($event)">
<!-- keydown.shift.alt.t use "code" keyword on mac avoid create character from key combination -->
<input (keydown.code.shiftleft.altleft.keyt)="onKeydown($event)" />
```

### Get user input from a template reference variable   
```typescript
@Component({
  selector: 'app-key-up2',
  template: `
    <input #box (keyup)="onKey(box.value)">
    <p>{{values}} {{box.value}}</p>

    <!-- Key event filtering(here enter key)  and On blur -->
    <input #box (keyup.enter)="onEnter(box.value)" (blur)="update(box.value)>
    <p>{{value}}</p>
  `
})
export class KeyUpComponent_v2 {
  values = '';
  onKey(value: string) {
    this.values += value + ' | ';
  }

  value = '';
  onEnter(value: string) { this.value = value; }
  update(value: string) { this.value = value; }
}
```

# Directives    

Directives are classes that add additional behavior to elements in your Angular applications.
Directive are simply an instruction to the dom.  

1. Components : Used with a template(html file). This type of directive is the most common directive type. eg: <app-root></app-root> in index.html
2. Attribute directives : Change the appearance or behavior of an element, component, or another directive.   
Attribute directives listen to and modify the behavior of other HTML elements, attributes, properties, and components. Built-in directives use only public APIs.   
NgClass, NgStyle, NgModel
3. Structural directives : Change the DOM layout by adding and removing DOM elements.    
NgIf, NgFor, NgSwitch (can't use in same tag. use ng-container)  

example of custom directive.    
```html 
<div changeDiveGreen > this is a Div </div>  
``` 
```typescript 
@Directive({
  selector:'[changeDivGreen]'
})
export class ChangeDivGreen{

}
```

## ngFor  

```typescript
@Component({
  selector: 'app-ngfortest',
  template: `
  <li *ngFor="let item of arr>
    {{item}}
  </li>

  <!-- Local variables  -->
  <!--   
  $implicit: T: The value of the individual items in the iterable (ngForOf).
  index: number: The index of the current item in the iterable.
  count: number: The length of the iterable.
  first: boolean: True when the item is the first item in the iterable.
  last: boolean: True when the item is the last item in the iterable.
  even: boolean: True when the item has an even index in the iterable.
  odd: boolean: True when the item has an odd index in the iterable.
  -->

  <li *ngFor="let item of arr;index as i; first as start">
    {{item}} index {{i}} {{start}}
  </li>
  `,
  styleUrls: ['./ngfortest.component.scss']
})
export class NgfortestComponent {
  
  public arr: Array<number> = [1,2,3,4,5]; 

}
```

## ngIf 

```typescript
@Component({
  selector: 'app-ngfortest',
  template: `
    <!-- with * -->
    <div *ngIf="hero" class="name">{{hero.name}}</div>    

    <!-- with bind -->
    <ng-template [ngIf]="hero">
      <div class="name">{{hero.name}}</div>
    </ng-template>  

    <!-- if else -->
    <div *ngIf="condition; else elseBlock">Content to render when condition is true.</div>
    <ng-template #elseBlock>Content to render when condition is false.</ng-template>

    <!-- if else then -->
    <div *ngIf="condition; then thenBlock else elseBlock"></div>
    <ng-template #thenBlock>Content to render when condition is true.</ng-template>
    <ng-template #elseBlock>Content to render when condition is false.</ng-template>

    <!-- if else creat local variable -->
    <div *ngIf="userObservable | async as user; else loading">
      Hello {{user.last}}, {{user.first}}!
    </div>
    <ng-template #loading let-user>Waiting... (user is {{user|json}})</ng-template>

    <!-- if else binding -->
    <ng-template [ngIf]="heroes" [ngIfElse]="loading">
    <div class="hero-list">...</div>
    </ng-template>
    <ng-template #loading>
    <div>Loading...</div>
    </ng-template>


  `,
  styleUrls: ['./ngfortest.component.scss']
})
export class NgfortestComponent {
  userObservable = new Subject<{first: string, last: string}>();
  public hero:object={
    name:'Samadhi'
  } 

}
```


# Custom Property and Event Binding

### Here we transfer data between two components.

we can send data parent to child using @input decorator and child to parent usgin @output    

@input : custom property binding (number, string, boolean, or object(function)).     
@output : custom event binding.

>child.ts
```javascript
@Component({
  selector: 'app-child',
  template : `
  `
})
export class ChildComponent {
   // property binding  without usgin alias   
   @Input() prop:string = '';

   // property binding  with usgin alias
   // @Input('alias_name') prop:string = '';

   // event binding
   @Output() newItemEvent:EventEmitter<string> = new EventEmitter<string>();  
   addNewItem(value: string) {
    this.newItemEvent.emit(value);
   }
}
```

>parent.ts
```javascript
@Component({
  selector: 'app-parent',
  templateUrl: `
    <!-- is there any argument then should provide "$event" -->
    <app-child [prop]="item" (newItemEvent)="nwItem($event)"  >Loading..</app-child>
  `
})
export class ParentComponent{
  public item: string = "no job";

  public nwItem(value:string):void{
      console.log("event from parent", value)
  }
}
```

# Template Reference Variable    
A template refernce variable is a reference to any DOM element, component or a directive in the template.    

```javascript
@Component({
  selector: 'app-child',
  template : `
    <table class="table">
        <thead>
            <tr>
                <th>customer</th>
                <th>controller</th>
            </tr>
        </thead>
        <tbody>
            <tr *ngFor="let customer of customers">
                <td>{{customer}}</td>
                <td><button  (click)="selectedCustomer = customer">select</button></td>
            </tr>
        </tbody>
    </table>
  `
})
export class ChildComponent {
  public selectedCustomer:string='';
  public customers:string[]=["samadhi", "lasksahan"];

}
```

```javascript
@Component({
  selector: 'app-parent',
  template: `
    <!-- just update input value with template ref variable -->
    <!-- here put keyup event for update template -->
    <input type="text" #myVariable (keyup)="0" >
    <p>{{myVariable.value}}</p>

    <!-- use ref variable pass data to component -->
    <input type="text" #pass  />
    <button (click)="sayHello(pass)">Say Hello</button>
    <p>{{myVariable.value}}</p>

    <!-- use ref variable pass data to component -->
    <app-child #selected></app-child>
    <p>{{selected.selectedCustomer}}</p>
  `
})
export class ParentComponent{

  // use ref variable pass data to component 
  public sayHello(inputElement: HTMLInputElement):void{
      console.log("text : ", inputElement.value)
  }

}
```

# ViewChild    

here we can access component from template using ViewChild decorator.   
and we can import child component in to our component and call it's function(but it's call servaral times )       

View queries are set before the ngAfterViewInit callback is called.


* selector - The directive type or the name used for querying.
* read - Used to read a different token from the queried elements.
* static - True to resolve query results before change detection runs, false to resolve after change detection. Defaults to false.


```javascript
@Component({
  selector: 'app-parent',
  template: `
    <div>
        <label for="">DOB :</label>
        <input type="date" #dateinput (blur)="calculateAge()">
    </div>
    <div>
        <label for="">Age :</label>
        <input type="text" #ageinput>
    </div>

    </div>
   
    <!-- import  child component and call it's function via template -->
    <app-child></app-child>
    {{ viewchild.sayHello() }}
  `
})
export class ParentComponent{

    // accesss template native element via template ref vatiable and @ViewChild
    @ViewChild('dateinput') dateofbirth! : ElementRef<HTMLInputElement>;
    @ViewChild('ageinput') age! : ElementRef;

    calculateAge():void{
        const birthYear:number = new Date(this.dateofbirth.nativeElement.value).getFullYear();
        const currentYear:number = new Date().getFullYear();
        const age:number = currentYear - birthYear;
        this.age.nativeElement.value= age;
    }

    // access child class using viewchild decorator 
    @ViewChild(ChildComponent, {static:true}) viewchild! : ChildComponent;

  }
}
```

```javascript
@Component({
  selector: 'app-child',
  template : ``
})
export class ChildComponent {

  // call this function from parent tempalte   
  // but this function call several times.   
  sayHello():void{
    console.log("Hello !!", ++this.count);
  }

}
```

# View Encapsulation   
The View Encapsulation is a concept or behaviour in angular, where component CSS styles are encapuslated in to the components view and do not effect the rest of the application.    


View Encapsulation types    
1. ViewEncapsulation.None     
2. ViewEncapsulation.Emulated (default)   add uniwue names for html and css attributes.  
3. ViewEncapsulation.ShadowDom   

Emulated 
```html
<!-- inside component class, tag, id styles all bind to _ngcontent-hxb-c18 attribute here -->
<!-- that's why inside component there are not common styels apply to child elements -->  
<!-- but after compile globle styles will add because class name still there -->
<button  class="btnx">Button</button> == > <button _ngcontent-hxb-c18="" class="btnx">Button</button>
```

None 
```html
<!-- inside component class, tag, id styles all apply as global -->
<!-- so this sytle going to map entire project that have same class, tag, id -->  
<button  class="btnx">Button</button> == > <button  class="btnx">Button</button>
```

ShadowDom 
```html
<!-- from this component create new dom and it's not add any styles except (*{}) -->
<!-- if this component child not a ShadowDom then this compoenent styles add to it's childrens   -->  
<button  class="btnx">Button</button> == > <button  class="btnx">Button</button>
```

# ng-content   

The ng-contents is used when we want to insert the content dynamically inside the component the helps to increase component reusability.  

This is very useful to pass child components(one or more) through common components.   

using ng-content we can pass content inside the component selector and when angular parses that content that appears at the place of ng-content.    

```javascript
@Component({
  selector: 'app-parent',
  template: `
    <!-- child tag will replace for ng-content tag -->
    <app-card>
        <h3 >this is header</h3> <!-- projected content -->
        <h3 >this is header 2</h3>  <!-- projected content -->
    </app-card>
    <app-card>
        <h2>this is header</h2>  <!-- projected content -->
    </app-card>

    <!-- event we have two ng-content tag child will only add for last ng-tag -->
    <app-card>
        <h3 >this is header</h3>
        <h3 >this is header 2</h3>
    </app-card>
    <app-card>
        <h2>this is header</h2>
    </app-card>

    <!-- use select attribute with parent class name to place tag with 
    multiple ng-content-->
    <app-card>
        <h3 class="c1">this is header</h3>
        <h3 class="c2">this is header 2</h3>
    </app-card>
    <app-card>
        <h2 class="c1" >this is header</h2>
    </app-card>
  `
})
export class ParentComponent{

}

```

```javascript
@Component({
  selector: 'app-child',
  template : `

    <!-- child tag will replace for ng-content tag -->
    <div class="frame">
        <ng-content ></ng-content>
    </div>

    <!-- event we have two ng-content tag child will only add for last ng-tag -->
    <div class="frame">
        <ng-content ></ng-content>
        <p> text ----------------------- </p>
        <ng-content ></ng-content>
    </div>

    <!-- use select attribute with parent class name to place tag with 
    multiple ng-content-->
    <div class="frame">
        <ng-content select=".c2"></ng-content>
        <p> text ----------------------- </p>
        <ng-content select=".c1"></ng-content>
    </div>
  `
})
export class ChildComponent {

}
```

# Angular Lifwcycle Hook.  
The Angular lifecycle hooks are the methods that angular invokes on the directives and components as it creates, changes and destroys them.   

When the angular application-start, it first creates and renders the root component. Then, it creates and rendres its Children's & their children. It forms a tree of components.   

Once Angular loads the components, it starts the process of rendering the view(template). To do that, it needs to check the input properties, evaluate the data bindings & expressions, render the projected content etc.   

Angular lets up know these events happed using lifecycle hooks. For Example:   
* "ngOnInit" when Angular initializes the component for the first time.   
* When a component's input property change, Angular invokes "ngOnChanges".   
* If the component is destroyed, Angular invokes ngOnDestroy.   

## Change detection cycle    
Change detection is the mechanism by which angular keeps the template is sync with the component.    

This run with every,    
1. input change.   
2. dom events.   
3. timer events (set timout, set interval, http request)   

if there any change it will update the dom.    


### projected content : 
Projectd content is the HTML content which replaces the <ng-content> directive in child component.    
### input bound properties :   
These are those properties of a component class which is decorated with @Input() decorator.  

### Constructor of a Component.    
1. Life Cycle of a component begins, when Angular creates the component class. First mothod that gets invoked is class "Constructor".   
2. "Constructor" is neither a life cycle hook nor it is specific to Angular. It is a javascript feature. It is a method whick gets invoked, when a class is created.    
3. When a constructor is called, at that point, none if the components input propertis are updated and available to use. Neither its child components are constructed. Projected contents are also not available.    
4. Once Angular instaintiages the class, it kick-start first change detection cycle of the component.


### 1. ngOnChanges lifecycle hook.   
1. It is executed right at the start, when a new component is created, and it also gets executed whehnever one if the bound input property changes.    
2. When change-detection-cycle detect any change, then only Angular invokes "ngOnChange" life cycle hook whenever any data bound input property(@input) of the component or directive changes.  

### 2. ngOnInit lifecycle hook.  
1. This hook is fired only once and immediately after create component and update its input properties.
2. child components, projected content are not available at here and @ViewChild, @ViewChildren, @ContentChild & @ContentChildren also can't use here.        
3. This is perfect palce where you want to add any initializaiton logic for your component.    

### 3. ngDoCheck lifecycle hook.   
1. This run when change-detection-cycle duration even it not detect any change(button click nothing change but "ngDoCheck" is working).    
2. Invokes after "ngOnInit" and "ngOnChange" , good to use custom change detection.   

### 4. ngAfterContenInit.  
1. This called after the component's projection content has been fully initialized.    
2. Works only onece when initializing.    
3. @ContentChild and @ContentChildren update before this hook.    
4. only for components.    

### 5. ngAfterContenChecked.  
1. This run when change-detection-cycle duration even it not detect any change.  
2. @ContentChild and @ContentChildren update before this hook.     
3. only for components.    

### 6. ngAfterViewInit.  
1. This run when component's view and all child views are fully initialized.  
2. @ViewChild and @ViewChildren update before this hook.     
3. Works only onece when initializing.     
4. only for components. 

### 7. ngAfterViewChecked.  
1. This involk after ngAfterViewInit and .  
2. run on every change detection(event nothing changed).     
3. only for components. 

### 8. ngOnDestroy.  
1. This involk before component remove from the dom.      
2. Use for some cleanup work(unsuscribe observable, detach event handlers to avoid memory leaks).     


```javascript
@Component({
  selector: 'app-parent',
  template: `
  <div>
      <input type="text" #inputSearch>
      <button (click)="onSubmit(inputSearch.value)">Submit</button>
      <app-lifecycle [value]="searchText">  
          <p>this is content element {{searchText}}</p>
      </app-lifecycle>
  </div>
  `
})
export class ParentComponent{
   public searchText:string='';
   public onSubmit(value:string):void{
      this.searchText = value;
   }
}
```

```javascript
@Component({
  selector: 'app-child',
  templateUrl: './child.component.html',
  styleUrls: ['./child.component.scss']
})
export class ChildComponent implements OnInit, OnChanges, 
AfterContentInit, AfterContentChecked, AfterViewInit, AfterViewChecked, OnDestroy {
  
  @Input() value:string='lanka';
  constructor() { 
    /* this should show empty string but show 'lanka' 
       because it's still not loaded to component. this run
       only one time*/
    console.log("constructor > ", this.value);
  }

  ngOnChanges(change:SimpleChanges):void{ // only take a argument    
    /* this should show empty string but and show empty string. 
       because here @input are loaded here. if change detected in change
       detection-lifecycle then this involk and show previous value and 
       new value.*/
    /* only text change and click button will call this fucntion */
    console.log("onChange > ", this.value);
    console.log("onChange value > ", change);
  }

  ngOnInit(): void {
    /* this should show empty string but and show empty string. 
       because here @input are loaded here. this run only one time
       because of @Input loaded here good initialize things.*/
    console.log("OnInit > ", this.value);
  }

  ngDoCheck(): void {
    /* this run in every change-detection event not change deteced 
       and @Input value still not here. */
    /* this will call two times because some file change in core.mjs */
    /* this will call even click submit button without chage text */
    console.log("DoChec > ", this.value);
  }

  ngAfterContentInit(){
    /* this will call even is there no projected content only one time */
    /* hare projected-content already updated in this stage */
    console.log("AfterContentInit  ");
  }

  ngAfterContentChecked(){
    /* this will call even is there no projected-content  */
    /* run in every change-detection-lifecycle even not changes detected */
    console.log("AfterContentChecked  ");
  }

  ngAfterViewInit(){
    /* this will call even is there no projected-content  */
    /* you can access native elements and child in this stage */
    console.log("AfterViewInit  ");
  }

  ngAfterViewChecked(){
    /* t */
    /* run in every change-detection-lifecycle even not changes detected */
    console.log("AfterViewChecked  ");
  }

  ngOnDestroy(){
    /* t */
    /* run just before current component destroy */
    console.log("OnDestroy  ");
  }
```

# @ContentChild   

use for access parent projected-content from child component class.

```javascript
@Component({
  selector: 'app-parent',
  template: `
      <h1>Parent Component</h1>
      <app-child>
        <p #paragraph>This is the paragraph</p>
      </app-child>
  `
})
export class ParentComponent{

  }
```

```javascript
@Component({
  selector: 'app-child',
  template : ``
})
export class ChildComponent implement  {
  @ContentChild('paragraph') paragraphE1: ElementRef;

  ngOnInit():void{
    console.log(this.paragraphE1) // UNDEFINED !!!!
  }
  ngAfterContentInit():void{
    console.log(this.paragraphE1) // show element 
    console.log(this.paragraphE1.nativeElement.textContent); // show text
  }
}
```

# Custom Attribute Directive.   
Drirectives are simply an instruction to the DOM.    
1. component directive. (only in tempalte view)   
2. attribute directive.(change behaviour or look)    
3. structural directive. (control dom element(add/remove))     

let's create attribute directive to change background color when we use it.   
you have to insert this directive to module.ts file in "declaration" array

```typescript 
@Directive({
    selector:'[setBackground]'
})
export class SetBackgroundDirective implement OnInit{
    /**
     * @param1 element :which we are put this directive
    */
    constructor(private element:ElementRef){
        // element.nativeElement.style.backgroundColor = '#CBE6C9';
        /* private argument in constructor makes private variable inside constructor and have access to outside of component */
    }

    ngOnInit{
       /* following function works even in constructor because it's a argument*/
       /* but good practice to put it inside ngOnInit */
       this.element.nativeElement.style.backgroundColor = '#CBE6C9';
    }
}
```

then add above "setBackground" directive to element.    

```typescript 
@Component({
  selector: 'app-parent',
  template : `
    <div setBackground >
       <p> This is demo HTML content </p>
    </div>
  `
})
export class ChildComponent {

}
```

# Renderer2 in Angular 


Access dom elements direcly in component.ts file is not good practice. here is why..

1. Angular keeps the component & the view in Sync using Template, data binding & change detection, etc. All of them are bypassed when we update the DOM Directly.    
2. DOM Manipulation works only in Browser. You will not able to use the Aoo in other platforms like a web-worker, in Server or in a Desktop, or in mobile app, etc. where there is no browser.   
3. The DOM APIs do not sanitize the data. Hence it is possible to inject a script, thereby, open our app an easy target for the XXS injection attack.   

let's see the better way to access DOM elements by using Renderer2   


```typescript 
@Directive({
    selector:'[appHighlight]'
})
export class SetBackgroundDirective implement OnInit{
    /**
     * @param1 element :which we are put this directive
     * @param2 render  : angular object/? that manipulate the dom
    */
    constructor(private element:ElementRef, private renderer: Renderer2){
        /* private argument in constructor makes private variable inside constructor and have access to outside of component */
    }

    ngOnInit{
        // add css style
        this.renderer.setStyle(this.element.nativeElement, 'backgroundColor', '#F198A');
        // add css class
        this.renderer.addClass(this.element.nativeElement, 'class-name-hare' );
        // add attribute
        this.renderer.setAttribute(this.element.nativeElement, 'title', 'this is example div' );
    }
}
```

then add above "appHighlight" directive to element.    

```typescript 
@Component({
  selector: 'app-parent',
  template : `
    <div appHighlight >
       <p> This is demo HTML content using renderer </p>
    </div>
  `
})
export class ChildComponent {

}
```

# @HostListner in Angular    

The @HostListner decorator listens to the DOM event on the host element and it reacts to that event by execution an event handler method.   

```typescript 
@Directive({
    selector:'[appHover]'
})
export class HoverDirective{
    /**
     * @param1 element :which we are put this directive
     * @param2 render  : angular object/? that manipulate the dom
    */
    constructor(private element:ElementRef, private renderer: Renderer2){
        /* private argument in constructor makes private variable inside constructor and have access to outside of component */
    }

    @HostListener('mouseenter') onmouseover(){
        this.renderer.setStyle(this.element.nativeElement, 'margin', '5px 10px');
        this.renderer.setStyle(this.element.nativeElement, 'padding', '30px 10px');
        this.renderer.setStyle(this.element.nativeElement, 'transition', '0.5s');
    }
    @HostListener('mouseleave') onmouseout(){
        this.renderer.setStyle(this.element.nativeElement, 'margin', '10px 20px');
        this.renderer.setStyle(this.element.nativeElement, 'padding', '10px 20px');
        this.renderer.setStyle(this.element.nativeElement, 'transition', '0.5s');
    }
}
```

then add above "appHover" directive to element.    

```typescript 
@Component({
  selector: 'app-parent',
  template : `
    <div appHover >
       <p> This is demo HTML content using renderer </p>
    </div>
  `
})
export class ChildComponent {

}
```

# @HostBinding in Angular.    

The @HostBinding decorator binds a host element property to a variable in a directive or a component.  

```typescript 
@Directive({
    selector:'[appBetterHighlight]'
})
export class BetterHighlightDirective{
    /**
     * @param1 element :which we are put this directive
     * @param2 render  : angular object/? that manipulate the dom
    */
    constructor(private element:ElementRef, private renderer: Renderer2){
        /* private argument in constructor makes private variable inside constructor and have access to outside of component */
    }

    /* you can add any count of hostbinding here */
    @HostBinding('style.backgroundColor') background: string = 'transparent'
    @HostBinding('style.border') border: string = 'none';

    @HostListener('mouseenter') mouseover(){
        this.background = 'pink';
        this.border = 'red 2px solid';
    }
    @HostListener('mouseleave') mouseout(){
        this.background = 'transparent';
        this.border = 'none';
    }
}
```

then add above "appBetterHighlight" directive to element.    

```typescript 
@Component({
  selector: 'app-parent',
  template : `
    <div appBetterHighlight >
       <p> This is demo HTML content using renderer </p>
    </div>
  `
})
export class ChildComponent {

}
```  


# Binding Directive Properties.     

Here we are talking pass data to any directive to make it more dynamic.

We take same example above to show how to pass data any directive using property binding.  

```typescript 
@Directive({
    selector:'[appBetterHighlight]'
})
export class BetterHighlightDirective implements OnInit{
 
    @Input () detaultColor:string = 'transparent';
    @Input () highlightColor:string = 'pink';

    ngOnInit(){
        // at the start detaultColor is 'transparent'
        this.background = this.detaultColor;
        // after this it will be 'yellow'
    }

    /* you can add any count of hostbinding here */
    @HostBinding('style.backgroundColor') background: string = 'transparent'
    @HostBinding('style.border') border: string = 'none';

    @HostListener('mouseenter') mouseover(){
        this.background = this.highlightColor;
        this.border = 'red 2px solid';
    }
    @HostListener('mouseleave') mouseout(){
        this.background = this.detaultColor;
        this.border = 'none';
    }
}
```

then add above "appBetterHighlight" directive to element.    

```typescript 
@Component({
  selector: 'app-parent',
  template : `
    <div appBetterHighlight [detaultColor]="yellow" [highlightColor]="red" >
       <p> This is demo HTML content using renderer </p>
    </div>
  `
})
export class ChildComponent {

}
```  

As we talk ngStyle and ngClass also attribute directive. But so far in our custom attribute directives doesn't wrapped with double square brackets. We can use that way too when we have one main property to bind. For this we use that main proterty allias as our directive name. Now we can't use  'highlightColor' variable anymore on template but can use in class.

```typescript 
@Directive({
    selector:'[appBetterHighlight]'
})
export class BetterHighlightDirective implements OnInit{
 
    @Input () detaultColor:string = 'transparent';
    @Input ('appBetterHighlight') highlightColor:string = 'pink';

    ngOnInit(){
        // at the start detaultColor is 'transparent'
        this.background = this.detaultColor;
        // after this it will be 'yellow'
    }

    /* you can add any count of hostbinding here */
    @HostBinding('style.backgroundColor') background: string = 'transparent'
    @HostBinding('style.border') border: string = 'none';

    @HostListener('mouseenter') mouseover(){
        this.background = this.highlightColor;
        this.border = 'red 2px solid';
    }
    @HostListener('mouseleave') mouseout(){
        this.background = this.detaultColor;
        this.border = 'none';
    }
}
```

then add above "appBetterHighlight" directive to element.    

```typescript 
@Component({
  selector: 'app-parent',
  template : `
    <div [appBetterHighlight]="'red'" [detaultColor]="'yellow'" >
       <p> This is demo HTML content using renderer </p>
    </div>
  `
})
export class ChildComponent {

}
```  

what happen when we bind property that name common with html property.  
```html 
<div title="this is title"> </div>
<div [title]="true"> </div>
``` 
hare angular first check custom directive if there not the check for the native element.  


# Custom appClass directive

# Conditional Directive in Angular

# How Structural Directive Works.    

A structural directive manipulate the DOM by adding or removing element to or from the DOM on which we use it.    
we prefix "Structural Directive" with asterix.   
when angular find the asterix angular know this is structural directive and agular create a template(ng-template) for it and it's wrap the view of the structural directive inside created template. And in the template angular not use asterix but use as just property bind.  

following example shows angular don't use "asterix" internally.    

```html
<div *ngIf="show">
    <p>this is notification.</p>
</div>

<!-- This convert to -->

<ng-template [ngIf]="show">
    <div>
        <p>this is notification.</p>
    </div>
</ng-template>
```

when we have if-else    

```html
<div *ngIf="show; else bottom">
    <p>this is notification.</p>
</div>

<!-- This convert to -->

<ng-template [ngIf]="show" [ngIfElse]="bottom">
    <div>
        <p>this is notification 1.</p>
    </div>
</ng-template>
<ng-template #bottom >
    <div>
        <p>this is notification 2.</p>
    </div>
</ng-template>
```


# Custom Structural Directive

```bash
$ ng g d if
```
above cmd create following two files.   
1. if.directive.ts   
2. if.directive.spec.ts    


Attribute directive change look and beheviour of elements but structural directive manipulate by adding or removing from the dom.  

for that we have to consider    
1. what to add or remove.   
2. from where to add or remove.   


```typescript
@Directive({
  selector: '[appIf]'
})
export class IfDirective {

   /** 
    *  @pram1 template wrapper element
    *  @pram2 viewContainer element inside wrapper element
   */ 
   constructor(private template: TemplateRef<any>, private viewContainer: ViewContainerRef){

   }

   /*
    @Input() set displayView(condition: boolean){
        if(condition) {
            this.viewContainer.createEmbeddedView(this.template);
        } else{
            this.viewContainer.clear();
        }
    }

    here to angular find this directive we can do in two ways.   
    1. add allias to @Input as 'appIf'.
    2. change displayView to appIf.

   */

    /* method 1 */

    @Input('appIf') set displayView(condition: boolean){
        if(condition) {
            this.viewContainer.createEmbeddedView(this.template);
        } else{
            this.viewContainer.clear();
        }
    }

    /* method 2 */

   @Input() set appIf(condition: boolean){
     if(condition) {
        this.viewContainer.createEmbeddedView(this.template);
     } else{
        this.viewContainer.clear();
     }
   }
}
```



# Think in Angular.  

## select most relevant style attribute or style bind for the element.  
* static or variable or dynamic 
* single or multiple or function    
## select most relevant for element.   
* select (click) event for button.
* select (change) event for radio button with [(ngMudule)]  
## avoid pass html element data with event.   
* use template reference variable.   
* use two data binding eg: builtin [(ngModule)].   
## can't use more than on Structural directives in single tag.  
* use ng-container.  
## local referance   
* can pass class variable data to parent view template.   
* can pass view template data to class using viewchild.   



? null equlize operator 
#bounce sign 





[Routing](#Routing)
# Routing

*  Here we declare routes in the `app-routing.module.ts` file.
*   The path: "" parameter relates to the url where the user will land when entered in the browser’s address bar.

* In first good to make new component

 ```bash
  $ ng generate component [name_of_component]
 ```
* When you are generate new component it will automatically will update with "declarations" and it's imports on `app.module.ts` file.

>app-routing.module.ts

```javascript
import { NgModule } from '@angular/core'; //#
import { Routes, RouterModule } from '@angular/router'; //#

// import your route files
import { HomeComponent } from "./home/home.component";
import { DirectoryComponent } from "./directory/directory.component";

// make your router path
const routes: Routes = [
  {
    path:'directory',
    component :DirectoryComponent,
  },
  {
    path:'', /* home  */
    component :HomeComponent,
  }
];


@NgModule({
  imports: [RouterModule.forRoot(routes)], //#
  exports: [RouterModule] //#
})
export class AppRoutingModule { } //#
```

following code show how to link our created routes on root.html file.

>root.html  (app.component.html)

```html
<!--   <app-home [prop]="school" (onYell)="yell($event)" >Loading..</app-home>  -->
<router-outlet> </router-outlet>
```



  URL pattern /heroes/:limit. Example: /heroes/20
      You can get raw value by using route.snapshot.paramMap.get.
      Subscribe from route.paramMap to get params

  URL pattern /heroes. Example: /heroes?limit=20
      You can get raw value by using route.snapshot.queryParamMap


# Adding Links

Following tutorial we are linking previous created routes on html page with two methods .
1. with normal  href html linking ( with reload hole page )
2. with special angular variables( non reload hole page )

```html
<header>
  <h1>{{title}}</h1>
  <nav>
    <ul>
      <!-- first method -->
      <li> <a href="/" >Home</a> </li>
      <li> <a href="/directory" >directory</a> </li>
      <li> <a href="/tables" >tables</a> </li>
    </ul>
    <ul>
      <!-- second method -->
      <li> <a [routerLink] ="['']" >Home</a> </li>
      <li> <a [routerLink] ="['directory']" >directory</a> </li>
      <li> <a [routerLink] ="['tables']" >tables</a> </li>
    </ul>
  </nav>
</header>

<section id="main">
   <!--   <app-home [prop]="school" (onYell)="yell($event)" >Loading..</app-home>  -->
   <router-outlet> </router-outlet>
</section>
```

# Route Params

* we are going to grap link parameter on 'tables' path.  
* first we need  add variable on 'tables' path in where we created routes(angular 9 > app-routing.module.ts ).

```javascript
import { NgModule } from '@angular/core';
import { Routes, RouterModule } from '@angular/router';

import { HomeComponent } from "./home/home.component";
import { DirectoryComponent } from "./directory/directory.component";
import { TableComponent } from "./table/table.component";

const routes: Routes = [
  {
    path:'directory',
    component :DirectoryComponent,
  },
  {
    path:'tables',
    component :TableComponent,
  },
  {
    path:'tables/:name', /*add> :name*/
    component :TableComponent,
  },
  {
    path:'', /* home  */
    component :HomeComponent,
  }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }

```


* secondly we need grep link variable from url

```javascript
import { Component, OnInit } from '@angular/core';
import { ActivatedRoute } from '@angular/router'  /*add> line */

@Component({
  selector: 'app-table',
  templateUrl: './table.component.html',
  styleUrls: ['./table.component.css']
})
export class TableComponent implements OnInit {
  ninja: string ;
  constructor( private route:ActivatedRoute ) {
    this.ninja = route.snapshot.params['name'];
    //console.log("param value :" ,this.ninja);
  }

  ngOnInit(): void {
  }

}

```

* lastly as working demonstration we can implement link variable value on "table.component.html"   

```html
    <p>table works!</p>
    <p>{{ninja}}</p>
```

# Directive Introduction

* Directives are instructions which tell Angular to do something.     
eg:
```html
    <router-outlet> </router-outlet>   
    [routerLink]=""
```    

There are two types of Directive
Attribute:
* Interacts with the element it's on to change it's properties.(eg:ngClass>change element class)
Structural:
* Change the structure of the HTML code.(eg:ngIf)

## Attribute Directive   

following example we use "ngClass" html element class selector on "file.component.html" page.

> file.component.html        

```html
<!-- ngClass class expection property here {}-->
<p [ngClass]="{'blue':false,'red':true,'underline':true}">directory works!</p>


<style>
  .blue{color:blue;}
  .red{color:red;}
  .underline{text-decoration: underline;}
</style>
```
even we can use this selector as property binder on "file.component.ts" file.advantage is we can dynamically change ngClass object on file.component.ts file.   

> file.component.html     

```html

<p [ngClass]="classes">directory works!</p>

<style>
  .blue{color:blue;}
  .red{color:red;}
  .underline{text-decoration: underline;}
</style>
```

> file.component.ts

```javascript
import { Component, OnInit } from '@angular/core';


@Component({
  selector: 'app-directory',
  templateUrl: './directory.component.html',
  styleUrls: ['./directory.component.css']
})
export class DirectoryComponent implements OnInit {
  classes = {'blue':true,'red':false,'underline':true };
  constructor( ) {

  }

  ngOnInit(): void {
  }

}
```

## Structural Directive  

```html

<p *ngIf="true">Only show if test it true </p>

```
this example also bind with variable from file.component.ts file for dynamically changes .

# ngFor


> home.ts      

```javascript

fruits: Array<string> = ['Apple', 'Orange', 'Banana'];

```

> home.html      

```javascript
<p *ngFor="let fruit of fruits; count as i;index as p" >
    {{fruit}} {{i}} <span></span>
</p>
```
you can use "span" tag inside p tags.
you can access ngFor variables using {{your_variable_inside_ngFor_condition}}   

# ngContent  

passing another template to child inside child template tag.    

>parent.tempate.html file

```html
<app-testcompo>
    <p #showme >samadhi laksahan piyasiri</p>
</app-testcompo>
```

>child.template.html file   

```html
<p >testcompo works!</p>
<ng-content></ng-content>
```

when we want access parent element within child element.
so we can use "@ContentChild" inside child compoent.ts file.
>child.component.ts file      

```typescript
import { AfterContentInit, Component, ContentChild, ElementRef, OnInit } from '@angular/core';

@Component({
  selector: 'app-testcompo',
  templateUrl: './testcompo.component.html',
  styleUrls: ['./testcompo.component.scss']
})
export class TestcompoComponent implements OnInit,AfterContentInit {

  constructor() { }

  @ContentChild('showme') public compo:ElementRef;

  ngOnInit(): void {
  }

  ngAfterContentInit():void{
    console.log('after content init in child :', this.compo);
  }

}
```

# ngTemplate

These template elements only work in the presence of structural directives.

different way to access ng-template.

1. by using structural directive.     
depend on ,mark>*ngIf</mark> directive it will show the ng-template.    

```html
<div *ngIf="false;else showTemplateOne;" >
    <p>no template </p>
</div>

<div *ngIf="true; then showTemplateTwo ;else showTemplateOne;" >
    <p>no template </p>
</div>

<ng-template #showTemplateOne >
    <p>show template one</p>
</ng-template>

<ng-template #showTemplateTwo >
    <p>show template two</p>
</ng-template>
```
2. passing data to ng template.    
you can pass n number of variables to ng-template.   
you can use <mark>div</mark> instead of <mark>ng-container</mark>.  

```html
<ng-container *ngTemplateOutlet="showTemplateOne; context:{ varOne : 'show template one', varTwo:'var two value'}">
    samadhi laksahan
</ng-container>

<ng-template #showTemplateOne let-varone="varOne" let-vartwo="varTwo">
    <p>{{varone}}</p>
    <p>{{vartwo}}</p>
</ng-template>
```
3. send data from component.ts file to ng-template.   
we need to add id for both tags for access from component.ts file.    

```html
<ng-container #placeholder> </ng-container>

<ng-template #showTemplate let-varone="varOne" let-vartwo="varTwo" >
     <p>{{ varone }}</p>
     <P>{{ vartwo }}</P>
</ng-template>
```

compoents.ts file  (static:true)

```typescript
import { Component, OnInit, TemplateRef, ViewChild, ViewContainerRef } from '@angular/core';

@Component({
  selector: 'app-main',
  templateUrl: './main.component.html',
  styleUrls: ['./main.component.scss']
})
export class MainComponent implements OnInit {

  constructor() { }

  @ViewChild('placeholder', {read : ViewContainerRef, static:true}) public container:ViewContainerRef;
  @ViewChild('showTemplate', {static:true}) public template:TemplateRef<any>;


  ngOnInit(): void {
    // because of we are using "static:true" we can use viewchild inside ngOnInit
    // otherwise we have to use "ngAfterViewInit"
    this.container.createEmbeddedView(this.template, {varOne:'show template one', varTwo:'show template two'});
  }

}
```

4. set compoent using ng-template

```html
<ng-container [ngTemplateOutlet]="showTemplate" > </ng-container>

<ng-template #showTemplate >
    <app-testcompo></app-testcompo>
</ng-template>
```

5. use like ng-content.

ng-content not work for for-loops    

> parent.component.html

```html
<app-testcompo>

    <ng-template #testcompo >
        <p>samadhi laksahan</p>
    </ng-template>

</app-testcompo>
```

> child.component.html    

```html
<p >testcompo works!</p>

<ng-container [ngTemplateOutlet]="testCompoRef">
</ng-container>
```

> child.component.ts   

"@ContentChild" usually using for "ng-content" only. But here we are using "@ContentChild"
for "ngTemplate" for get it's ID(#testcompo) from parent component for trick.

```typescript
import { Component, ContentChild, OnInit, TemplateRef } from '@angular/core';

@Component({
  selector: 'app-testcompo',
  templateUrl: './testcompo.component.html',
  styleUrls: ['./testcompo.component.scss']
})
export class TestcompoComponent implements OnInit {

  constructor() { }

  @ContentChild('testcompo', {static:false})  testCompoRef:TemplateRef<any>;

  ngOnInit(): void {
  }
}
```

# add bootstrap to angular
this is new method to add full package of boostrap for angular    

option one:    
```bash
$ ng add @ng-bootstrap/ng-bootstrap
```

option two:

```bash
$ ng install boostrap
```
import following bootstrap directory in 'angular.json' file.
```json
"styles": [
              "node_modules/bootstrap/dist/css/bootstrap.min.css",
              "src/styles.scss"
          ],
```

# add modal with bootstrap

to install bootstrap

```bash
npm install --save @ng-bootstrap/ng-bootstrap
# should take care about related packages version
#or
npm add  @ng-bootstrap/ng-bootstrap
```

>package.json file
```json
"@angular/localize": "~10.0.11",
"@ng-bootstrap/ng-bootstrap": "^8.0.4", # not a latest version
"bootstrap": "^4.5.0", # not a latest version
```

>app.module.ts    

```typescript
import {NgbModule} from '@ng-bootstrap/ng-bootstrap';

@NgModule({
  declarations: [
    ...
  ],
  imports: [
    ...

    NgbModule

  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```
>Component Controller

```typescript
import { TemplateRef, ViewChild } from '@angular/core';
import { NgbModal } from '@ng-bootstrap/ng-bootstrap';

@Component({
  selector: 'app-app-registration',
  templateUrl: './app-registration.component.html',
  styleUrls: ['./app-registration.component.css']
})

export class AppRegistrationComponent implements OnInit {

  @ViewChild('editModal') editModal : TemplateRef<any>; // Note: TemplateRef

  constructor(private modalService: NgbModal) { }

  openModal(){
    this.modalService.open(this.editModal);
  }

}
```
>Component HTML

```typescript
<ng-template #editModal let-modal>

<div class="modal-header">
  <h4 class="modal-title" id="modal-basic-title">Edit Form</h4>
  <button type="button" class="close" aria-label="Close" (click)="modal.dismiss()">
    <span aria-hidden="true">&times;</span>
  </button>
</div>

<div class="modal-body">

  <form>
    <div class="form-group">
      <label for="dateOfBirth">Date of birth</label>
      <div class="input-group">
        <input id="dateOfBirth" class="form-control" placeholder="yyyy-mm-dd" name="dp" ngbDatepicker #dp="ngbDatepicker">
        <div class="input-group-append">
          <button class="btn btn-outline-secondary calendar" (click)="dp.toggle()" type="button"></button>
        </div>
      </div>
    </div>
  </form>

</div>

<div class="modal-footer">
  <button type="button" class="btn btn-outline-dark" (click)="modal.close()">Save</button>
</div>

</ng-template>

```
if you just install then you have to install following package
1. boostrap
2. localize
3. add script file for angular.js file.

you can just add component url where you want to display as it button

#  import component

import another components to component.

add "@Injectable" decoretor to top of class.

```typescript
import { Component, Injectable, OnInit} from '@angular/core';

@Injectable({
  providedIn: 'root'
})

@Component({
  selector: 'app-processing',
  templateUrl: './processing.component.html',
  styleUrls: ['./processing.component.scss']
})
export class ProcessingComponent implements OnInit {
  constructor() {}
}
```

and just import component and add it to constructor    

```typescript  
import { Component,  OnInit } from '@angular/core';
import { ProcessingComponent } from 'src/app/components/processing/processing.component';

@Component({
  selector: 'app-main',
  templateUrl: './main.component.html',
  styleUrls: ['./main.component.scss']
})
export class MainComponent implements OnInit  {

  constructor(private processing: ProcessingComponent){
  }

  ngOnInit(): void {
  }
}
```

# get data from api

to create new service
$ ng generate service <service-name>

just think we make service call 'http'

> name.service.ts    

````javascript
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http'; /* add new > line*/

@Injectable({
  providedIn: 'root'
})
export class HttpService {

  constructor(private http:HttpClient) { } /* add new > 'private http:HttpClientModule' */

  myMethod(){  /* add new > fucntion */
      return this.http.get('https://api.openbrewerydb.org/breweries');
  }

}
````

> app.module.ts   

````javascript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';
import { AppRoutingModule } from './/app-routing.module';
import { HomeComponent } from './home/home.component';
import { ProductsComponent } from './products/products.component';

import { HttpClientModule } from '@angular/common/http'; /* add new > line */



@NgModule({
  declarations: [
    AppComponent,
    HomeComponent,
    ProductsComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    HttpClientModule, /* add new > line */
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
````

> home.component.ts  

````javascript
import { Component, OnInit } from '@angular/core';

import { HttpService } from '../http.service' /* add new > line*/

@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
  styleUrls: ['./home.component.css']
})
export class HomeComponent implements OnInit {

  constructor(private _http:HttpService) { } /* add new > 'private _http:HttpService' */

  ngOnInit(): void {

    this._http.myMethod().subscribe(data=>{ /* add new > function*/
       console.log("api data : ", data);
    });

  }

}

````

# angular deploy with node js

## Proxy To Backend

Using the proxying support in webpack's dev server we can highjack certain URLs and
send them to a backend server. We do this by passing a file to --proxy-config.
for more info you can see[documentation](https://github.com/angular/angular-cli/blob/master/docs/documentation/stories/proxy.md).     

you have to customly create <name>.json file for proxy
``` javascript
{
  "/api": {
    "target": "http://localhost:3000",
    "secure": false
  }
}
```

to run angular using Proxy
```shell
$ ng serve --proxy-config proxy.conf.json
```

store on dist file on <mark>static-folder</mark> or <mark>nginx-server</mark>
```javascript
app.use(express.static(path.join(__dirname,'./dist/my-app/')));
```

use Get respons to send html page .
```javascript
app.get('/',function(req,res){
    return res.sendFile(path.join(__dirname,'./dist/my-app/index.html'));
});
```

# uninstall angular-cli

Using following commands to uninstall :

```shell
npm uninstall -g @angular/cli
npm cache clean --force  // use os admin
```

reinstall angular :

```shell
npm install -g @angular/cli
```

# Optimize Your Angular App

1. ChangeDetectionStrategy.OnPush    
Angular utilized Zone.js to monkey-patch each asynchronous event, so whenever any event occurs Angular runs change detection over its component tree

This OnPush change detection strategy disables CD to be run on a component and its children.   

2. Detaching the Change Detector


3. Local Change Detection  

4. Run outside Angular  


5. Use pure pipes  
  Pipes makes cache.
  We cache the results and return them when next the same input occurs.

So no matter how many times the pipe is called with an input, the bigFunction is called once and the cached results are just returned on subsequent calls.

> with none pure     

```javascript
function bigFunction(val) {
    ...
    return something
}@Pipe({
    name: "util"
})
class UtilPipe implements PipeTransform {
    transform(value) {
        return bigFunction(value)
    }
}
```

> with  pure     

```javascript
function bigFunction(val) {
    ...
    return something
}@Pipe({
    name: "util",
    pure: true // **add
})
class UtilPipe implements PipeTransform {
    transform(value) {
        return bigFunction(value)
    }
}
```

6. Use trackBy option for *ngFor directive  



7. Optimize template expressions     

"func()" will work every CD and it's very bad.

```javascript
@Component({
    template: `
        <div>
            {{func()}}
        </div>
    `
})
class TestComponent {    func() {
        ...
    }
}
```


8. Web Workers

JS is a single-threaded language,  non-UI algorithm gets heavy we will see that it will impact the UI thread slowing it down. Web Worker is a feature added that enables us to create and run code in another thread.

9. Lazy-Loading    

```javascript
const routes: Routes = [
    {
        path: '',
        component: HomeComponent
    },
    {
        path: 'about',
        loadChildren: ()=> import("./about/about.module").then(m => m.AboutModule)
    },
    {
        path:'viewdetails',
        loadChildren: ()=> import("./viewdetails/viewdetails.module").then(m => m.ViewDetailsModule)
    }
]@NgModule({
    exports: [RouterModule],
    imports: [RouterModule.forChild(routes)]
})
class AppRoutingModule {}
```
10. 10. Preloading

```javascript
class OurPreloadingStrategy implements PreloadingStrategy {
    preload(route: Route, fn: ()=> Observable <any>) {
        // ...
    }
}
```




#electron

to install electron

```bash
npm install electron --save-dev
```

change imdex.html file  with single period in front of slash  

```html
<base href="./">
```

create main.js file inside src/ file (root directory)

```javascript
const { app, BrowserWindow } = require('electron');

let win;

function createWindow(){
    // create browser window
    win= new BrowserWindow({
        width: 600,
        height: 600,
        backgroundColor: '#ffffff',
        //icon: `file://${__dirname}/dist/assets/logo.png`
    })

    win.loadURL(`file://${__dirname}/dist/index.html`);

    // to open devTools during development
    //win.winContents.openDevTools();

    // event when the window is closed
    win.on('closed', function(){
        win= null
    });




}

// Create window on electron initialization
app.on('ready',createWindow);

// Quit when all windows are closed
app.on('window-all-closed', function(){

    // On macOS specific close process
    if(process.platform !== 'darwin'){
        app.quit();
    }

})

app.on('activate', function(){

    // On macOS
    if(win === null){
        createWindow();
    }

})
```

let change package.json file to build and run electron app.        
add following two lines.

```json
{
  "main": "main.js",
  "scripts": {
    "electron": "electron .",
    "electron-build": "ng build --prod"
  }
}
```

to run electron app with angular    

```bash
$ npm run electron-build
$ npm run electron
```

to create executable files for different OS    

```bash
npm install electron-packager -g    
npm install electron-packager -D

```
