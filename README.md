# angular-gihub-page

[Link to angular-github-page](https://codingwithstrangers.github.io/angular-github-page/)

I want an easy way to deploy an angular application as a github page to render
and sort some markdown files. It can be used to generate a static webpage for 
the github organization

# Steps to reproduce this repo from scratch

```
git init
git remote add origin git@github.com:codingwithstrangers/angular-github-page.git
ng new sample
git add -A
git commit -m "chore: initial commit"
git push
```

# Deploy with angular-cli-ghpages

```
cd sample
ng add angular-cli-ghpages
ng deploy --base-href=/angular-app/
```
Next go to https://github.com/<username>/<repositoryname> Settings and enable
github pages for the repository. The site can be found under this url:
https://<username>.github.io/<repositoryname>

# Deploy manually

```
cd sample
# build the site with: ng build --output-path docs --base-href /repository-name/
# ie
ng build --output-path docs --base-href /angular-app/
```
The build output can be found in `sample/docs/`

# Build, push and run Docker container
```
#Example
docker build -t codingwithstrangers/sample:latest .
docker login
docker push codingwithstrangers/sample:latest
docker run -d -p 80:80 codingwithstrangers/sample:latest
```
