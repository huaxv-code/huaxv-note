# css 文件

!!! note "css 文件引入"

    ```css title="mystyle.css"
    body {
    background-color: lightblue;
    }

    h1 {
    color: navy;
    margin-left: 20px;
    }
    ```

    ```html title="myhtml.html"
    <!DOCTYPE html>
    <html>
        <head>
            <!-- 引入 css 文件 -->
            <link rel="stylesheet" type="text/css" href="mystyle.css">
        </head>
        <body>

            <h1>This is a heading</h1>
            <p>This is a paragraph.</p>

        </body>
    </html>    
    ```