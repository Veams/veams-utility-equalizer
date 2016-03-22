# Equalizer

This blueprint is based on the blueprint of Veams-Components.

This utility equals the heights of its child elements.

###  Important Notes

For the implentation you need to make sure that you have the following attributes
 
 1. on the wrapper element:
  * `data-js-module="equalizer"`
 2. on all childs (which should be equalized): 
  * `data-js-atom="equalizer-child"`
 
These attributes can be applied anywhere in your HTML you like. The equalizer should work on every grid element. 

### Modifiers (only necessary when you use the provided markup)

For demo purpose there are some layout styles integrated.

 - `is-grid-3` - For 3 columns
 - `is-grid-2`- For 2 columns

## Usage

### Include: Page

``` hbs
{{! @INSERT :: START @id: equalizer, @tag: component-partial }}
{{#wrapWith "u-equalizer" columns=3}}
    {{#wrapWith "u-equalizer__child"}}
        <div style="background-color: black; color: #fff; padding: 20px; display: block; height: 100%">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab accusamus accusantium aperiam cupiditate error excepturi ipsa libero magni maiores molestiae, nostrum optio placeat repudiandae sed sit velit voluptatum. Labore, recusandae.</p>
        </div>
    {{/wrapWith}}
    {{#wrapWith "u-equalizer__child"}}
        <div style="background-color: black; color: #fff; padding: 20px; display: block; height: 100%">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab accusamus accusantium aperiam cupiditate error excepturi ipsa libero magni maiores molestiae, nostrum optio placeat repudiandae sed sit velit voluptatum. Labore, recusandae.</p>

            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab accusamus accusantium aperiam cupiditate error excepturi ipsa libero magni maiores molestiae, nostrum optio placeat repudiandae sed sit velit voluptatum. Labore, recusandae.</p>
        </div>
    {{/wrapWith}}
    {{#wrapWith "u-equalizer__child"}}
        <div style="background-color: black; color: #fff; padding: 20px; display: block; height: 100%">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
        </div>
    {{/wrapWith}}

{{/wrapWith}}
{{! @INSERT :: END }}
```

### Include: JavaScript

#### Import
``` js
// @INSERT :: START @tag: js-import 
import Equalizer from './modules/equalizer/equalizer';
// @INSERT :: END
```

#### Initializing in Veams V2
``` js
// @INSERT :: START @tag: js-init-v2 
/**
 * Init Equal Rows
 */
Helpers.loadModule({
	el: '[data-js-module="equalizer"]',
	module: Equalizer,
	render: false,
	cb: function (module, options) {
        if (options && options.delayInit) {
            $(window).load(function () {
                module._reinit(module);
            });
        }
    },
	context: context
});
// @INSERT :: END
```

#### Initializing in Veams V3
``` js
// @INSERT :: START @tag: js-init-v3  
/**
 * Init Call-To-Action
 */
Helpers.loadModule({
	domName: 'equalizer',
	module: Equalizer,
	render: false,
	cb: function (module, options) {
        if (options && options.delayInit) {
            $(window).load(function () {
                module._reinit(module);
            });
        }
    },
	context: context
});
// @INSERT :: END
```
