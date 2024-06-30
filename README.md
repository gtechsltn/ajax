# jQuery Ajax call ASP.NET Core 5.0 Web API
+ JavaScript POST FormData
+ jQuery Ajax call ASP.NET Core 5.0 Web API
+ Input type file
+ Excel upload file
+ OpenXML
+ DTO

https://medium.com/coding-design/writing-better-ajax-8ee4a7fb95f

https://www.sitepoint.com/use-jquerys-ajax-function/

https://www.digitalocean.com/community/tutorials/submitting-ajax-forms-with-jquery

# jQuery Ajax Setup
```
$.ajaxPrefilter(function(opt, origOpt, jqxhr) {
    jqxhr.always(function() {
        $("[data-plugin]").plugin();
    });
});
```

# jQuery Ajax
```
$.ajax({
    data: someData,
    dataType: 'json',
    url: '/path/to/script',
    success: function(data, textStatus, jqXHR) {
        // When AJAX call is successfuly
        console.log('AJAX call successful.');
        console.log(data);
    },
    error: function(jqXHR, textStatus, errorThrown) {
        // When AJAX call has failed
        console.log('AJAX call failed.');
        console.log(textStatus + ': ' + errorThrown);
    },
    complete: function() {
        // When AJAX call is complete, will fire upon success or when error is thrown
        console.log('AJAX call completed');
    };
});
```

# jQuery Ajax Promise

**Promises and deferred objects**
```
.done() as a replacement for .success()
.fail() as a replacement for .error()
.always() as a replacement of .complete()
```

```
$.ajax({
    data: someData,
    dataType: 'json',
    url: '/path/to/script'
}).done(function(data) {
    // If successful
   console.log(data);
}).fail(function(jqXHR, textStatus, errorThrown) {
    // If fail
    console.log(textStatus + ': ' + errorThrown);
});
```

# Multiple AJAX calls
```
var a1 = $.ajax({...}),
    a2 = $.ajax({...});

$.when(a1, a2).done(function(r1, r2) {
    // Each returned resolve has the following structure:
    // [data, textStatus, jqXHR]
    // e.g. To access returned data, access the array at index 0
    console.log(r1[0]);
    console.log(r2[0]);
});
```
