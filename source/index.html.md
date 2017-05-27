---
title: API Reference

language_tabs:
  - url

toc_footers:
  - <a href='https://www.traffiqa.com'>Request an invitation on our homepage</a>

includes:
  - errors

search: true
---

# Traffiqa Documentation

Traffiqa is an optimization service that will help you make your service run much faster. In this documentation we will try our best to help you to get to know and use the Traffiqa service. 

If you have any question, the best way to reach us is by using the online chat. Just click on the small rectangle on the right bottom corner. You can also reach us @traffiqa on twitter and also on [support@traffiqa.com](mailto:support@traffiqa.com)

# Images

## From Website Origin

> To get a file from your account, call this end point:

```url
GET http://s.traffiqa.com/{accountId}/origin/{filePath}
```

> Make sure to replace `{accountId}` with your account ID and `{filePath}` with your file path.

You don't need to upload your files to Traffiqa in order to start using the service. you just need to tell Traffiqa where your current files are.

After you've [setup your account](https://app.traffiqa.com/settings) origin, you can access any file from your origin

<aside class="notice">
You must replace <code>{accountId}</code> with your account Id
and <code>{filePath}</code> with the file path on your origin server.
</aside>

## Origin Example

```url
GET http://s.traffiqa.com/demo/origin/images/my-awsome-logo.png
```

> Traffiqa will go yo your service origin, grab the file, optimize it, save it and sent it back to the browser

For example, let's assume you have these settings:

`Website Origin: http://www.my-awsome-service.com`

`File Path On Origin: http://www.my-awsome-service.com/images/my-awsome-logo.png`

`{accountId}: demo`

`{filePath}: /images/my-awsome-logo.png`

### Processes Summary

Process | Default | Description
--------- | ------- | -----------
optimize | true | Optimize image with same file type.
format | auto | Change image file format to a different format.
width | -- | No default. Change image width to a different one. Value are in pixels
height | -- | No default. Change image height to a different one. Value are in pixels


## Processes

### optimize

Use the `optimize` process when you want to shrink down the current image and keeping it with the same file format.

* Type: `Boolean`
* Default Value: `true`
* Example values: `optimize=false`, `o=true`
* Alias `o`

### format

Use the `format` process to enforce a certain file format, to keep original file format or specify `auto` to change file format according to user browser type.

* Type: `String`
* Default Value: `auto`
* Example values: `format=auto`, `f=auto`, `f=png`, `f=jpg`, `f=webp`
* Alias `f`

### width

Use the `width` process to change the image width, if `height` is not specified - the original `height` will change with the same proportion.
Values are in pixels.

* Type: `Integer`
* Example values: `width=500`, `w=500`, `w=250`
* Alias `w`

### height

Use the `height` process to change the image width, if `width` is not specified - the original `width` will change with the same proportion.
Values are in pixels.

* Type: `Integer`
* Example values: `height=500`, `h=500`, `h=250`
* Alias `h`

## Default Processes Values

```url
GET http://s.traffiqa.com/demo/origin/images/my-awsome-logo.png
```

> Is the same as:

```url
GET http://s.traffiqa.com/demo/origin/images/my-awsome-logo.png?format=auto&optimize=true
```

> To turn off optimization and auto file format, use:

```url
GET http://s.traffiqa.com/demo/origin/images/my-awsome-logo.png?format=original&optimize=false
```

If you will try to fetch an image from your origin you will see that it will be optimized without you specifying anything.

Traffiqa is optimized by default and you need to explicitly say that you don't want a file to be optimized


# Javascript

## Origin Example

```url
GET http://s.traffiqa.com/demo/origin/js/main.js
```

> Traffiqa will go yo your service origin, grab the Javascript file, minify it, remove unnecessary comments and sent it back to the browser

For example, let's assume you have these settings:

`Website Origin: http://www.my-awsome-service.com`

`{accountId}: demo`

`{filePath}: /js/main.js`

### Processes Summary

Process | Default | Description
--------- | ------- | -----------
minify | true | Minify your Javascript file and remove unnecessary comments.


## Processes

### minify

Use the `minify` process when you want to minify the current Javascript.

* Type: `Boolean`
* Default Value: `true`
* Example values: `minify=false`, `minify=true`

## Default Processes Values

```url
GET http://s.traffiqa.com/demo/origin/js/main.js
```

> Is the same as:

```url
GET http://s.traffiqa.com/demo/origin/js/main.js?minify=true
```

> To turn off minification and auto file format, use:

```url
GET http://s.traffiqa.com/demo/origin/js/main.js?minify=false
```

If you will try to fetch a Javascript file from your origin you will see that it will be minified without you specifying anything.

Traffiqa is minifying by default and you need to explicitly say that you don't want a file to be minified.

# CSS

## Origin Example

```url
GET http://s.traffiqa.com/demo/origin/css/main.css
```

> Traffiqa will go to your service origin, grab the CSS file, minify it, remove unnecessary comments and sent it back to the browser

For example, let's assume you have these settings:

`Website Origin: http://www.my-awsome-service.com`

`{accountId}: demo`

`{filePath}: /css/main.css`

### Processes Summary

Process | Default | Description
--------- | ------- | -----------
minify | true | Minify your CSS file and remove unnecessary comments.


## Processes

### minify

Use the `minify` process when you want to minify the current CSS file.

* Type: `Boolean`
* Default Value: `true`
* Example values: `minify=false`, `minify=true`

## Default Processes Values

```url
GET http://s.traffiqa.com/demo/origin/css/main.css
```

> Is the same as:

```url
GET http://s.traffiqa.com/demo/origin/css/main.css?minify=true
```

> To turn off minification and auto file format, use:

```url
GET http://s.traffiqa.com/demo/origin/css/main.css?minify=false
```

If you will try to fetch a CSS file from your origin you will see that it will be minified without you specifying anything.

Traffiqa is minifying by default and you need to explicitly say that you don't want a file to be minified.

# HTML

## Origin Example

```url
GET http://s.traffiqa.com/demo/some.html
```

> Traffiqa will go to your service origin, grab the HTML file, minify it, remove unnecessary comments and sent it back to the browser

For example, let's assume you have these settings:

`Website Origin: http://www.my-awsome-service.com`

`{accountId}: demo`

`{filePath}: /some.html`

### Processes Summary

Process | Default | Description
--------- | ------- | -----------
minify | true | Minify your HTML file and remove unnecessary comments.


## Processes

### minify

Use the `minify` process when you want to minify the current HTML file.

* Type: `Boolean`
* Default Value: `true`
* Example values: `minify=false`, `minify=true`

## Default Processes Values

```url
GET http://s.traffiqa.com/demo/origin/some.html
```

> Is the same as:

```url
GET http://s.traffiqa.com/demo/origin/some.html?minify=true
```

> To turn off minification and auto file format, use:

```url
GET http://s.traffiqa.com/demo/origin/some.html?minify=false
```

If you will try to fetch a HTML file from your origin you will see that it will be minified without you specifying anything.

Traffiqa is minifying by default and you need to explicitly say that you don't want a file to be minified.

