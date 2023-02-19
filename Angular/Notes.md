## What is Angular?
Angular is an open-source web application development framework created by Google. It is used to build frontend, single-page applications that run on JavaScript. It is a full-fledged framework, i.e., it takes care of many aspects of frontend web applications such as HTTP requests, routing, layout, forms, reactivity, validation, etc.

## What is TypeScript?
The TypeScript feature offered by Angular is preferred by a majority of Front-End Developers. TypeScript helps in efficiently detecting bugs and helps in easy compilation by its automatic populating functionality. Also, it offers rich interfaces, access modifiers, hybrid types etc. All these combined lead to reduction in the developing time.

# The architecture of Angular comprises the following elements. The pictorial representation of the same is given below:

* Components and Templates
* Ng Modules
* Metadata
* Data Binding
* Directives
* Services
* Dependency Injection

## What is a bootstrapping module?
In Angular, the root module used for bootstrapping or launching the application is known as the ‘Bootstrapping Module’. A Bootstrapping Module is present in every Angular app and it is stored in the AppModule class. Infact, the Bootstrapping module is also called the AppModule.

## What is the purpose of the async pipe?
The async pipe subscribes to an Observable or Promise and returns the latest value it has emitted. When a new value is emitted, the async pipe marks the component to be checked for changes. When the component gets destroyed, the async pipe unsubscribes automatically to avoid potential memory leaks.


## What is the option to choose between inline and external template?
Usually, inline templates are used for small codes and external templates are used for comparatively bigger views. However, the choice of inline or external templates is sometimes based on organization policy, situations etc.

## How do you categorize data binding types?
Data Binding in Angular is categorized into Two types:

* One Way Data Binding
* Two-Way Data Binding

# In One way data binding, the changes in the state affect the view from component to view template

# Two-way Data Binding, the changes in the view can lead to change in the model. Similarly, any changes in the model can change the view from component to view template.

## How do you define typings for custom elements?
Defining typings for custom elements in Angular can be done by using NgElement and WithProperties exported from @angular/elements. The following component is a simple container with input property:

@Component(…)
class MyDialog {
@Input() content: string;
}


## Explain how custom elements work internally?
Let us understand the internal working of custom elements in steps:

* Registration of the custom elements:
Angular registers the custom elements using the createCustomElement() function. This function converts a component into a class that can be registered with the browser as a custom element.

* Addition of the custom element to DOM: 
The custom element is added to DOM similar to a built-in HTML.

* Browser instantiates component based class: 
Once the custom element is added to DOM, an instance of the registered class is created by the browser and added to the DOM.

* Data binding and Change detection:
In the final step, the created instance enables data binding and change detection. The template content is rendered using the component and DOM data.

## How to transfer components to custom elements?
There are two important steps to be followed in order to transfer components to custom elements:

* Creating a custom element class: 
As a first step, build a custom element class using the createCustomElement() function provided by Angular. The function converts an Angular component (including its dependencies) to a custom element. The NgElementConstructor interface is implemented through this conversion which, in turn, creates a constructor class that is used for producing a self-bootstrapping instance.

* Registering element class with browser:
The customElements.define() function is used to register the configured constructor, and its associated custom-element tag with the browser’s CustomElementRegistry.


## What are the mapping rules between Angular component and custom element?

* The component input properties are parsed with the corresponding attributes for the custom element using the createCustomElement() API.

* The Component outputs are dispatched as HTML Custom Events and have the name of the custom event that also matches the output name.

## How do you chain pipes?
use more pipe one by one like below example.

example:

Today is {{ today | date:’fullDate’ | uppercase}}.

## What is a custom pipe?
They are nothing but customized pipes and were earlier known as ‘Filters’ in Angular

import { Pipe, PipeTransform } from '@angular/core';  
@Pipe({name: 'Pipename'}) 

export class Pipeclass implements PipeTransform { 
   transform(parameters): returntype { } 
}

## What is the difference between pure and impure pipe?

## Meaning	

* An pure pipe is called when a change in the value or the parameters passed to a pipe is detected by Angular.

* An impure pipe is called in case of every change detection cycle irrespective of any change in the value or parameter passed.
 

# Syntax
@Pipe({
name: ‘filterPipe’,
pure: true
})

export class FilterPipe {}
@Pipe({
name: ‘filterPipe’,
pure: false
})

export class FilterPipe

# Shareability
* Pure pipes can be shared across various usages and that too without having any effect on the output result.

* Impure Pipes cannot be shared because they might affect the internal state from outside

# Determination of Output change.
* Input values or parameters can determine the output value or the change in it.	

* Input values cannot determine the output value or the change in it.


## Explain how to use HttpClient with an example?

* Firstly, start by creating a HttpClient instance.
* Next, create an instance of one of the methods.
* Command HttpClient to execute the method.
* After the execution, read the response.
* Finally, release the connection.
* And deal with the response.

## How can you read the full response?
when we subscribe any Observable then we got full response like below example.
getUserResponse(): Observable<HttpResponse> {
  return this.http.get(
    this.userUrl, { observe: 'response' });
}

## How do you perform Error handling?
* by using try catch, and when we subscribe observable or promise then we have 
error parameter for handle a error.

* error handling can be done by writing a function using HttpClient along with catchError from RxJS.

* To handle errors, Angular’s HttpClient parses JSON responses and returns a JavaScript object in the observable.


## What is the difference between promise and observable?
** Observables	Promise **
# Values	
* Observables have the capacity to emit multiple values over a given period of time.	
* A promise emits only a single value over a given period of time.

# Execution
* They can be executed only when subscribed using subscribe() method.	* Promises can be executed as soon as they get created.

# Cancellation
* Observables are cancellable as they consist of subscriptions that can be cancelled using the unsubscribe() method.	
* Promises once executed are non cancellable.

# Operations
* Can provide operations like map for forEach, filter, reduce, retry, and retryWhen operators.
* Promises do not offer any operations.

# Errors	
* An observable pushes the errors to the subscribers.
* A promise pushes the errors to the child promises.

## What do you mean by data binding?
Data binding help in establishing communication between DOM and the component.
It makes the defining process for pushing or pulling data between the component and the template.

* Event binding (click)
* Property binding [data]
* String interpolation {{data}}
* Two-way data binding [ngModel]

## What are the differences between Angular decorator and annotation?
* Decorators,
are design patterns that help in the modification or decoration of the respective classes without making changes in the actual source code.

* Annotations,
are used in Angular to build an annotation array. They use the Reflective Metadata library and are a metadata set of the given class.

## What is an AOT compilation in Angular?
The AOT (ahead-of-time) compiler in Angular converts Angular HTML and TypeScript code into JavaScript code during the build phase, 
which makes the rendering process much faster. 

This compilation process is needed since Angular uses TypeScript and HTML code. The compiler converts the code into JavaScript, which can then be effectively used by the browser that runs our application.

## What are the three phases of AOT?
The three phases of AOT are:

* code analysis
* code generation
* template type checking

## What are dynamic components?
Dynamic Components in the Angular framework are the components that help in building large-scale applications easily. Dynamic components are usually instantiated and placed in the application at runtime.

## What is the purpose of base href tag?
The href attribute is used to specify the base URL for all relative URLs on a page.During navigation, the base href tag is used by the Angular router as a base path to the component, template, and module files

## What are services in Angular?
A service in Angular is a term that covers broad categories of functionalities. A service is any value, function, or feature that an app needs. 
A service is typically used to accomplish a very narrow purpose such as HTTP communication, sending data to a cloud service, decoding some text, validating data, etc. 
A service does one thing and does it well. It is different from a component as it is not concerned with HTML or any other kind of presentation logic. Normally, a component uses multiple services to accomplish multiple tasks.

## What is the difference between jQuery and Angular?
 jQuery is a JS library, whereas Angular is a JS frontend framework. 

* Unlike jQuery, Angular offers two-way data binding
* Unlike Angular, jQuery does not offer support for the RESTful API
* Angular supports deep linking routing, while jQuery does not
* Form validation is available in Angular but not in jQuery

## What are observables in Angular?
An observable is a declarative way using which we can perform asynchronous tasks.

 Observables can be thought of as streams of data flowing from a publisher to a subscriber. They are similar to promises as they both deal with handling asynchronous requests. However, observables are considered to be a better alternative to promises as the former comes with a lot of operators that allow developers to better deal with asynchronous requests, especially if there is more than one request at a time.

Observables are preferred by many developers as they allow them to perform multiple operations such as combining two observables, mapping an observable into another observable, and even piping multiple operations through an observable to manipulate its data.

## How are observables different from promises?
Although both promises and observables are used to handle asynchronous requests in JavaScript, they work in very different ways. Promises can only handle a single event at a time, while observables can handle a sequence of asynchronous events over a period of time. Observables also provide us with a wide variety of operators that allow us to transform data flowing through these observables with ease.

A promise is just a way to wrap asynchronous operations so that they can be easily used, while an observable is a way to turn asynchronous operations into a stream of data that flows from a publisher to a subscriber through a well-defined path with multiple operations transforming the data along the way

## What is meant by dependency injection in Angular?
* DI is wired into the Angular framework and allows classes with Angular decorators, such as Components, Directives, Pipes, and Injectables, to configure dependencies that they need.

* Angular uses the Dependency Injection design pattern, which makes it extremely efficient. This programming paradigm allows classes, components, and modules to be interdependent while maintaining consistency. This reduces the frequency with which the class changes.


##  Explain the MVVM architecture.
The MVVM architecture plays a significant role in eliminating tight coupling between the components. This architecture includes the following three parts:

* Model:
The model represents the business logic and data of a particular application. In other words, it consists of an entity structure. The model has the business logic, including model classes, remote and local data sources, and the repository.
* View: 
View is the application’s visual layer that comprises the UI code. The view sends the action of the user to the ViewModel. However, it does not receive the response directly. The view must subscribe to the observables that are exposed to it by the ViewModel to receive a response.
* ViewModel: 
ViewModel is the application’s abstract layer that connects the View and the Model and acts as a bridge between the two. It does not know which View needs to be made use of since it does not have any direct access to the View. The two are connected using data binding, and the ViewModel records all the changes that are made to the View and makes the necessary changes to the Model

## Describe Angular authentication and authorization.
The login details of a user are given to an authenticate API available on the server. Once the credentials are validated by the server, it returns a JSON web token (JWT), which includes attributes and the data of the current user. Further, the user is easily identified using JWT, and this process is known as authentication.

After logging in, users have various types and levels of access—some can access everything, while others may have restrictions from some resources. Authorization determines the access level of these users.

## Explain Angular CLI.
Angular CLI is otherwise known as Angular command-line interface. Angular supports CLI tools that give professionals the ability to use them to add components, deploy them instantly, and perform testing and many such functions.

## What is the purpose of the common module in Angular?
In Angular, the common module that is available in the package @angualr/common is a module that encapsulates all the commonly needed features of Angular, such as services, pipes, directives, etc. It contains some sub-modules as well such as the HttpClientModule, which is available in the @angular/common/http package. Because of the modular nature of Angular, its functionalities are stored in small self-contained modules, which can be imported and included in our projects if we need these functionalities.

## What is server-side rendering in Angular?
In a normal Angular application, the browser executes our application, and JavaScript handles all the user interactions. However, because of this, sometimes, if we have a large application with a big bundle size, our page’s load speed is slowed down quite a bit as it needs to download all the files, parse JavaScript, and then execute it. To overcome this slowness, we can use server-side rendering, which allows us to send a fully rendered page from the server that the browser can display and then let the JavaScript code take over any subsequent interactions from the user.

## How does one share data between components in Angular?
There is not one but various methods to share data between components in Angular. They are mentioned as below:

* Parent to Child: via Input
* Child to Parent: via Output() and EventEmitter
* Child to Parent: via ViewChild
* Unrelated Components: via a Service

## What is ng-content and its purpose?
The usage of ng-content in Angular is to insert the content dynamically inside the component. It helps in  increasing component reusability and passing content inside the component selector.

## What is ngcc?
The ngcc(Angular Compatibility Compiler) is a tool used in Angular to upgrade node_module, compiled with non-ivy ngc into ivy compliant format.