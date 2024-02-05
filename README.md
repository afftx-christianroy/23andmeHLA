
# My links

https://www.jade-cheng.com/au/23andme-to-plink/
https://www.biostars.org/p/165472/
https://bioconductor.org/packages/release/bioc/vignettes/HIBAG/inst/doc/Implementation.html
https://anaconda.org/bioconda/plink
https://www.cog-genomics.org/plink/1.9/input#23file
# HLA imputation Using a 23andMe Genome

This repository contains an web shell for the [HIBAG project](http://www.biostat.washington.edu/~bsweir/HIBAG/), implemented using flask, gunicorn, nginx and wrapped in a convenient Docker container. It can be accessed online at [hla.nicokist.com](http://hla.nicokist.com).

To run it locally you should execute the following:

```
docker run --name some-redis -d redis
docker build -t 23andmehla:latest .
docker run -e flask_secret_key='ThisSecretIsNotUsedInDeployment' --link some-redis:redis -p 5000:5000 -p 8000:80 23andmehla
```
