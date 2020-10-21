# Setup

1/

```
git clone https://github.com/fastdev-today/Gatsby.js.git
```

2/ 

```
docker run --rm -w "/app" -v $(pwd):/app node /bin/bash -c "npm install -g gatsby-cli; gatsby new hello-world"

//PowerShell Windows 10
docker run --rm -w "/app" -v "$(pwd):/app" node /bin/bash -c "npm install -g gatsby-cli; gatsby new hello-world" 
```

3/

- Move the content of the `hello-world` folder into the root `./`
- Delete the `node_modules`
- Update `package.json` and add `-H 0.0.0.0`

```
...
    "develop": "gatsby develop -H 0.0.0.0",
...
```

4/

```
docker build
docker run develop?
```

# Build

This build uses the `Dockerfile`

```
docker build --tag gatsbyjs .
```

# Lunch

```
docker run --rm -it -v "${PWD}/src:/app/src" -v "${PWD}/gatsby-browser.js:/app/gatsby-browser.js" -v "${PWD}/gatsby-config.js:/app/gatsby-config.js" -v "${PWD}/gatsby-node.js:/app/gatsby-node.js" -v "${PWD}/gatsby-ssr.js:/app/gatsby-ssr.js" -p 80:8000 -e CHOKIDAR_USEPOLLING=true --name gatsbyjs8000 gatsbyjs
```

```
localhost:80
```