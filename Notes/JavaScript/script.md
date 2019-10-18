### Как оформляется скрипт

#### HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>

<script type="text/javascript">
    function compare(a, b) {
        if (a < b) {
            console.log("A is less than B");
        } else if (a > b) {
            console.log("A is greater than B");
        } else {
            console.log("A is equal to B");
        }
    }
</script>

<p>Hello</p>

</body>
</html>
```

#### XHTML

```xhtml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE html
        PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
        "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
<head>
    <title>Title</title>
</head>
<body>
<script type="text/javascript">
    //<![CDATA[
    function compare(a, b) {
        if (a < b) {
            console.log("A is less than B");
        } else if (a > b) {
            console.log("A is greater than B");
        } else {
            console.log("A is equal to B");
        }
    }
    //]]>
</script>

<p>Hello</p>

</body>
</html>
```