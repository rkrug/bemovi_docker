## Build the images

```
cd master/3.6.0/
docker build -t bemovi_master .
```

or for the bemovi develop branch:


```
cd develop/3.6.0/
docker build -t bemovi_develop .
```

## Start the docker container:


### For bemovi_master
```
docker run -i -e PASSWORD=pwd --rm -p 8787:8787 -v /DIRETORY/TO/SHARE/:/home/rstudio/Documents bemovi_master
```

### For bemovi_develop
```
docker run -i -e PASSWORD=pwd --rm -p 8787:8787 -v /DIRETORY/TO/SHARE/:/home/rstudio/Documents bemovi_develop
```

## Access Rstudio
From your browser, goto

```
http://localhost:8787/
```

This should open Rstudio. If it asks for a password, use `pwd`.
