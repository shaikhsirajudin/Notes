Installation
```
npm install -g @angular/cli
```
Usage
```
ng help
```
Generating and serving
```
ng new PROJECT-NAME
cd PROJECT-NAME
ng serve

ng serve --host 0.0.0.0 --port 4201
```
Generating Components, Directives, Pipes and Services
```
ng generate component my-new-component
ng g component my-new-component # using the alias

# components support relative path generation
# if in the directory src/app/feature/ and you run
ng g component new-cmp
# your component will be generated in src/app/feature/new-cmp
# but if you were to run
ng g component ../newer-cmp
# your component will be generated in src/app/newer-cmp
# if in the directory src/app you can also run
ng g component feature/new-cmp
# and your component will be generated in src/app/feature/new-cmp

> Component 
 ng g component my-new-component  
> Directive  
ng g directive my-new-directive  
> Pipe  
ng g pipe my-new-pipe  
> Service  
ng g service my-new-service  
> Class  
ng g class my-new-class  
> Guard  
ng g guard my-new-guard  
> Interface  
ng g interface my-new-interface  
> Enum  
ng g enum my-new-enum  
Module  
ng g module my-module  



```

#  npm link  is very similar to  npm install -g 

•It creates a folder src/app/nav/ containing these 4 files:
```
nav.component.ts      - The component class + definition 
nav.component.css     - The component stylesheet
nav.component.html    - The component template
nav.component.spec.ts - The component test spec class
```