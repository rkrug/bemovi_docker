# The Docker container works, but one can't run ImageJ as it needs to run headless.

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

This should open Rstudio. If it asks for a password, use


* **username** = `rstudio`
* **password** = `pwd`

## **<span style="color:red"> TODO </span>**
There are issues with running ImageJ headless - I don't have a solution at the moment.

Likely solution: use `ImageJ --headless -macro ...` instead of `java -jar ij.jar -macro ...`, but this needs to be tested before.
