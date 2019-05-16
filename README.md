# YugaStore in Java
**NOTE: these instructions are still in progress.**

This is an implementation of a sample ecommerce app. This online retail marketplace app uses Spring (Java), React and YugaByte DB. It has the following microservices:

* products-microservice
* checkout-microservice
* react-ui

# Building the app

To build, simply run the following from the base directory:

```
$ mvn -DskipTests package
```

To run the app, you need to first install YugaByte DB, create the necessary tables, start each of the microservices and finally the React UI.

## Running the app

Make sure you have built the app as described above. Now do the following steps.

## Step 1: Install and initialize YugaByte DB

You can [install YugaByte DB by following these instructions](https://docs.yugabyte.com/latest/quick-start/).

Now create the necessary tables as shown below. Note that these steps would take a few seconds.

```
$ cd resources
$ cqlsh -f schema.cql
```

Next, load some sample data.

```
$ cd resources
$ ./dataload.sh
```

## Step 2: Start the products microservice

To run the products microservice, do the following:

```
$ cd products-microservice/
$ mvn spring-boot:run
```

## Step 3: Start the checkout microservice

## Step 4: Start the UI

To do this, simply run `npm start` from the `frontend` directory:

```
$ cd react-ui/frontend
$ npm start
```
