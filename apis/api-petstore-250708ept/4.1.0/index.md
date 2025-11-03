---
# NOTICE: Copyright 2025 Talend SA, Talend, Inc., and affiliates. All Rights Reserved. Customer’s use of the software contained herein is subject to the terms and conditions of the Agreement between Customer and Talend.
layout: "apiDefinition_1.1.0"
api-definition:
  specVersion: "4.1.0"
  info:
    name: "API Petstore 250708EPT"
    version: "4.1.0"
    description: "This is a sample server Petstore server.  You can find out more about Swagger at [http://swagger.io](http://swagger.io) or on [irc.freenode.net, #swagger](http://swagger.io/irc/).  For this sample, you can use the api key `special-key` to test the authorization filters."
    license:
      name: "Apache 2.0"
      url: "http://www.apache.org/licenses/LICENSE-2.0.html"
    contact:
      email: "apiteam@swagger.io"
    termsOfService: "http://swagger.io/terms/"
  contract:
    baseUrls:
    - url: "https://m16708kjr1i6bdq.eu.api-mocks.com"
      description: "URL du serveur du mock de votre API. Lorsqu'il est appelé, il simule le comportement de votre API."
      isPublished: true
    - url: "http://petstore.swagger.io/v2"
      isPublished: true
    mediaTypes:
    - "application/json"
    sections:
    - name: "Pet"
      elementOrder:
      - "#/contract/resources/1d880df7-26e9-43db-93fa-8e02e25d3c2d"
      - "#/contract/resources/423cc030-46ab-4e5b-888e-26fde3be73bf"
      - "#/contract/resources/9b71d344-b8a0-490e-a473-3b7ac792ad39"
      - "#/contract/resources/39e0fcb9-d5ec-4c68-a071-6bf270ff0de0"
      - "#/contract/resources/8acd2c5d-9a8c-4f5a-8e5d-84614551501e"
      - "#/contract/types/5708c654-fae9-4746-9c71-27cb31581e40"
      - "#/contract/types/9ccd9761-8e2a-4786-a35e-69b81d0b6708"
      - "#/contract/types/135f0729-d31a-4b36-bcb3-ebbb3c675604"
      - "#/contract/types/a6fb71b4-b694-432a-a0ab-3283ca88e44c"
    - name: "Store"
      elementOrder:
      - "#/contract/resources/39d22839-d327-465c-b84c-3f80f21c50f1"
      - "#/contract/resources/27b38f9a-1fec-4436-86de-a7ce7a80c438"
      - "#/contract/resources/87a4bb3c-d7d6-4426-ad8e-cbf792405e8d"
      - "#/contract/types/0fdae497-78b9-4b0b-8feb-5fd0674451ca"
    - name: "User"
      elementOrder:
      - "#/contract/resources/3561466c-3b20-4502-92a1-063490bbcb1d"
      - "#/contract/resources/953d1d5c-78bf-49c3-9d37-3662a4d3e558"
      - "#/contract/resources/373f21dd-1068-4576-bca3-6dc1185072f2"
      - "#/contract/resources/9b4c20d8-1894-4a8e-bef4-ed988d4572c3"
      - "#/contract/resources/991db52d-6380-4519-b1b2-d48f23babcac"
      - "#/contract/resources/2030d72d-2bf9-4375-b532-996bd03e50d8"
      - "#/contract/types/365e0d77-46c4-4312-a91f-dee8819d7494"
    securitySchemes:
      "92eb878b-1816-4dfb-a3ba-7d60597a16d3":
        name: "petstore_auth"
        type: "oauth2"
        settings:
          authorizationUri: "http://petstore.swagger.io/oauth/dialog"
          authorizationGrants:
          - "implicit"
          scopes:
            f9d02d6b-4993-4238-8278-389fda4018cf:
              name: "write:pets"
              description: "modify pets in your account"
            "89a8b475-56fe-4e6e-8da9-8e9541041968":
              name: "read:pets"
              description: "read your pets"
      "64c8c546-7a90-4689-9735-9289ba284279":
        name: "api_key"
        type: "custom"
        describedBy:
          headers:
          - name: "api_key"
            type: "STRING"
    resources:
      "9b71d344-b8a0-490e-a473-3b7ac792ad39":
        path: "/pet"
        section: "#/contract/sections/983cb6ee-d55c-4e3e-963c-fd00c8e8917c"
        operations:
          "66117941-7b5f-4587-bd42-9b3ffb28f959":
            name: "Update an existing pet"
            method: "PUT"
            description: ""
            operationId: "updatePet"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3"
              scopes:
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/f9d02d6b-4993-4238-8278-389fda4018cf"
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/89a8b475-56fe-4e6e-8da9-8e9541041968"
            bodies:
            - type: "#/contract/types/5708c654-fae9-4746-9c71-27cb31581e40"
              mediaTypes:
              - "application/json"
              - "application/xml"
            responses:
              b1455f2d-e9da-4efa-a834-dc9531ff6c05:
                status: "400"
                description: "Invalid ID supplied"
              a868f8bb-f8da-469d-8dd5-df65b11c6a1a:
                status: "404"
                description: "Pet not found"
              c2b7b9a9-db2f-4307-928f-5eab9d75b290:
                status: "405"
                description: "Validation exception"
          "63797b71-f494-45ed-9282-4ac579c2c70b":
            name: "Add a new pet to the store"
            method: "POST"
            description: ""
            operationId: "addPet"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3"
              scopes:
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/f9d02d6b-4993-4238-8278-389fda4018cf"
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/89a8b475-56fe-4e6e-8da9-8e9541041968"
            bodies:
            - type: "#/contract/types/5708c654-fae9-4746-9c71-27cb31581e40"
              mediaTypes:
              - "application/json"
              - "application/xml"
            responses:
              a8620583-efd5-46fc-8b6f-61645d5c1446:
                status: "405"
                description: "Invalid input"
      "423cc030-46ab-4e5b-888e-26fde3be73bf":
        path: "/pet/findByStatus"
        section: "#/contract/sections/983cb6ee-d55c-4e3e-963c-fd00c8e8917c"
        operations:
          ef57fd65-3ce2-44c3-b6a3-9b40eea5bc9a:
            name: "Finds Pets by status"
            method: "GET"
            description: "Multiple status values can be provided with comma separated strings"
            operationId: "findPetsByStatus"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3"
              scopes:
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/f9d02d6b-4993-4238-8278-389fda4018cf"
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/89a8b475-56fe-4e6e-8da9-8e9541041968"
            queryParameters:
            - name: "status"
              type: "ARRAY"
              description: "Status values that need to be considered for filter"
              required: true
              items:
                type: "STRING"
                default: "available"
                enum:
                - "available"
                - "pending"
                - "sold"
            responses:
              "1a19e0e0-db0f-4d39-babc-bf9cba2dc17d":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "ARRAY"
                  items:
                    type: "#/contract/types/5708c654-fae9-4746-9c71-27cb31581e40"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              c042d7f9-ee51-41c3-99d5-acec9ecc6665:
                status: "400"
                description: "Invalid status value"
      "1d880df7-26e9-43db-93fa-8e02e25d3c2d":
        path: "/pet/findByTags"
        section: "#/contract/sections/983cb6ee-d55c-4e3e-963c-fd00c8e8917c"
        operations:
          b4e9a1ed-5c22-41fb-8d1e-427fb9e3bb02:
            name: "Finds Pets by tags"
            method: "GET"
            description: "Muliple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing."
            operationId: "findPetsByTags"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3"
              scopes:
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/f9d02d6b-4993-4238-8278-389fda4018cf"
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/89a8b475-56fe-4e6e-8da9-8e9541041968"
            queryParameters:
            - name: "tags"
              type: "ARRAY"
              description: "Tags to filter by"
              required: true
              items:
                type: "STRING"
            responses:
              c652b27b-80ad-4d59-b868-d640edeb0194:
                status: "200"
                description: "successful operation"
                bodies:
                - type: "ARRAY"
                  items:
                    type: "#/contract/types/5708c654-fae9-4746-9c71-27cb31581e40"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              cb333039-3e59-4986-8bc7-6f061c57185c:
                status: "400"
                description: "Invalid tag value"
      "39e0fcb9-d5ec-4c68-a071-6bf270ff0de0":
        path: "/pet/{petId}"
        section: "#/contract/sections/983cb6ee-d55c-4e3e-963c-fd00c8e8917c"
        pathVariables:
        - name: "petId"
          type: "INTEGER"
          description: "ID of pet to return"
          required: true
        operations:
          "839cd8fa-5b83-4bb1-bc07-bcc114d12784":
            name: "Find pet by ID"
            method: "GET"
            description: "Returns a single pet"
            operationId: "getPetById"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/64c8c546-7a90-4689-9735-9289ba284279"
              scopes: []
            responses:
              "4b6f7de3-846f-49ca-b0da-88a6da810652":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/5708c654-fae9-4746-9c71-27cb31581e40"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "5cbd87d7-6fa5-4596-a737-1d833bd49c3b":
                status: "400"
                description: "Invalid ID supplied"
              "7eea3199-64f4-4a52-b5d8-ebc80ace8a6a":
                status: "404"
                description: "Pet not found"
          b9c34e8e-45a0-414f-b558-4e2eee2e9f0f:
            name: "Updates a pet in the store with form data"
            method: "POST"
            description: ""
            operationId: "updatePetWithForm"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3"
              scopes:
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/f9d02d6b-4993-4238-8278-389fda4018cf"
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/89a8b475-56fe-4e6e-8da9-8e9541041968"
            bodies:
            - type: "OBJECT"
              properties:
              - name: "name"
                type: "STRING"
                description: "Updated name of the pet"
              - name: "status"
                type: "STRING"
                description: "Updated status of the pet"
              mediaTypes:
              - "application/x-www-form-urlencoded"
            responses:
              d27d8981-d686-4897-9fdc-8721044ce4e7:
                status: "405"
                description: "Invalid input"
          "7a63b559-305c-4935-b31a-e31afc3ac817":
            name: "Deletes a pet"
            method: "DELETE"
            description: ""
            operationId: "deletePet"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3"
              scopes:
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/f9d02d6b-4993-4238-8278-389fda4018cf"
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/89a8b475-56fe-4e6e-8da9-8e9541041968"
            headers:
            - name: "api_key"
              type: "STRING"
            responses:
              "47acf7e2-c3b0-49a7-ba36-d8083b75bbcc":
                status: "400"
                description: "Invalid ID supplied"
              "0e97b17f-8dda-4157-94db-ad2d6a410d92":
                status: "404"
                description: "Pet not found"
      "8acd2c5d-9a8c-4f5a-8e5d-84614551501e":
        path: "/pet/{petId}/uploadImage"
        section: "#/contract/sections/983cb6ee-d55c-4e3e-963c-fd00c8e8917c"
        pathVariables:
        - name: "petId"
          type: "INTEGER"
          format: "INT64"
          description: "ID of pet to return"
          required: true
        operations:
          "3ac61902-ec53-4c44-ae28-a49a8c39fa39":
            name: "uploads an image"
            method: "POST"
            description: ""
            operationId: "uploadFile"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3"
              scopes:
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/f9d02d6b-4993-4238-8278-389fda4018cf"
              - "#/contract/securitySchemes/92eb878b-1816-4dfb-a3ba-7d60597a16d3/settings/scopes/89a8b475-56fe-4e6e-8da9-8e9541041968"
            bodies:
            - type: "OBJECT"
              properties:
              - name: "additionalMetadata"
                type: "STRING"
                description: "Additional data to pass to server"
              - name: "file"
                type: "FILE"
                description: "file to upload"
              mediaTypes:
              - "multipart/form-data"
            responses:
              "0703d819-d061-4977-a981-f1516775091d":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/a6fb71b4-b694-432a-a0ab-3283ca88e44c"
                  mediaTypes:
                  - "application/json"
      "87a4bb3c-d7d6-4426-ad8e-cbf792405e8d":
        path: "/store/inventory"
        section: "#/contract/sections/72d443d8-7898-4a4e-83c0-bc87a86e140f"
        operations:
          "4fea88b3-2769-4652-97e0-faca4447b799":
            name: "Returns pet inventories by status"
            method: "GET"
            description: "Returns a map of status codes to quantities"
            operationId: "getInventory"
            tags:
            - "store"
            securedBy:
            - scheme: "#/contract/securitySchemes/64c8c546-7a90-4689-9735-9289ba284279"
              scopes: []
            responses:
              e322f1a4-9961-4d45-8da5-ed9d0277ee20:
                status: "200"
                description: "successful operation"
                bodies:
                - type: "OBJECT"
                  mediaTypes:
                  - "application/json"
      "39d22839-d327-465c-b84c-3f80f21c50f1":
        path: "/store/order"
        section: "#/contract/sections/72d443d8-7898-4a4e-83c0-bc87a86e140f"
        operations:
          "2e327b89-eb99-43ca-b19f-8df52f4cb4a2":
            name: "Place an order for a pet"
            method: "POST"
            description: ""
            operationId: "placeOrder"
            tags:
            - "store"
            bodies:
            - type: "#/contract/types/0fdae497-78b9-4b0b-8feb-5fd0674451ca"
            responses:
              d618a45e-531f-44c6-8cc5-0483599fb87c:
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/0fdae497-78b9-4b0b-8feb-5fd0674451ca"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "43677b31-0ff8-4aad-9b27-35b4ff9d878d":
                status: "400"
                description: "Invalid Order"
      "27b38f9a-1fec-4436-86de-a7ce7a80c438":
        path: "/store/order/{orderId}"
        section: "#/contract/sections/72d443d8-7898-4a4e-83c0-bc87a86e140f"
        pathVariables:
        - name: "orderId"
          type: "INTEGER"
          format: "INT64"
          required: true
          minimum: 1
          maximum: 10
        operations:
          c01fe494-85d0-4dec-8773-35b81ca2154d:
            name: "Find purchase order by ID"
            method: "GET"
            description: "For valid response try integer IDs with value >= 1 and <= 10. Other values will generated exceptions"
            operationId: "getOrderById"
            tags:
            - "store"
            responses:
              b76ab6a5-a58a-46b7-8d39-5dd86b55ac23:
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/0fdae497-78b9-4b0b-8feb-5fd0674451ca"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              f496e9cc-b9ff-4ec7-bef9-47ec5b455480:
                status: "400"
                description: "Invalid ID supplied"
              d3410424-4e42-4aa6-9963-238ae6d0f084:
                status: "404"
                description: "Order not found"
          abeb8434-4bdb-41d9-afa4-a951ece3bfc9:
            name: "Delete purchase order by ID"
            method: "DELETE"
            description: "For valid response try integer IDs with positive integer value. Negative or non-integer values will generate API errors"
            operationId: "deleteOrder"
            tags:
            - "store"
            responses:
              e0a12986-997b-4619-be62-fb4c53320c4a:
                status: "400"
                description: "Invalid ID supplied"
              addeccae-778b-4af4-9561-b90259df2191:
                status: "404"
                description: "Order not found"
      "3561466c-3b20-4502-92a1-063490bbcb1d":
        path: "/user"
        section: "#/contract/sections/1546a876-de25-45f9-b18a-d5543b3575d9"
        operations:
          e1b3a6a2-c0dc-47e3-92a9-c64296fce588:
            name: "Create user"
            method: "POST"
            description: "This can only be done by the logged in user."
            operationId: "createUser"
            tags:
            - "user"
            bodies:
            - type: "#/contract/types/365e0d77-46c4-4312-a91f-dee8819d7494"
      "953d1d5c-78bf-49c3-9d37-3662a4d3e558":
        path: "/user/createWithArray"
        section: "#/contract/sections/1546a876-de25-45f9-b18a-d5543b3575d9"
        operations:
          e98a773d-1255-47d2-b828-7da531f58d88:
            name: "Creates list of users with given input array"
            method: "POST"
            description: ""
            operationId: "createUsersWithArrayInput"
            tags:
            - "user"
            bodies:
            - type: "ARRAY"
              items:
                type: "#/contract/types/365e0d77-46c4-4312-a91f-dee8819d7494"
      "373f21dd-1068-4576-bca3-6dc1185072f2":
        path: "/user/createWithList"
        section: "#/contract/sections/1546a876-de25-45f9-b18a-d5543b3575d9"
        operations:
          "1b5b95a4-b97a-43a0-8191-8e644bf64e07":
            name: "Creates list of users with given input array"
            method: "POST"
            description: ""
            operationId: "createUsersWithListInput"
            tags:
            - "user"
            bodies:
            - type: "ARRAY"
              items:
                type: "#/contract/types/365e0d77-46c4-4312-a91f-dee8819d7494"
      "991db52d-6380-4519-b1b2-d48f23babcac":
        path: "/user/login"
        section: "#/contract/sections/1546a876-de25-45f9-b18a-d5543b3575d9"
        operations:
          "4d517d08-30ea-4b7b-bd93-b5d1ecf9feb8":
            name: "Logs user into the system"
            method: "GET"
            description: ""
            operationId: "loginUser"
            tags:
            - "user"
            queryParameters:
            - name: "username"
              type: "STRING"
              description: "The user name for login"
              required: true
            - name: "password"
              type: "STRING"
              description: "The password for login in clear text"
              required: true
            responses:
              bffecc18-30c8-44e2-92d3-f93e78d625db:
                status: "200"
                description: "successful operation"
                headers:
                - name: "X-Rate-Limit"
                  type: "INTEGER"
                  format: "INT32"
                  description: "calls per hour allowed by the user"
                - name: "X-Expires-After"
                  type: "DATETIME"
                  description: "date in UTC when token expires"
                bodies:
                - type: "STRING"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "765e7a25-f404-4bc8-bed6-7c6621520a17":
                status: "400"
                description: "Invalid username/password supplied"
      "2030d72d-2bf9-4375-b532-996bd03e50d8":
        path: "/user/logout"
        section: "#/contract/sections/1546a876-de25-45f9-b18a-d5543b3575d9"
        operations:
          "2b149865-c437-443a-be81-f34989f3e99f":
            name: "Logs out current logged in user session"
            method: "GET"
            operationId: "logoutUser"
            tags:
            - "user"
            responses:
              ee06c328-842b-477e-92e9-eec0797f14eb:
                status: "200"
      "9b4c20d8-1894-4a8e-bef4-ed988d4572c3":
        path: "/user/{username}"
        section: "#/contract/sections/1546a876-de25-45f9-b18a-d5543b3575d9"
        pathVariables:
        - name: "username"
          type: "STRING"
          description: "The name that needs to be fetched. Use user1 for testing."
          required: true
        operations:
          "94963825-80cb-4bdf-97b2-96ac81575df5":
            name: "Get user by user name"
            method: "GET"
            description: ""
            operationId: "getUserByName"
            tags:
            - "user"
            responses:
              "9975e0ef-3999-4f49-9cb1-b2c1ef6a1dcb":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/365e0d77-46c4-4312-a91f-dee8819d7494"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "0feac683-8e4e-4ba2-92f8-53cda7758f67":
                status: "400"
                description: "Invalid username supplied"
              "8b4ad973-e302-4bf1-a63e-a5bef78e6699":
                status: "404"
                description: "User not found"
          "8228f835-083a-42ba-881d-b053bf22aa1e":
            name: "Updated user"
            method: "PUT"
            description: "This can only be done by the logged in user."
            operationId: "updateUser"
            tags:
            - "user"
            bodies:
            - type: "#/contract/types/365e0d77-46c4-4312-a91f-dee8819d7494"
            responses:
              "580127c0-bd77-479c-bcf1-a774423f1d6d":
                status: "400"
                description: "Invalid user supplied"
              "3341bccc-a02e-462d-bb36-5e21fdf05157":
                status: "404"
                description: "User not found"
          d7aa795d-d2e8-4df0-add9-82635d837ed3:
            name: "Delete user"
            method: "DELETE"
            description: "This can only be done by the logged in user."
            operationId: "deleteUser"
            tags:
            - "user"
            responses:
              db57ac22-7861-4a3d-ac31-e2e29c8f4a87:
                status: "400"
                description: "Invalid username supplied"
              "54e791c7-9bd7-4294-a1ad-e4c635096616":
                status: "404"
                description: "User not found"
    types:
      "0fdae497-78b9-4b0b-8feb-5fd0674451ca":
        name: "Order"
        type: "OBJECT"
        section: "#/contract/sections/72d443d8-7898-4a4e-83c0-bc87a86e140f"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "petId"
          type: "INTEGER"
          format: "INT64"
        - name: "quantity"
          type: "INTEGER"
          format: "INT32"
        - name: "shipDate"
          type: "DATETIME"
        - name: "status"
          type: "STRING"
          description: "Order Status"
          enum:
          - "placed"
          - "approved"
          - "delivered"
        - name: "complete"
          type: "BOOLEAN"
          default: false
      "135f0729-d31a-4b36-bcb3-ebbb3c675604":
        name: "Category"
        type: "OBJECT"
        section: "#/contract/sections/983cb6ee-d55c-4e3e-963c-fd00c8e8917c"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "name"
          type: "STRING"
      "365e0d77-46c4-4312-a91f-dee8819d7494":
        name: "User"
        type: "OBJECT"
        section: "#/contract/sections/1546a876-de25-45f9-b18a-d5543b3575d9"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "username"
          type: "STRING"
        - name: "firstName"
          type: "STRING"
        - name: "lastName"
          type: "STRING"
        - name: "email"
          type: "STRING"
        - name: "password"
          type: "STRING"
        - name: "phone"
          type: "STRING"
        - name: "userStatus"
          type: "INTEGER"
          format: "INT32"
          description: "User Status"
      "9ccd9761-8e2a-4786-a35e-69b81d0b6708":
        name: "Tag"
        type: "OBJECT"
        section: "#/contract/sections/983cb6ee-d55c-4e3e-963c-fd00c8e8917c"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "name"
          type: "STRING"
      "5708c654-fae9-4746-9c71-27cb31581e40":
        name: "Pet"
        type: "OBJECT"
        section: "#/contract/sections/983cb6ee-d55c-4e3e-963c-fd00c8e8917c"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "category"
          type: "#/contract/types/135f0729-d31a-4b36-bcb3-ebbb3c675604"
        - name: "name"
          type: "STRING"
          required: true
          examples:
          - value: "doggie"
        - name: "photoUrls"
          type: "ARRAY"
          required: true
          items:
            type: "STRING"
        - name: "tags"
          type: "ARRAY"
          items:
            type: "#/contract/types/9ccd9761-8e2a-4786-a35e-69b81d0b6708"
        - name: "status"
          type: "STRING"
          description: "pet status in the store"
          enum:
          - "available"
          - "pending"
          - "sold"
      a6fb71b4-b694-432a-a0ab-3283ca88e44c:
        name: "ApiResponse"
        type: "OBJECT"
        section: "#/contract/sections/983cb6ee-d55c-4e3e-963c-fd00c8e8917c"
        properties:
        - name: "code"
          type: "INTEGER"
          format: "INT32"
        - name: "type"
          type: "STRING"
        - name: "message"
          type: "STRING"
  components: {}
api-tryin: |-
  {
    "version" : 6,
    "entities" : [ {
      "entity" : {
        "type" : "Project",
        "name" : "API Petstore 250708EPT 4.1.0",
        "description" : "This is a sample server Petstore server.  You can find out more about Swagger at [http://swagger.io](http://swagger.io) or on [irc.freenode.net, #swagger](http://swagger.io/irc/).  For this sample, you can use the api key `special-key` to test the authorization filters.",
        "importedFrom" : "af665832-e702-40d0-871e-a72ed5f352a0"
      },
      "children" : [ {
        "entity" : {
          "type" : "Service",
          "name" : "Pet"
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "b4e9a1ed-5c22-41fb-8d1e-427fb9e3bb02",
            "name" : "Finds Pets by tags",
            "description" : "Muliple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/findByTags",
              "query" : {
                "delimiter" : "&",
                "items" : [ {
                  "name" : "tags",
                  "value" : "",
                  "enabled" : true
                } ]
              }
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "uriEditor" : true
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "ef57fd65-3ce2-44c3-b6a3-9b40eea5bc9a",
            "name" : "Finds Pets by status",
            "description" : "Multiple status values can be provided with comma separated strings",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/findByStatus",
              "query" : {
                "delimiter" : "&",
                "items" : [ {
                  "name" : "status",
                  "value" : "",
                  "enabled" : true
                } ]
              }
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "uriEditor" : true
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "66117941-7b5f-4587-bd42-9b3ffb28f959",
            "name" : "Update an existing pet",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet"
            },
            "method" : {
              "link" : "",
              "name" : "PUT",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            }, {
              "enabled" : false,
              "name" : "Content-Type",
              "value" : "application/xml"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "63797b71-f494-45ed-9282-4ac579c2c70b",
            "name" : "Add a new pet to the store",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            }, {
              "enabled" : false,
              "name" : "Content-Type",
              "value" : "application/xml"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "839cd8fa-5b83-4bb1-bc07-bcc114d12784",
            "name" : "Find pet by ID",
            "description" : "Returns a single pet",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : false,
              "name" : "api_key",
              "value" : "${\"Api_keyHeaderApi_key\"}"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "b9c34e8e-45a0-414f-b558-4e2eee2e9f0f",
            "name" : "Updates a pet in the store with form data",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/x-www-form-urlencoded"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Form",
              "formBody" : {
                "items" : [ {
                  "enabled" : false,
                  "name" : "name",
                  "value" : "",
                  "type" : "Text"
                }, {
                  "enabled" : false,
                  "name" : "status",
                  "value" : "",
                  "type" : "Text"
                } ],
                "encoding" : "application/x-www-form-urlencoded"
              }
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "7a63b559-305c-4935-b31a-e31afc3ac817",
            "name" : "Deletes a pet",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}"
            },
            "method" : {
              "link" : "",
              "name" : "DELETE"
            },
            "headers" : [ {
              "enabled" : false,
              "name" : "api_key",
              "value" : ""
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "3ac61902-ec53-4c44-ae28-a49a8c39fa39",
            "name" : "uploads an image",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}/uploadImage"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "multipart/form-data"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Form",
              "formBody" : {
                "items" : [ {
                  "enabled" : false,
                  "name" : "additionalMetadata",
                  "value" : "",
                  "type" : "Text"
                }, {
                  "enabled" : false,
                  "name" : "file",
                  "type" : "File"
                } ],
                "encoding" : "multipart/form-data"
              }
            }
          }
        } ]
      }, {
        "entity" : {
          "type" : "Service",
          "name" : "Store"
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "2e327b89-eb99-43ca-b19f-8df52f4cb4a2",
            "name" : "Place an order for a pet",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/order"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "c01fe494-85d0-4dec-8773-35b81ca2154d",
            "name" : "Find purchase order by ID",
            "description" : "For valid response try integer IDs with value >= 1 and <= 10. Other values will generated exceptions",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/order/{orderId}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "abeb8434-4bdb-41d9-afa4-a951ece3bfc9",
            "name" : "Delete purchase order by ID",
            "description" : "For valid response try integer IDs with positive integer value. Negative or non-integer values will generate API errors",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/order/{orderId}"
            },
            "method" : {
              "link" : "",
              "name" : "DELETE"
            },
            "headers" : [ ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "4fea88b3-2769-4652-97e0-faca4447b799",
            "name" : "Returns pet inventories by status",
            "description" : "Returns a map of status codes to quantities",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/inventory"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : false,
              "name" : "api_key",
              "value" : "${\"Api_keyHeaderApi_key\"}"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form"
          }
        } ]
      }, {
        "entity" : {
          "type" : "Service",
          "name" : "User"
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "e1b3a6a2-c0dc-47e3-92a9-c64296fce588",
            "name" : "Create user",
            "description" : "This can only be done by the logged in user.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "e98a773d-1255-47d2-b828-7da531f58d88",
            "name" : "Creates list of users with given input array",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/createWithArray"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "1b5b95a4-b97a-43a0-8191-8e644bf64e07",
            "name" : "Creates list of users with given input array",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/createWithList"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "94963825-80cb-4bdf-97b2-96ac81575df5",
            "name" : "Get user by user name",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/{username}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "8228f835-083a-42ba-881d-b053bf22aa1e",
            "name" : "Updated user",
            "description" : "This can only be done by the logged in user.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/{username}"
            },
            "method" : {
              "link" : "",
              "name" : "PUT",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "d7aa795d-d2e8-4df0-add9-82635d837ed3",
            "name" : "Delete user",
            "description" : "This can only be done by the logged in user.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/{username}"
            },
            "method" : {
              "link" : "",
              "name" : "DELETE"
            },
            "headers" : [ ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "4d517d08-30ea-4b7b-bd93-b5d1ecf9feb8",
            "name" : "Logs user into the system",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/login",
              "query" : {
                "delimiter" : "&",
                "items" : [ {
                  "name" : "username",
                  "value" : "",
                  "enabled" : true
                }, {
                  "name" : "password",
                  "value" : "",
                  "enabled" : true
                } ]
              }
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "uriEditor" : true
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "2b149865-c437-443a-be81-f34989f3e99f",
            "name" : "Logs out current logged in user session",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/logout"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ ],
            "headersType" : "Form"
          }
        } ]
      } ]
    } ],
    "environments" : [ {
      "name" : "API Petstore 250708EPT 4.1.0",
      "importedFrom" : {
        "projectId" : "af665832-e702-40d0-871e-a72ed5f352a0"
      },
      "variables" : {
        "e12428d2-72c6-4721-ad68-3e16b16f5609" : {
          "name" : "BaseUrl",
          "value" : "https://m16708kjr1i6bdq.eu.api-mocks.com",
          "enabled" : true,
          "private" : false
        },
        "b3173358-6717-4086-8091-9463196c95a7" : {
          "name" : "Api_keyHeaderApi_key",
          "value" : "",
          "enabled" : true,
          "private" : true
        }
      }
    }, {
      "name" : "API Petstore 250708EPT 4.1.0",
      "importedFrom" : {
        "projectId" : "af665832-e702-40d0-871e-a72ed5f352a0"
      },
      "variables" : {
        "30f55967-38d3-4d00-af27-c189bcebfeca" : {
          "name" : "BaseUrl",
          "value" : "http://petstore.swagger.io/v2",
          "enabled" : true,
          "private" : false
        },
        "0a648226-79d7-40e1-9f51-3f85c2626362" : {
          "name" : "Api_keyHeaderApi_key",
          "value" : "",
          "enabled" : true,
          "private" : true
        }
      }
    } ]
  }
---
