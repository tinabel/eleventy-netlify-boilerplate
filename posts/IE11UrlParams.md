---
title: Getting URL parameters in IE11
summary: IE11 is a groanfest for most developers in terms of what is and isn't supported. Among the things that isn't supported is the URL api. It makes things less than ideal when you have to split a url's parameters out and fetch a specific parameter....
date: 2019-01-24
tags:
    - post
    - JavaScript
    - IE11
featured: true
---

IE11 is a groanfest for most developers in terms of what is and isn't supported. Among the things that isn't supported is the [URL api](https://developer.mozilla.org/en-US/docs/Web/API/URL). It makes things less than ideal when you have to split a url's parameters out and fetch a specific parameter.

I recently ran into this on a project: everything worked fine in WebKit and Mozilla, but IE threw exceptions, because we were using the URL api. I didn't know what to do!

Enter Stack Overflow. Several answers were given, but i needed one that I could pass the url to and get back specified parameters, so I took an answer and altered it to my needs. Here it is:

```
$.urlParam = function (location, name) {
    var results = new RegExp('[\?&]' + name + '=([^&#]*)')
        .exec(location);
    if (results == null) {
        return 0;
    }
    return results[1] || 0;
}
```

This function takes the specified url, does a regular expression search for the specified parameter, and returns the value. Easy as pie.

Remember, kids: drink your milk and always test your JavaScript in every browser you support. You don't want to be surprised when something like this comes back to bite you. 