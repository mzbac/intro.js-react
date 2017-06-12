# intro.js-react

A small React wrapper around [Intro.js](http://introjs.com/). The wrapper provides support for both steps and hints.

## Installation

The wrapper is not yet published on npm. At the moment, you can fork this repository to use it.

Make sure to have [React](https://facebook.github.io/react/) & [Intro.js](http://introjs.com/) installed (they're peer dependencies) and the Intro.js CSS definitions [properly loaded](http://introjs.com/docs/getting-started/install) into your project.

This would usually looks like:

```js
import 'intro.js/introjs.css';
```

## Usage

Two component are available for both steps and hints:

```js
import { Steps, Hints } from 'intro.js-react';
```

## Steps

**Note: Steps indexes always starts from 0 in this wrapper instead of 1 like in Intro.js.**

### Basic example:

```js
<Steps
  enabled={stepsEnabled}
  steps={steps}
  initialStep={initialStep}
  onExit={this.onExit}
/>
```

### Props

| Name | Description | Type | Required |
| --- | --- | :---: | :---: |
| `enabled` | Defines if the steps are visible or not. <br> *Default: false.* | Boolean |  |
| `initialStep` | Step index to start with when showing the steps. | Number | ✅ |
| `steps` | All the steps. | [Step[]](https://github.com/HiDeoo/intro.js-react#step) | ✅ |
| `onExit` | Callback called when the steps are disabled <br> *Required to force keeping track of the state when the steps are dismissed with an Intro.js event and not the `enabled` prop.* | Function <br> *(stepIndex)* | ✅ |
| `onStart` | Callback called when the steps are enabled. | Function <br> *(stepIndex)* |  |
| `onChange` | Callback called when the current step is changed. | Function <br> *(nextStepIndex, nextElement)*  |  |
| `onBeforeChange` | Callback called before changing the current step. | Function <br> *(nextStepIndex, nextElement)* |  |
| `onAfterChange` | Callback called after changing the current step. | Function <br> *(newStepIndex, newElement)* |  |
| `options` | Intro.js options. | [Object](https://github.com/HiDeoo/intro.js-react#introjs-options) | | |

### Step

```js
const steps = [
  {
    element: '.selector1',
    intro: 'test 1',
    position: 'right',
    tooltipClass: 'myTooltipClass',
    highlightClass: 'myHighlightClass',
  },
  {
    element: '.selector2',
    intro: 'test 2',
  },
  {
    element: '.selector3',
    intro: 'test 3',
  },
];
```

| Name | Description | Type | Required |
| --- | --- | :---: | :---: |
| `element` | CSS selector to use for the step. | String | ✅ |
| `intro` | The tooltip text. | String | ✅ |
| `position` | Position of the tooltip. | String | |
| `tooltipClass` | CSS class of the tooltip. | String | |
| `highlightClass` | CSS class of the helperLayer. | String |  |  |

## Hints

### Basic example:

```js
<Hints
  enabled={hintsEnabled}
  steps={hints}
/>
```

### Props

| Name | Description | Type | Required |
| --- | --- | :---: | :---: |
| `enabled` | Defines if the hints are visible or not. <br> *Default: false.* | Boolean |  |
| `hints` | All the hints. | [Hint[]](https://github.com/HiDeoo/intro.js-react#hint) | ✅ |
| `onClick` | Callback called when a hint is clicked. | Function <br> *( )* |  |
| `onClose` | Callback called when a hint is closed. | Function <br> *( )*  |  |
| `options` | Intro.js options. | [Object](https://github.com/HiDeoo/intro.js-react#introjs-options) | | |

### Hint

```js
const hints = [
  {
    element: '.selector1',
    hint: 'test 1',
    hintPosition: 'middle-middle',
  },
  {
    element: '.selector2',
    hint: 'test 2',
  },
];
```

| Name | Description | Type | Required |
| --- | --- | :---: | :---: |
| `element` | CSS selector to use for the hint. | String | ✅ |
| `hint` | The tooltip text. | String | ✅ |
| `hintPosition` | Position of the tooltip. | String | | |

## Intro.js options

You can find more details regarding Intro.js options and their default values in [the documentation](http://introjs.com/docs/) or directly in [their code](https://github.com/usablica/intro.js/blob/master/intro.js#L32).

You can also adjust default options for both components in the `helpers/defaultProps.js` file.

| Name | Description | Type |
| --- | --- | :---: |
| `nextLabel` | Next button label. | String |
| `prevLabel` | Previous button label. | String |
| `skipLabel` | Skip button label. | String |
| `doneLabel` | Done button label. | String |
| `hidePrev` | Hides the Previous button in the first step. | Boolean |
| `hideNextl` | Hide the Next button in the last step. | Boolean |
| `tooltipPosition` | Position of the tooltips. | String |
| `tooltipClass` | CSS class of the tooltips. | String |
| `highlightClass` | CSS class of the helperLayer. | String |
| `exitOnEsc` | Exit by pressing Escape. | Boolean |
| `exitOnOverlayClick` | Exit by clicking on the overlay layer. | Boolean |
| `showStepNumbers` | Show steps number in a red circle. | Boolean |
| `keyboardNavigation` | Allows navigation between steps using the keyboard. | Boolean |
| `showButtons` | Show navigation buttons. | Boolean |
| `showBullets` | Show bullets. | Boolean |
| `showProgress` | Show progress indicator. | Boolean |
| `scrollToElement` | Enables scrolling to hidden elements. | Boolean |
| `overlayOpacity` | Opacity of the overlay. | Number |
| `scrollPadding` | Padding when automatically scrolling to an element. | Number |
| `positionPrecedence` | Precedence of positions. | String[] |
| `disableInteraction` | Disables interaction inside elements. | Boolean |
| `hintPosition` | Position of the hints. | String |
| `hintButtonLabel` | Hint button label. | String |
| `hintAnimation` | Enables hint animations. | Boolean |

## License

Licensed under the MIT License, Copyright © HiDeoo.

See [LICENSE](./LICENSE) for more information.