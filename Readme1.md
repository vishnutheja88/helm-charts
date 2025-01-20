# push image to Github package (GHCR)
1. create image
    ```t
        docker build -t hello .
        docker images
        docker run hello
    ```
2. Create PAT on GitHub
    generate personal access token
        github >> Settings >> Developer Settings >> Personal Access Tokens >> Generate new token
        Note: GHRC
        Expiration:  90 days
        [x] write: packages
            [x] read:packages
        [x] delete: packages
        >> generate token

3. Authenticate GHCR
    ```t
        docker tag hello ghcr.io/vishnutheja88/hello:latest
        docker images
        docker push ghcr.io/vishnutheja88/hello:latest
        export CR_PAT= <token>
        echo $CR_PAT | docker login ghcr.io -u vishnutheja88 --password-stdin
        docker push ghcr.io/vishnutheja88/hello:latest
    ```
4. Tag and push our image to Github Container Registry (GHCR)

