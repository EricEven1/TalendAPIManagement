---
# NOTICE: Copyright 2025 Talend SA, Talend, Inc., and affiliates. All Rights Reserved. Customer’s use of the software contained herein is subject to the terms and conditions of the Agreement between Customer and Talend.
layout: "apiDefinition_1.1.0"
api-definition:
  specVersion: "4.1.0"
  info:
    name: "APIPretsEP"
    version: "1.0.0"
    description: "API d'apprentissage \nLe 20/10/2025"
    license: {}
    contact:
      name: "Eric Proust"
      email: "eric.proust@even.fr"
  contract:
    baseUrls:
    - url: "https://ecckpdj69thuaik.eu.api-mocks.com"
      description: "URL du serveur du mock de votre API. Lorsqu'il est appelé, il simule le comportement de votre API."
      isPublished: true
    mediaTypes:
    - "application/json"
    sections:
    - name: "Entité"
      description: "Section regroupant les entités"
      elementOrder:
      - "#/contract/types/65e6b88c-72f9-4c1b-b59a-e432375e9a1c"
      - "#/contract/types/9925c06e-8e2a-475f-8d1e-4361faa92b12"
    unsortedElementOrder:
    - "#/contract/types/674bb782-309e-4f85-a464-eb4700db3efa"
    - "#/contract/types/1e0236f7-e525-4f48-9dd6-84150df8f907"
    - "#/contract/resources/1c11c281-7c90-45e4-9726-2927c11bf83b"
    - "#/contract/resources/05c88f36-acd1-4b32-9010-7dd10d8482a5"
    - "#/contract/texts/74ee2901-5cb3-4bdc-8bdb-e9b9f66c9e1d"
    securitySchemes:
      bdfd56c5-4758-4993-ba1d-cd1aa1a446b0:
        name: "Authentification \"Bearer\""
        type: "bearer"
        settings: {}
        describedBy:
          headers:
          - name: "Authorization"
            type: "STRING"
            required: true
      "6bdaeda2-c376-47f2-8700-5233a2b0eabe":
        name: "Basic authentication"
        type: "basic"
        describedBy: {}
    securedBy:
    - scheme: "#/contract/securitySchemes/bdfd56c5-4758-4993-ba1d-cd1aa1a446b0"
    resources:
      "1c11c281-7c90-45e4-9726-2927c11bf83b":
        path: "/demandes"
        operations:
          "980306bf-9a6f-47f3-8deb-d4f73f450388":
            name: "Obtenir les demandes de prêts"
            method: "GET"
            description: "Obtenir la liste de toutes les demandes de prêts qui vous sont accessibles"
            responses:
              "3558a980-cc48-484b-adf4-768890bc0e16":
                status: "200"
                bodies:
                - type: "ARRAY"
                  items:
                    type: "STRING"
                    required: false
              b6f58e04-3465-4ac8-977f-293a70145b4e:
                status: "4XX"
                reference: "#/components/responses/39371974-3ec9-4aee-9aa2-2978365c2e06"
          "94b3b6c1-0d36-418f-a4bf-1b246d0efa45":
            name: "Soumettre une demande de prêt"
            method: "POST"
            description: "Créer et soumettre une demande de prêt"
            bodies:
            - type: "#/contract/types/1e0236f7-e525-4f48-9dd6-84150df8f907"
            responses:
              "5ae5dd91-3af1-4c4e-b095-d13d860529f5":
                status: "201"
                bodies:
                - type: "OBJECT"
                  properties:
                  - name: "idPret"
                    type: "STRING"
                    required: true
              b0af5a70-fb89-4f90-a1bf-5b89da2f9ac6:
                status: "4XX"
                reference: "#/components/responses/39371974-3ec9-4aee-9aa2-2978365c2e06"
      "05c88f36-acd1-4b32-9010-7dd10d8482a5":
        path: "/demandes/{idPret}"
        pathVariables:
        - name: "idPret"
          type: "STRING"
          required: true
        operations:
          "85ce90d1-6d8d-4e56-bcb2-677f0a961444":
            name: "Obtenir une demande de prêt par ID"
            method: "GET"
            description: "Obtenir une demande de prêt spécifique en utilisant son ID"
            responses:
              "39858da0-6e17-451f-81d5-e880c59afa1b":
                status: "200"
                bodies:
                - type: "#/contract/types/1e0236f7-e525-4f48-9dd6-84150df8f907"
              "7c9f0126-9add-43b6-89e2-27764d10fbfb":
                status: "4XX"
                reference: "#/components/responses/39371974-3ec9-4aee-9aa2-2978365c2e06"
          "39a75531-3a24-4d2e-a1f8-5585070172e3":
            name: "Mettre à jour une demande de prêt"
            method: "PUT"
            description: "Mettre à jour une demande de prêt existante"
            queryParameters:
            - name: "Demande"
              type: "#/contract/types/1e0236f7-e525-4f48-9dd6-84150df8f907"
              required: true
            responses:
              "4ca48644-2f02-41a0-ad70-10adcaae8863":
                status: "201"
              ab0cf24f-414b-4d12-aafb-d90802195ce3:
                status: "4XX"
                reference: "#/components/responses/39371974-3ec9-4aee-9aa2-2978365c2e06"
          d421314a-c70d-4bec-a04a-ba1f49432c1e:
            name: "Annuler une demande de prêt"
            method: "DELETE"
            description: "Annuler une demande de prêt existant"
            responses:
              ff4f55fd-7a79-4019-82a8-9e22a506bdce:
                status: "200"
              "6d9e9f1d-0602-45ef-87d5-09afc6b88bff":
                status: "4XX"
                reference: "#/components/responses/39371974-3ec9-4aee-9aa2-2978365c2e06"
    types:
      "674bb782-309e-4f85-a464-eb4700db3efa":
        name: "Adresse"
        type: "OBJECT"
        required: false
        properties:
        - name: "rue"
          type: "STRING"
          required: false
          examples:
          - value: "ZI Traon Bihan"
        - name: "rue2"
          type: "STRING"
          required: false
        - name: "codePostal"
          type: "STRING"
          required: false
          examples:
          - value: "29200"
          - value: "35100"
        - name: "ville"
          type: "STRING"
          required: false
          examples:
          - value: "Ploudaniel"
          - value: "Paris"
          - value: "Rome"
        - name: "etat"
          type: "STRING"
          required: false
          examples:
          - value: "Californie"
        examples:
        - value: "{\r\n\t\"rue\": \"3185 Gateway Avenue\",\r\n\t\"rue2\": \"\",\r\n\t\"codePostan\": \"93301\",\r\n\t\"ville\": \"Bakersfield\",\r\n\t\"etat\": \"CA\"\r\n}"
      "65e6b88c-72f9-4c1b-b59a-e432375e9a1c":
        name: "Personne"
        type: "OBJECT"
        section: "#/contract/sections/62c6d1e1-c538-4589-bb5e-14f89a0fe5dc"
        properties:
        - name: "Nom"
          type: "STRING"
          required: true
        - name: "prenom"
          type: "STRING"
          required: true
        - name: "adresse"
          type: "#/contract/types/674bb782-309e-4f85-a464-eb4700db3efa"
          required: true
      "9925c06e-8e2a-475f-8d1e-4361faa92b12":
        name: "Societe"
        type: "OBJECT"
        section: "#/contract/sections/62c6d1e1-c538-4589-bb5e-14f89a0fe5dc"
        properties:
        - name: "nomSociete"
          type: "STRING"
          required: true
        - name: "typeSociete"
          type: "STRING"
          required: true
          enum:
          - "SA"
          - "SARL"
          - "EURL"
          - "GIE"
        - name: "adresse"
          type: "#/contract/types/674bb782-309e-4f85-a464-eb4700db3efa"
          required: true
      "1e0236f7-e525-4f48-9dd6-84150df8f907":
        name: "Demande"
        type: "OBJECT"
        properties:
        - name: "idPret"
          type: "STRING"
          restrictions: "READ_ONLY"
          required: true
        - name: "typePret"
          type: "STRING"
          required: true
          enum:
          - "Entreprise"
          - "Personnel"
        - name: "infoDemandeur"
          type: "ONEOF"
          required: true
          oneOf:
          - "#/contract/types/65e6b88c-72f9-4c1b-b59a-e432375e9a1c"
          - "#/contract/types/9925c06e-8e2a-475f-8d1e-4361faa92b12"
        - name: "etatApplication"
          type: "STRING"
          restrictions: "READ_ONLY"
          required: true
          enum:
          - "En attente"
          - "Approuvée"
          - "Rejetée"
        - name: "detailPret"
          type: "OBJECT"
          required: true
          properties:
          - name: "montant"
            type: "NUMBER"
            required: true
          - name: "duree"
            type: "INTEGER"
            required: true
          - name: "mensualite"
            type: "NUMBER"
            required: true
    texts:
      "74ee2901-5cb3-4bdc-8bdb-e9b9f66c9e1d":
        title: "Bloc de texte exemple"
        content: "Ce bloc permet de donner des informations"
  components:
    pathVariables:
      b530120a-c22e-4348-815b-6bfbec075864:
        name: "idPret"
        componentName: "idPret"
        type: "STRING"
        description: "Identifiant d'un prêt"
        required: true
    responses:
      "39371974-3ec9-4aee-9aa2-2978365c2e06":
        status: "4XX"
        componentName: "Erreur"
        description: "Erreur"
        bodies:
        - type: "OBJECT"
          properties:
          - name: "message"
            type: "STRING"
            required: false
          examples:
          - value: "Une erreur est survenue, réessayez ou contactez le Support"
api-tryin: |-
  {
    "version" : 6,
    "entities" : [ {
      "entity" : {
        "type" : "Project",
        "name" : "APIPretsEP 1.0.0",
        "description" : "API d'apprentissage \nLe 20/10/2025",
        "importedFrom" : "21c71288-b184-4f8b-b335-4ca824fe2db6"
      },
      "children" : [ {
        "entity" : {
          "type" : "Request",
          "id" : "980306bf-9a6f-47f3-8deb-d4f73f450388",
          "name" : "Obtenir les demandes de prêts",
          "description" : "Obtenir la liste de toutes les demandes de prêts qui vous sont accessibles",
          "uri" : {
            "host" : "${\"BaseUrl\"}",
            "path" : "/demandes"
          },
          "method" : {
            "link" : "",
            "name" : "GET"
          },
          "headers" : [ {
            "enabled" : true,
            "name" : "Authorization",
            "value" : "${\"Authentification\\\"Bearer\\\"HeaderAuthorization\"}"
          }, {
            "enabled" : true,
            "name" : "Accept",
            "value" : "application/json"
          } ],
          "headersType" : "Form"
        }
      }, {
        "entity" : {
          "type" : "Request",
          "id" : "94b3b6c1-0d36-418f-a4bf-1b246d0efa45",
          "name" : "Soumettre une demande de prêt",
          "description" : "Créer et soumettre une demande de prêt",
          "uri" : {
            "host" : "${\"BaseUrl\"}",
            "path" : "/demandes"
          },
          "method" : {
            "link" : "",
            "name" : "POST",
            "requestBody" : true
          },
          "headers" : [ {
            "enabled" : true,
            "name" : "Authorization",
            "value" : "${\"Authentification\\\"Bearer\\\"HeaderAuthorization\"}"
          }, {
            "enabled" : true,
            "name" : "Content-Type",
            "value" : "application/json"
          }, {
            "enabled" : true,
            "name" : "Accept",
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
          "id" : "85ce90d1-6d8d-4e56-bcb2-677f0a961444",
          "name" : "Obtenir une demande de prêt par ID",
          "description" : "Obtenir une demande de prêt spécifique en utilisant son ID",
          "uri" : {
            "host" : "${\"BaseUrl\"}",
            "path" : "/demandes/{idPret}"
          },
          "method" : {
            "link" : "",
            "name" : "GET"
          },
          "headers" : [ {
            "enabled" : true,
            "name" : "Authorization",
            "value" : "${\"Authentification\\\"Bearer\\\"HeaderAuthorization\"}"
          }, {
            "enabled" : true,
            "name" : "Accept",
            "value" : "application/json"
          } ],
          "headersType" : "Form"
        }
      }, {
        "entity" : {
          "type" : "Request",
          "id" : "39a75531-3a24-4d2e-a1f8-5585070172e3",
          "name" : "Mettre à jour une demande de prêt",
          "description" : "Mettre à jour une demande de prêt existante",
          "uri" : {
            "host" : "${\"BaseUrl\"}",
            "path" : "/demandes/{idPret}",
            "query" : {
              "delimiter" : "&",
              "items" : [ {
                "name" : "Demande",
                "value" : "",
                "enabled" : true
              } ]
            }
          },
          "method" : {
            "link" : "",
            "name" : "PUT"
          },
          "headers" : [ {
            "enabled" : true,
            "name" : "Authorization",
            "value" : "${\"Authentification\\\"Bearer\\\"HeaderAuthorization\"}"
          } ],
          "headersType" : "Form",
          "uriEditor" : true
        }
      }, {
        "entity" : {
          "type" : "Request",
          "id" : "d421314a-c70d-4bec-a04a-ba1f49432c1e",
          "name" : "Annuler une demande de prêt",
          "description" : "Annuler une demande de prêt existant",
          "uri" : {
            "host" : "${\"BaseUrl\"}",
            "path" : "/demandes/{idPret}"
          },
          "method" : {
            "link" : "",
            "name" : "DELETE"
          },
          "headers" : [ {
            "enabled" : true,
            "name" : "Authorization",
            "value" : "${\"Authentification\\\"Bearer\\\"HeaderAuthorization\"}"
          } ],
          "headersType" : "Form"
        }
      }, {
        "entity" : {
          "type" : "Service",
          "name" : "Entité",
          "description" : "Section regroupant les entités"
        }
      } ]
    } ],
    "environments" : [ {
      "name" : "APIPretsEP 1.0.0",
      "importedFrom" : {
        "projectId" : "21c71288-b184-4f8b-b335-4ca824fe2db6"
      },
      "variables" : {
        "272e8a1f-cb83-4715-8c32-091381fb7022" : {
          "name" : "BaseUrl",
          "value" : "https://ecckpdj69thuaik.eu.api-mocks.com",
          "enabled" : true,
          "private" : false
        },
        "433bc437-57a2-423d-a1c6-29545105cf36" : {
          "name" : "Authentification\\\"Bearer\\\"HeaderAuthorization",
          "value" : "",
          "enabled" : true,
          "private" : true
        }
      }
    } ]
  }
---
