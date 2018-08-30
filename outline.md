# Endpoint testing and E2E Testing

## Endpoint testing

Endpoint testing is writing code to test endpoints and ensure they preform the required task.

There are a lot of programs that can do Endpoint tests but an easy one to work with is postman.
we can create a collection of tests that can rely on data we get from other tests. It can be used to dynamically create endpoints as well based on global variables we set.

### Tests

We will be testing the pokemon Api and the data we get back from it. We will be using the data from the responses to do other requests that relate to the original request.

we can run code before the first request to set up values.
lets set a global variable using:
  `pm.globals.set('property', value)`

we can use this global variable in the url to get dynamic information

to access the response in the test you can do so using
`pm.response.json()`
without the json it will not parse the response and it is unreadable.

the perform a test it typically looks like this.
`pm.test("test description", () => {
  pm.expect(valueToTest).to.equal(valueToEqual)
})`

There are a few other test we can use like,
`pm.response.to.have.status(200)`
`.to.contain()`
`.to.be.true`

## Cypress
- have the class clone https://github.com/DevMountain/cypress_walkthrough
- open a second terminal to have everyone run `npm i -g cypress`

- Talk about what cypress is and how it can save so much time testing functionality of a website.
- once app is installed have everyone run npm i, then have them check package.json to see scrips.
- when we run `npm run cypress`
- to start run the file that comes with cypress to show how amazing the tool is
- then we will mess around with selecting items on https://example.cypress.io and running tests on it
  - do things like select a link and click it, then find an input and type in it
  - do a few examples of these.
  - show '{enter}' is the enter key.

- we will build out a bunch of functionality to test the todo app
  - show the cypress.json and add base url
    - with this we can just use visit('/')
  -