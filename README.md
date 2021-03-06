# Secret-Harbor
Heroku app using [Tesseract OCR](https://code.google.com/p/tesseract-ocr/) written in Python and based on the [Flask web microframework](http://flask.pocoo.org/). Only English and Finnish language are supported.

## Quick Start - Push the Button!

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

## Configuration
In addition to the default [heroku-buildpack-python](https://github.com/heroku/heroku-buildpack-python), this app also requires the custom [heroku-buildpack-tesseract](https://github.com/matteotiziano/heroku-buildpack-tesseract).  

Heroku natively supports [multiple buildpacks per app](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app).

Before deploying the app, you should setup the base buildpack and add the custom buildpack to the app configuration:
```
heroku buildpacks:set heroku/python
heroku buildpacks:add https://github.com/matteotiziano/heroku-buildpack-tesseract
```

## How to use
Let us assume you have deployed this app in Heroku and you called it `your-heroku-app`.

The app provides a REST method `https://your-heroku-app.herokuapp.com/process`: the client provides the input url (text), whereas the REST method returns a JSON object containing the OCR of the input.

## Licence
MIT Licence. Anson Liu, using work of Matteo Maggioni
