# Foundation 7: JavaScript plugin initialization

## Introduction
Foundation JavaScript architecture is really a piece of beauty, and you can easily proof that by opening the `foundation.core.js` then you will clearly notice these arguments:
-	Wrapping the whole stuff in a namespace
-	Registering and Unregistering the plugins
-	Smart initializing technique
-	Storing the initialized plugins
-	And more...

One more thing, Foundation JavaScript plugins are not defined directly to jQuery, but they are completely live in that isolated namespace which is called Foundation, that kind of isolation gives Foundation the power to manage those plugins and keep them away from jQuery’s plugins and other worlds!

I am not going to describe the other strengths of the Foundation JavaScript architecture, but I would only like to make you notice that Foundation really has the principles of the Scalable Architecture.

## Foundation JavaScript plugin initialization
Foundation is smart enough to recognize the elements that should be initialized, it looks for any element that has the data attribute, for example: data-dropdown, and once Foundation finds that plugin name in the registered plugins list, it will initialize that element. Additionally, Foundation will collect and merge the plugin’s options from three resources: plugin’s default options, the value of `data-options`, and the individual data attributes.

However, what about if Foundation is used with any other non-Foundation JavaScript plugin or framework? I am sure mixing UI frameworks is not recommended, but as you know there are many other front-end frameworks that don’t target the UI but the data binding, so let’s assume this scenario:

You have a non-Foundation JavaScript plugin that requires this data attribute `data-what-ever`, while you also have a Foundation JavaScript plugin that assume `data-what-ever` is a plugin name or an option name. That is a very simple example of the expected conflicts, and regardless that conflicts, Foundation is assumed to be used even partially, that means you can only use one plugin from Foundation in your application and that implicitly means you will use another bunch of other JavaScript code, so in this case Foundation must not assume that all data attributes are reserved for it!

## Solution
I would suggest these two steps to solve that:
-	Adding a namespace to the data attribute of the plugin name and the plugin’s options, so the data attributes should look like: `data-zf-plugin-name` and `data-zf-options`.
-	Removing the previous data individual options, and keep all the passed options in `data-zf-options`.

I think that will help Foundation to be easily mixed with any other JavaScript plugins and avoiding any expected naming conflicts, and the most important is to free the data attribute to be used from others.