# Nativescript tests hook
Nativescript plugin that lets you handling your Nativescript tests like the angular style guide

Nativescript is configured by default to let you put all your tests into `tests` folder but sometimes it can be a little annoying, as apps grow in size and components, having unit-tests next to implementations makes easier maintaining these tests, when we do development for web version of angular application, we put the test files in respective feature folders with `.spec.ts` or `.spec.js` suffix as per the angular style guide.

### Example
~~~
app
|-- myFeature
     |- myFeature.component.html
     |- myFeature.component.ts
     |- myFeature.component.spec.ts
~~~

Just keep your `.spec.ts` or `.spec.js` files next to implementations and that's it. It moves all your tests from wherever they are into `app` to `tests` folder at tns' before-prepare hook time.

## Installation

### Npm

```bash
npm install nativescript-tests-hook --save-dev
```

## Configuration

The only thing you need to be aware of is when importing file dependencies in your tests you have to reference them as loading files from the app bundle according to [Nativescript's Location Rules Docs](https://docs.nativescript.org/runtimes/require#loading-files-from-the-app-bundle) to keep their references when they will move.

### Example

```typescript
import { MyFeatureComponent } from '~/myFeature/myFeature.component';
import { AppComponent } from '~/app.component';


```