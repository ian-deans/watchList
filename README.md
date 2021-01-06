# Watch List

A practice in decoupling functionality into microservices

PostgreSQL database with a GraphQL layer provided by Hasura
Google's Firebase for cloud based services

The idea here is to build an api service that is completely independent of the ui. Rather than create a react or react native app that does most of the work and saves data to the database, I want to create a service of sorts using just hasura on heroku for sql db and graphql layer and firebase http functions to perform all the searches. 

This might cause a higher cost due to the bulk of the processing being done in firebase. Maybe make an sdk? If I could provide all the features and functionality in the form of a javascript class, then perhaps that would make it easier to create multiple ui applications without rewriting any functionality.

<br>
<br>
<br>

### SDK Class Approach
<hr>

The class would have to be able to:
- log a user in
- request the user's list and return the data
- search for programs relevent to the user's search term and return the results
- request to save a program to the user's list

```js
const app = new WatchList()

app.loginUser('ideans', 'password')

let watchListData = app.getList()

let searchResults = app.searchForProgram('user provided search string')

watchListData = app.saveToList( searchResults[ 3 ] )
```


```js
class WatchList {
    constructor() {
        this.user = null;
    }

    getList() {
        if (!this.user) {
            throw "No user logged in!"
        }

        
    }
}
```