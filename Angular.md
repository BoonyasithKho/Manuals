## Prerequisites
  - Javascript
  - HTML
  - CSS
  - Node.js
  - npm package manager
## Install Angular CLI
    npm install -g @angular/cli
## Create a workspace and initial application
### Create Project
    ng new 'my-app'
### Access Folder
    cd my-app
### Open Serve
    ng serve --open
## Command in Angular
### Generate Component
    ng generate component 'component-name'
   - Results in component-name folder :
      - 'component-name'.component.css      >> .css/.scss depend on project creation
      - 'component-name'.component.html     >> edit HTML tag
      - 'component-name'.component.spec.ts  >> use for test component
      - 'component-name'.component.ts       >> typescript for operation
### Generate Service
    ng generate service 'service-name'
   - Results :
      - 'service-name'.service.ts
