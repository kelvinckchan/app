
> Build and run
```
docker build -t getting-started .
docker run -dp 3000:3000 getting-started
docker tag getting-started YOUR-USER-NAME/getting-started
```

> Persisting data with named volume
```
docker volume create todo-db
```

> Check image 
```
docker ps
docker stop <the-container-id>
docker rm -f <id>
```


> Run with Dev tool livereload
> * -d : detached mode (run in background)
> * -p : port mapping
> * -v : mounting volumn
> * image name and tag
> * sh : shell command in alpine run yarn install for dependencies

```
docker run -dp 3000:3000 `
    -v todo-db:/etc/todos `
    -w /app -v "$(pwd):/app" `
    kelvinckchan94/node:12-alpine `
    sh -c "yarn install && yarn run dev" 
```

