# Angular2 bootstrap confirm
[![Build Status](https://travis-ci.org/mattlewis92/angular2-bootstrap-confirm.svg?branch=master)](https://travis-ci.org/mattlewis92/angular2-bootstrap-confirm)
[![npm version](https://badge.fury.io/js/angular2-bootstrap-confirm.svg)](http://badge.fury.io/js/angular2-bootstrap-confirm)
[![devDependency Status](https://david-dm.org/mattlewis92/angular2-bootstrap-confirm/dev-status.svg)](https://david-dm.org/mattlewis92/angular2-bootstrap-confirm#info=devDependencies)
[![GitHub issues](https://img.shields.io/github/issues/mattlewis92/angular2-bootstrap-confirm.svg)](https://github.com/mattlewis92/angular2-bootstrap-confirm/issues)
[![GitHub stars](https://img.shields.io/github/stars/mattlewis92/angular2-bootstrap-confirm.svg)](https://github.com/mattlewis92/angular2-bootstrap-confirm/stargazers)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/mattlewis92/angular2-bootstrap-confirm/master/LICENSE)

## Demo
https://mattlewis92.github.io/angular2-bootstrap-confirm/

## Table of contents

- [About](#about)
- [Installation](#installation)
- [Documentation](#documentation)
- [Development](#development)
- [License](#licence)

## About

A simple angular2 directive to display a bootstrap styled confirmation popover when an element is clicked.

Pull requests are welcome.

[AngularJS 1.x version](https://github.com/mattlewis92/angular-bootstrap-confirm)

## Installation

Install through npm:
```
npm install --save angular2-bootstrap-confirm
```

Then use it in your app on a component:

```typescript
import {NgModule, Component} from '@angular/core';
import {ConfirmationPopoverModule} from 'angular2-bootstrap-confirm';

// first add it to your apps module
@NgModule({
  declarations: [MyComponent],
  imports: [
    ConfirmationPopoverModule.forRoot({
      confirmButtonType: 'danger' // set defaults here
    })
  ],
  bootstrap: [MyComponent]
})
class MyModule {}

// now use it within your component
@Component({
  selector: 'my-component',
  template: `
    <button
      class="btn btn-default"
      mwlConfirmationPopover
      [title]="title"
      [message]="message"
      placement="left"
      (confirm)="confirmClicked = true"
      (cancel)="cancelClicked = true"
      [(isOpen)]="isOpen">
      Click me!
    </button>
  `
})
class MyComponent {
  public title: string = 'Popover title';
  public message: string = 'Popover description';
  public confirmClicked: boolean = false;
  public cancelClicked: boolean = false;
  public isOpen: boolean = false;
}

```

You may also find it useful to view the [demo source](https://github.com/mattlewis92/angular2-bootstrap-confirm/blob/master/demo/demo.ts).

### Usage without a module bundler
```
<script src="node_modules/angular2-bootstrap-confirm/dist/umd/angular2-bootstrap-confirm.js"></script>
<script>
    // everything is available under the ng2BootstrapConfirm namespace
</script>
```

### Usage with universal

You will need to add this line in your server bootstrap code to get this module to work with universal:
```
(global as any).HTMLElement = () => {};
```

## Documentation
All documentation is auto-generated from the source via typedoc and can be viewed here:
https://mattlewis92.github.io/angular2-bootstrap-confirm/docs/

The main confirm directive options can be viewed [here](https://mattlewis92.github.io/angular2-bootstrap-confirm/docs/classes/confirm.html).

## Development

### Prepare your environment
* Install [Node.js](http://nodejs.org/) and NPM (should come with)
* Install local dev dependencies: `npm install` while current directory is this repo

### Development server
Run `npm start` to start a development server on port 8000 with auto reload + tests.

### Testing
Run `npm test` to run tests once or `npm run test:watch` to continually run tests.

### Release
```bash
npm run release
```

## License

MIT
