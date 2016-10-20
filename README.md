# BlueOak Server Pet Store

_What would the Swagger Pet Store example look like if written with BlueOak?_

**This**.

## Things to Notice

1. the Swagger spec is spread across several files that get joined together on BOS start
1. `$ref`s in the spec are the relative paths to the files with the details of the desired object
1. the BOS "$ref compiler" is used to add all `definitions`, `parameters`, and `responses` to the end of the main spec file
	1. because of that, our `nodemon.json` file is set to ignore `.yaml` files in the `swagger` directory
	1. because we're not watching the root spec file for changes, we put as little data there as possible 

## How to Try

1. start the server using either `npm start` or `nodemon`
1. take a look at the swagger spec served from `http://localhost:3003/swagger/bos-petstore`
    1. if you have `swagger-commander` (do `npm i -g swagger-commander` if you don't) you can simply run it to explore
    1. if you have `swagger-ui` to run locally, you can point it to that URl to see it's representation of the spec
