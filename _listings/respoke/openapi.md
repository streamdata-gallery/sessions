swagger: "2.0"
x-collection-name: Respoke
x-complete: 1
info:
  title: Respoke REST API
  description: add-live-voice-video-text-and-data-features-to-your-website-or-app-
  termsOfService: https://www.respoke.io/files/respoke-tos-20141007.pdf
  version: v1
host: api.respoke.io
basePath: v1/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  admin-sessions/:
    post:
      summary: Admin Sessions
      description: Log in with the account username and password. Get an Admin-Token.
      operationId: postAdminSessions
      x-api-path-slug: adminsessions-post
      parameters:
      - in: query
        name: password
        description: Your password
      - in: query
        name: username
        description: Your username
      responses:
        200:
          description: OK
      tags:
      - Admin
      - Sessions
  session-tokens/:
    post:
      summary: Session Tokens
      description: An end-user client posts a tokenId from POST [base]/tokens to authenticate
        to an app as endpointId.
      operationId: postSessionTokens
      x-api-path-slug: sessiontokens-post
      parameters:
      - schema:
          $ref: '#/definitions/holder'
      - in: header
        name: App-Token
        description: Your application token
      responses:
        200:
          description: OK
      tags:
      - Session
      - Tokens