#### MOBILFOX test project: urls ☕

##### Technologies

* docker (optional)
* go (echo framework)
* angular (front-end framework)
* postgres or sqlite

##### Description

You can use any ORM / database to create the following functionality. The front-end's design doesn't matter as long as its understandable.
Give yourself a timeframe, document it and separate your commits by features. You can use docker & compose to make a smooth setup experience.

#### Back-end

Create the following endpoints in go using echo framework:


* POST
    * /urls/new
        * Create an endpoint where if you submit an URL (https://google.com/), it creates a 8 character random hash (AbG45JL9) lets call it short-link and saves it along with the sent URL. If the url has already been submitted it creates no exta records.
* GET
    * /urls
        * Create an endpoint that lists all saved urls with their short link.
* GET
    * /url/<short_link>
        * Returns the URL belonging to the given shortlink, if it does not exist it returns 404 error code.
* DELETE
    * /url/<short_link>
        * Deletes the URL belonging to the given shortlink, if it does not exist it returns 404 error code.

#### Front-end

* Create a page with a form where you can submit a new URL using "POST /urls/new".
* Create a page where it shows all available URLs fetched from the go service along with their short-link. The short-link should be a html link leading to the corresponding page. (AbG45JL9 -> when clicked forwards you to "GET /url/AbG45JL9")
* On the "GET /url/<short_link>" page make a delete button that forwards you back to the "GET /urls" page and deletes the corresponding link & short-link from the db.
