# ClickLoad
A Bootstrap enhancement to make buttons that cause AJAX to be prettier.

##How to use
To use ClickLoad, include it on your page and attach it to a button. It takes the place of the jQuery click handler and handles all of Bootstrap's contextual classes for you depending on the result of the AJAX request it makes.

Say you have a button with the ID `testbutton`. To enable ClickLoad on that button, simply:

    $("#testbutton").clickLoad(options);
  
`options` is an object containing the following options:
* `during:"String"` - Required. What the button should say during the AJAX request.
* `after:"String"` - Required. What the button should say on success.
* `url:"String"` - Required. The endpoint you're contacting.
* `method:"String"` - Optional, defaults to `"GET"`. Any HTTP Method jQuery will support.
* `data:{object}"` - Optional, defaults to `{}`. What data to post in the AJAX call.
* `success:boolean function(data,textStatus,jqXHR)` - Optional. A function that's called on AJAX success with the same variables as `$.ajax`'s success function. The difference is that ClickLoad cares about the return value. If you return false, the transaction will be treated as an error and your error function will be called if it exists. If nothing is returned, a success is assumed.
* `error:string function(jqXHR, textStatus, errorThrown, data)` - Optional. A function that's called on AJAX failure of if your success function determines that the response it got was, in fact, an error. If AJAX calls this function, `data` will be undefined. If it's called as a result of your success function, `errorThrown` is undefined and `data` will have the data retrieved from the AJAX call. In either case, the string returned from this function is shown on the button. If you don't return anytthing, "Error!" is shown instead.
* `headers:{Object}` = Optional. Passed directly to the AJAX call.
* `disable:boolean` - Optional, defaults to `true`. If true, the button will be disabled while the AJAX request is in flight. If false, it won't be disabled.
* `animate:boolean` - Optional, defaults to `true`. If true, the button will take the appearance of the active stripped progress bar. If false, this won't happen.

##Credits
Credit either Tucker Osman or Osmium USA and please link back to this repository.
