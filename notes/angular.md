# Angular

## Summary

### Angular CLI Commands

#### Create a new project
| Syntax      | Description |
| :----------- | :----------- |
| ng new app-name      | Generates all the files needed for an angular app to run properly.       |

<br/>

Options:
- --dry-run => Shows all the files that can potentially be generated.
- --prefix braga => Create your project with a custom prefix. For example, normally your project at components level has the selector with the alias app-component-name, right? So, with this CLI command your selector will be braga-component-name.
- --routing --style scss => Adds the routing file to your project and puts the CSS files in SASS type.

<br/>

#### Build and Run
| Syntax      | Description |
| :----------- | :----------- |
| ng serve      | Builds your entire project.       |
| ng serve -o | Builds your entire project. |
| ng serve -p 666 -o | Builds your entire project and automatically opens the browser with the url pointing to port 666. This is useful if for example we need to run two angular projects simultaneously. |
| ng serve --help | Gives you more information about ng serve. |

<br/>

#### Tslint
| Syntax      | Description |
| :----------- | :----------- |
| ng lint | Runs the tslint file in your project and validates if all the code respects the rules. |
| ng lint --format stylish | The same as ng lint but formats the output in a more tidier way. |
| ng lint --fix | The same as ng lint but it also tries to fix any errors. |
| ng lint --help | Gives you more information about ng lint. |

<br/>

#### Create Components/Services/Models/Pipes

| Syntax      | Description |
| :----------- | :----------- |
| ng generate component customer | Generates the “customer” component and creates a folder with the name “customer”.
| ng g c customer | The same as ng generate component customer but using an alias.
| ng g c customer --flat | Generates the customer component without the folder.
| ng g s sales-data | Generates the service “sales data”.
| ng g cl models/customer | Generates the customer class inside of the models folder ( if the folder models doesn’t exist the CLI will create it).
| ng g i models/person | The same as ng g cl models/customer but for creating an interface.
| ng g e models/gender | The same as ng g cl models/customer but for creating an enumerator.
| ng g p shared/init-caps | Generates the pipe “init-caps” inside of the shared folder.
| ng g d search-box | Generates the “search box” directive.

<br/>

#### Downgrade/Upgrade CLI

```
npm uninstall -g @angular/cli
npm cache clean
npm install -g @angular/cli@{latest or wanted version}
```

<br/>

## Testing

[Add how to test different things]

<br/>

## Best Practices

## Useful links

- [Angular Questions](https://medium.com/javascript-in-plain-english/tricky-interview-questions-in-angular-2020-part-3-659c0bc81a9d)
