### Bootstrap

#### Supported browsers

|	        | Chrome	| Firefox	| Safari	| Android Browser & WebView	| Microsoft Edge
|-----------|-----------|-----------|-----------|---------------------------|---------------
|Android	| Supported	| Supported	| N/A	    | Android v5.0+ supported	| Supported
|iOS	    | Supported	| Supported	| Supported	| N/A	                    | Supported     

|	      | Chrome	  | Firefox	  | Internet Explorer | Microsoft Edge | Opera	   | Safari
|---------|-----------|-----------|-------------------|----------------|-----------|-------
| Mac	  | Supported |	Supported |	N/A	              | N/A            | Supported | Supported
| Windows |	Supported |	Supported |	IE10+	          | Supported      | Supported | Not supported

#### Starter template

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <link rel="stylesheet" 
        href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" 
        integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" 
        crossorigin="anonymous">
    <link rel="stylesheet"
        href="css/style.css"> 

    <title>Hello, world!</title>
  </head>
  <body>
    <header>
        <nav class="navbar">
            <div class="containter-fluid">
                <img src="img/logo.png" alt="logo">
            </div>
        </nav>
    </header>
    <div class="container-fluid">
        <div class="row">
            <aside class="col-sm-2">
                <p>Morbi rutrum magna.</p>
                <p>Nunc sed metus.</p>
                <p>Fusce efficitur.</p>
            </aside>
            <div id="content" class="col-sm-10">
                <article>
                    <h1>Article title</h1>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
                       Vestibulum nec leo eu odio dignissim semper. Ut
                       porta non ipsum ut suscipit. In dapibus nisl eget quam 
                       lacinia varius. Ut imperdiet tristique diam a
                       ultrices. In hac habitasse platea dictumst. Nullam tempor 
                       condimentum mattis. Sed dapibus bibendum elementum.</p>
                </article>
                <article>
                    <h1>Article title</h1>
                    <p>Curabitur dictum viverra ante, in sodales nisi imperdiet ut. 
                       Proin cursus ipsum libero, vitae malesuada magna tincidunt 
                       quis. Proin orci neque, tristique sed vulputate eu, feugiat 
                       non ex.</p>
                </article>
            </div>        
        </div>
    </div>
    <footer>
        Footer here
    </footer>

    <script 
        src="https://code.jquery.com/jquery-3.3.1.slim.min.js" 
        integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" 
        crossorigin="anonymous"></script>
    <script 
        src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" 
        integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" 
        crossorigin="anonymous"></script>
    <script 
        src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" 
        integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" 
        crossorigin="anonymous"></script>
  </body>
</html>
```