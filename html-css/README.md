# HTML
## index.html
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <title></title>
        <meta name="description" content="">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="">
    </head>
    <body>
        <!--[if lt IE 7]>
            <p class="browsehappy">You are using an <strong>outdated</strong> browser. Please <a href="#">upgrade your browser</a> to improve your experience.</p>
        <![endif]-->
        
        <script src="" async defer></script>
    </body>
</html>
```
# CSS
## style.css
```css
* {
    box-sizing: border-box;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
}
.navbar {
  position: sticky;
  margin: -10px;
  top: 0;
  z-index: 2;
}
.btn:hover {
    transition-duration: 0.3s;
    background-color: red;
    transform: translateY(-5px);
}
.game-board {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.game {
    display: grid;
    grid-gap: 1px;
    grid-template-columns: repeat(3, 1fr);
}
.container {
    display: grid;
    grid-template-columns: auto auto;
    text-align: center;
}
```
