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

go to /src/app/app.component.ts     
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
  styles: ['h1 { font-weight: normal; }']
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

# you can remove styles and add styles to template    

```   
show app.component.ts file "app-root" in index.html file and "app-root" on browser inspect.  


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

# Data Binding

### data transfer from file.ts to file.html in same component


>file.ts

```javascript
import { Component, OnInit } from '@angular/core';


@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
  styleUrls: ['./home.component.css']
})
export class HomeComponent implements OnInit {
  homeTitle = "this data from homeComponent class";

  constructor() { }

  ngOnInit(): void {
  }

}
```

>file.html  

```html
<p>{{homeTitle}}</p>
```

# Property Binding

### data transfer from file.ts to file.html in same component

This thing can do with previous method too.    
```html
<input value="{{myString}}" />
```
But as a improvment here we are use '[property_name ]' to get this property name's value from file.ts.    
```html
<input [property_name ]="value_variable_located_in_ts_file" />
```

### Binding to HTML properties
  * Native HTML properties: [value]="express"   
      ```html
         <input value="type some thing" />
      ```
  * Custom-made properties: [myProp]="express"   
      ```html
         <input count="true" />
      ```
  * Built in angular directives: [ngClass]="express"   
      ```html
         <input count="true" />  ????
      ```

### Binding to HTML properties  


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

### Here dynamically changing value from shared variable(ninja) that located in file.ts .(Binding in same component)

>file.ts

```javascript
import { Component, OnInit } from '@angular/core';


@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
  styleUrls: ['./home.component.css']
})
export class HomeComponent implements OnInit {

  public ninja = {
      name:"Yoshi",
      belt:"Black"
  };

  constructor() { }

  ngOnInit(): void {
  }

}
```

>file.html  

```html
<input [(ngModel)]="ninja.name" />
<p>{{ninja.name}}</p>
```
*  *space required ( "ninja.name" /> )*

* In html file when value change of input field then dynamically it change value of p tags.    
* "ngModel" is unique name binder for make communicate between file.ts and file.html .



# Native Event Binding

### Here we send click event from file.html to file.ts in same component. (Binding in same component)

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

  constructor() { }

  ngOnInit(): void {
  }

}
```

>file.html  

```html
<button (click)="alertMe('i am good person')" > Click Me</button>
```


# Custom Property Binding

### Here we transfer data between two components.

we are using data sender component's html file as media of transferring between two components.     
data sending parent to child.     

>app.ts

```javascript
import { Component } from '@angular/core';
import { NgModule } from '@angular/core';

//import { ROUTER_DIRECTIVES } from "@/angular/router";

@Component({
  selector: 'app-root', /* selector of index.html*/
  templateUrl: './app.component.html', /**/
  /*template : '<h1>{{title}}</h1>',*/
  styleUrls: ['./app.component.css'],
  //directives : [ ROUTER_DIRECTIVES ]
})
export class AppComponent {

  public school ={
    name:"Asoka Collage",
    adress:"Colombo 10"
  };

}

```

>root.html  

```html
<app-home [prop]="school"  >Loading..</app-home>
```


>file.ts

```javascript
import { Component, OnInit , Input} from '@angular/core';

@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
  styleUrls: ['./home.component.css']
})
export class HomeComponent implements OnInit {

  @Input() prop;

  constructor() { }

  ngOnInit(): void {
  }

}
```

>file.html  

```html
<p>{{prop.name}}</p>
<p>{{prop.adress}}</p>
```
Finally we can represent data values from app.component.ts on home.component.html


# Custom Event Binding

### Here we make custom event among components.    
event sending child to parent.

In here we make app.html `(onYell)` event listen from home.ts using  
`@Output onYell = new EventEmitter()``

To control custom event `(onYell)` from different component we make native `(click)` event on home.html page and when if fire then it's inside function `fireYellEvent` we can `onYell.emit(e)` the custom function on app.html .

>app.ts (custom event's fire function )

```javascript
import { Component } from '@angular/core';
import { NgModule } from '@angular/core';

@Component({
  selector: 'app-root', /* selector of index.html*/
  templateUrl: './app.component.html', /**/
  /*template : '<h1>{{title}}</h1>',*/
  styleUrls: ['./app.component.css'],
  //directives : [ ROUTER_DIRECTIVES ]
})
export class AppComponent {
  //
  yell(e){
     alert("I am yelling...");
  }
}

```

>root.html  (custom event )

```html
 <app-home (onYell)="yell($event)" >Loading..</app-home>
```


>file.ts (make listem the custom event and make it's emit with click event)

```javascript
import { Component, OnInit , Input, Output , EventEmitter} from '@angular/core';

@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
  styleUrls: ['./home.component.css']
})
export class HomeComponent implements OnInit {

  /* make listener for custom event
     @Output() mean...
  */
  @Output() onYell = new EventEmitter();

  fireYellEvent(e){
    this.onYell.emit();
  }

  constructor() { }

  ngOnInit(): void {
  }

}

```

>file.html  (make native click event )

```html
<button (click)="fireYellEvent($event)" > Hit Me</button>
```

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
