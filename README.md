Docker build files for Codementor
=============

## Install 

### Prepare images

```
docker pull lazywei/cm_psql:latest
docker pull lazywei/cm_rails:latest
```

### Create data-only container to make gems and db data persistent

_Only need to run this command at the first time_

```
docker run -d -v /ruby_gems -v /pg_data --name cm_data busybox echo Data-only container for codementor
```


## When developing

### Start PostgreSQL

```
docker run --rm -P --name cm_pg lazywei/cm_psql
```

### Start Main Container

```
docker run --rm -it --volumes-from cm_data --link cm_pg:pg lazywei/cm_rails:latest
```
