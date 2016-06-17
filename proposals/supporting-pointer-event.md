# JavaScript: supporting Pointer event

## Why Pointer Events?
>Mouse events and touch events are fundamentally different beasts in browsers today, and that makes it hard to write cross-platform apps.
>
>For example, a simple finger paint app needs plenty of work to behave correctly with mouse and touch:
>Current platforms that implement touch events also provide mouse events for backward compatibility; however, only a subset of mouse events are fired and the semantics are changed.
> 
> - Mouse events are only fired after the touch sequence ends.
> - Mouse events are not fired on elements without a `click` event handler. One must be attached by default, or directly on the element with `onclick`.
> - `click` events are not fired if the content of the page changes in a `mousemove` or `mouseover` event.
> - `click` events are fired 300ms after the touch sequence ends.
> - More information: [Apple Developer Documentation](http://developer.apple.com/library/safari/#documentation/appleapplications/reference/safariwebcontent/HandlingEvents/HandlingEvents.html).
> 
> Additionally, touch events are sent only to the element that received the `touchstart`. This is fundamentally different than mouse events, which fire on the element that is under the mouse. To make them behave similarly, touch events need to be retargeted with `document.elementFromPoint`.
> 
> These incompatibilities lead to applications having to listen to 2 sets of events, mouse on desktop and touch for mobile.
> 
> **This forked interaction experience is cumbersome and hard to maintain.**
> 
> Instead, there should exist a set of events that are normalized such that they behave exactly the same, no matter the source: touch, mouse, stylus, skull implant, etc. To do this right, this normalized event system needs to be available for all the web platform to use.
>
>
> * Ctrl+S / Cmd+S to save the file
> * Ctrl+Shift+S / Cmd+Shift+S to choose to save as Markdown or HTML
> * Drag and drop a file into here to load it
> * File contents are saved in the URL so you can share files
>
> *Thus, Pointer Events!*

-- [jQuery PEP](https://github.com/jquery/PEP#why-pointer-events)

### References
- [jQuery PEP](https://github.com/jquery/PEP)
- [jQuery blog, "Getting on Point"](https://blog.jquery.com/2015/02/24/getting-on-point/)
- [W3C Pointer Events Specification](https://www.w3.org/TR/pointerevents/)
- [MSDN, Pointer Events](https://msdn.microsoft.com/en-us/library/dn433244%28v=vs.85%29.aspx)
- [MDN, Pointer Events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events)

## Suggested Solution
At the time of writing this proposal, I have not tried any third-party solution, but I simply attach the `pointer[event name]` to the element using the jQuery `.on()` method. Using that technique takes us into another challenge, which is getting the cursor's coordinates, when that event is fired the properties `pageX` and `pageY` of the jQuery event object will be `undefined`, so that we use like [this algorithms](https://github.com/zurb/foundation-sites/blob/v5.5.3/js/foundation/foundation.slider.js#L101) to get the cursor's coordinates.

However, I would suggest that [jQuery PEP](https://github.com/jquery/PEP) rather than writting our custom code, if it will handle all the relevant issues.