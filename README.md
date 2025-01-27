<p align="center">
  <h1>Enketo - ODK Backend</h1>
</p>

## About :open_book:

Enketo has been used all around the world for a wide range of uses from needs assessments in humanitarian aid, to raising historical awareness, to clinical research, to election monitoring.

## Features :dart:

- [x] Can connect to your custom backend
- [ ] Have the edit api in case user wants to edit submitted response
- [ ] Api for the customize change in XML of form
- [x] Have beautiful themes and widgets
- [x] Are printer-friendly
- [x] Can use very powerful skip and validation logic
- [x] Run on any device, mobile or desktop, as long as it has a fairly modern browser

## Use Case :rocket:

![Screencast from 03-02-22 05_31_50 PM IST](https://user-images.githubusercontent.com/56133783/152341126-ac03baa3-258c-473a-956a-d0973682234a.gif)


## Requirements :scroll:

1. Your machine should have [Yarn](https://classic.yarnpkg.com/en/docs/install/#windows-stable) or [Npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm), [Docker](https://docs.docker.com/get-docker/), [Python](https://www.python.org/downloads/) installed.

*Note: Preferable Npm version (6.14.15) and Node version(v14.18.1) and Ubuntu OS version(18.04)**

2. Check the node and npm version by running following commands.
```sh
node -v
npm -v
```


## Installation Steps :walking:

### 1. Fork it :fork_and_knife:

You can get your own fork/copy of [enketo](https://github.com/Samagra-Development/enketo) by using the <kbd><b>Fork</b></kbd> button.

### 2. Clone it :busts_in_silhouette:

You need to clone (download) it to a local machine using

```sh
git clone https://github.com/Your_Username/enketo.git
```

> This makes a local copy of the repository in your machine.

Once you have cloned the `enketo` repository in GitHub, move to that folder first using the change directory command.

```sh
# This will change directory to a folder enketo
cd enketo
```

Move to this folder for all other commands.

### 3. Set it up :arrow_up:

Run the following commands to see that _your local copy_ has a reference to _your forked remote repository_ in GitHub :octocat:

```sh
git remote -v
origin  https://github.com/Your_Username/enketo.git (fetch)
origin  https://github.com/Your_Username/enketo.git (push)
```
### 4. Run it :checkered_flag:

```sh
cd enketo-express
docker run --name enketo-redis-main -p 6379:6379 -d redis
docker run --name enketo-redis-cache -p 6380:6379 -d redis
npm install
npm i -g grunt
grunt develop
```

```sh
cd ../enketo-core
npm install
npm start
```

```sh
cd ../enketo-transformer
npm install
npm start
```

```sh
cd ../forms
python3 -m http.server
```

You can preview your form on http://localhost:8005/preview?xform=http://localhost:8000/sample.xml

### 5. For integrating your backend
Customize the [submission url](https://github.com/Samagra-Development/enketo/blob/main/enketo-express/public/js/src/module/connection.js#L150) with your hosted backend. 

## Future Enhancements :rocket:

- [Encrypting query parameters on rendering the enketo form. ](https://github.com/Samagra-Development/enketo/issues/1)
- Writing a API for changing an XML form directly from it.
