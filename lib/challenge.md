# MongoDB CLI

## Getting Started

The prompts below each ask for you to write the query in MongoDB for performing
some action (described in the prompt). Your response should be a valid query and
it should be property formatted in Markdown. For example:

**Prompt:** Find all burgers in the `burgers` collection.

```
db.burgers.find({})
```

### Instructions

* Start your `mongo` server
* Connect to the `mongo` shell

### Prompts

**Prompt:** What is the command to start the `mongo` server?

mongod

**Prompt:** What is the command to connect to the `mongo` shell?

mongo

**Prompt:** What is the command for listing all `mongo` databases?

show dbs

**Prompt:** What command would you use to create a database called `burgers`?

use burgers_db

**Prompt:** What command would you use to add the collection `burger` to your
`burgers` database?

db.burger.insert({"name": "Turkey"})

**Prompt:** What is the command for listing all collections in a database?

show collections

## Inserting

### Prompts

**Prompt:** Insert a single burger into the `burgers` collection with the
following:

* a `patty` property set to `beef`
* a `cheese` property set to `false`
* a `toppings` set to an array with `ketchup`, `onions`, and `pickles`

> db.burger.insert({"patty": "beef", "cheese": "false", "toppings": ["ketchup","pickles","onions"]})


**Prompt:** Insert 10 burgers into the `burgers` collection with the following:

* a `patty` property that is set to one of: `beef`, `turkey`, or `veggie`
* a `cheese` property that is either `true` or `false`
* a `toppings` property that is either one of `ketchup`, `onions`, `pickles`,
  `mustard`, and `mayonnaise`





## Reading

The following prompts will have you querying (reading) from your `burger`
collection. If you don't have burgers in your database that match the query
criteria described below, you wont get any results back. So, add one or two that
match that criteria before running the query.

### Prompts

**Prompt:** What query would find all burgers with a `beef` patty?

> db.burger.find({"patty":"beef"})

**Prompt:** What query would find all burgers with cheese on them?

> db.burger.find({"cheese": "true"})

**Prompt:** What query would find a burger by it's ObjectId?

> db.burger.find({"_id":ObjectId("5e375c476bed3fcbdefd69e1")})

**Prompt:** What query would find all burgers with `ketchup` as a topping?

> db.burger.find({"toppings":"ketchup"})

**Prompt:** What query would find all burgers with either a turkey or veggie
patty?

> db.burger.find({patty: {$in: ["turkey", "veggie"]}}).pretty()

**Prompt:** What query would find all burgers with a beef patty and cheese?

> db.burger.find({patty: {$in: ["beef","cheese"]}})

**Prompt:** What query would find all burgers with a beef patty and ketchup as
a topping?

> db.burger.find({patty:"beef",toppings:"ketchup"}).pretty()

**Prompt:** What query would find all burgers with a beef patty and both onions
and pickles as toppings?

> db.burger.find({patty:"beef",toppings:"pickles",toppings:"onions"}).pretty()

**Prompt:** What query would find burgers with either a turkey patty or cheese?

> db.burger.find({$or: [{cheese:"true"},{patty:"turkey"}]})

## Update

### Prompts

**Prompt:** What query would update one burger by it's ObjectId, setting it's
"patty" to "pork"?



**Prompt:** What query would update all burgers with beef paddies to have
cheese? (i.e. set "cheese" to true)

## Delete

### Prompts

**Prompt:** What query would delete a burger by it's ObjectId?

**Prompt:** What query would delete all veggie burgers?

**Prompt:** What query would delete all burgers with pickles on them?



Extra:

How to rename a collection