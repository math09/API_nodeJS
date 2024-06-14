# Cours API nodeJS

FireBase

### outil de management des versions nodeJS :
- NVM
- WSL

SliDev


Pas de var uniquement let et const (plus sécuritaire)

### syntaxe js compris par les moteurs de recherche
- CJM 
- ESM (excmasript module)


```
const fs = require("fs");
const http = require("http");

const server = http.createServer((request, response)=> {
  const url = request.url;
  const method = request.method
  if (url === '/'){
    response.write(`
    <html>
        <body>
            <form action="/message" method="POST">
            <input type="text" name="message">
                <button type="submit"> Send </button>
            </form>
        </body>
    </html>
    `)
    return response.end();
  }
  if (url === '/message' && method==='POST'){
    fs.writeFileSync('toto.txt',"POST request");
    response.statusCode = 200;
    response.setHeader("Location", "/");
    return response.end();

  }

})

server.listen(3000);
```