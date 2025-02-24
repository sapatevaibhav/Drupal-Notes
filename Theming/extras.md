## Adding favicon
1. Move your favicon.ico file to the themes root directory
2. In themes info.yml file add `favicon: 'favicon.ico'`
3. Inside your themes **html.html.twig** file add below lines
```html
    <link rel="icon" href="{{ base_path }}themes/custom/simplecollege/favicon.ico" type="image/x-icon">
```


## Tailwind setup

There are two ways to do so in libraries file

 ```yml
tailwind:
  js:
    https://cdn.tailwindcss.com/3.4.1: { type: external, minified: true }
```

and then load it in the **info.yml**
```yml
libraries:
  - simplecollege/tailwind
```
