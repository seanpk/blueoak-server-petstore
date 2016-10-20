# BlueOak Pet Store OpenAPI definition

> What would the Swagger Pet Store example look like if written with BlueOak?

**This**.

## The Starting Point

This is an implementation of the [`heroku-pets` example from swagger-editor](https://github.com/swagger-api/swagger-editor/blob/996cc252aeebdb46d3f09e67c6396a077e1ceaf2/spec-files/heroku-pets.yaml).

### For Local Reference:

```yaml
swagger: '2.0'
info:
  version: 1.0.0
  title: PetStore on Heroku
  description: |
    **This example has a working backend hosted in Heroku**

    You can try all HTTP operation described in this Swagger spec.
    
    Find source code of this API [here](https://github.com/mohsen1/petstore-api)
host: petstore-api.herokuapp.com
basePath: /pet
schemes:
  - http
  - https
consumes:
  - application/json
  - text/xml
produces:
  - application/json
  - text/html
paths:
  /:
    get:
      parameters:
        - name: limit
          in: query
          description: number of pets to return
          type: integer
          default: 11
          minimum: 11
          maximum: 10000
      responses:
        200:
          description:  List all pets
          schema:
            title: Pets
            type: array
            items:
              $ref: '#/definitions/Pet'
    post:
      parameters:
        - name: pet
          in: body
          description: The pet JSON you want to post
          schema:
            $ref: '#/definitions/Pet'
          required: true
      responses:
        200:
          description: Make a new pet
    put:
      parameters:
        - name: pet
          in: body
          description: The pet JSON you want to post
          schema:
            $ref: '#/definitions/Pet'
          required: true
      responses:
        200:
          description: Updates the pet
  /{petId}:
    get:
      parameters:
        - name: petId
          in: path
          type: string
          description: ID of the pet
          required: true
      responses:
        200:
          description: Sends the pet with pet Id

definitions:
  Pet:
    type: object
    properties:
      name:
        type: string
      birthday:
        type: integer
        format: int32

```
