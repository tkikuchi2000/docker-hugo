# docker-hugo

Usage

```bash
# Create new site
$ git clone https://github.com/yourname/your-hugo-repo.git site
$ echo 'SITE=/path/to/your/site' > .env
$ docker-compose up -d
```

docker-compose.yml
```yml
version: '3'
services:
  alpine-hugo:
    image: andthensome/alpine-hugo-git-bash
    env_file: .env
    volumes:
      - ./site:${SITE}
    ports:
      - "1313:1313"
    working_dir: ${SITE}
    entrypoint: ['hugo', 'server', '-D', '--bind', '0.0.0.0']
```


