# Next Suggested Questions

> Get next questions suggestions for the current message.



## OpenAPI

````yaml en/api-reference/openapi_chatflow.json get /messages/{message_id}/suggested
openapi: 3.0.1
info:
  title: Advanced Chat App API
  description: >-
    Chat applications support session persistence, allowing previous chat
    history to be used as context for responses. This can be applicable for
    chatbot, customer service AI, etc. This version includes advanced features
    like workflow events and more detailed file type support.
  version: 1.0.0
servers:
  - url: '{api_base_url}'
    description: >-
      The base URL for the Advanced Chat App API. Replace {api_base_url} with
      the actual API base URL provided for your application (e.g., from
      props.appDetail.api_base_url).
    variables:
      api_base_url:
        default: https://api.dify.ai/v1
        description: Actual base URL of the API
security:
  - ApiKeyAuth: []
tags:
  - name: Chatflow
    description: Advanced chat operations with workflow events.
  - name: Files
    description: File upload and preview operations for advanced chat.
  - name: Feedback
    description: User feedback operations for advanced chat.
  - name: Conversations
    description: Conversation management for advanced chat.
  - name: TTS
    description: Speech and Text conversion for advanced chat.
  - name: Application
    description: Application settings and info for advanced chat.
  - name: Annotations
    description: Annotation management for advanced chat.
paths:
  /messages/{message_id}/suggested:
    get:
      tags:
        - Chatflow
      summary: Next Suggested Questions
      description: Get next questions suggestions for the current message.
      operationId: getAdvancedSuggestedQuestions
      parameters:
        - name: message_id
          in: path
          required: true
          description: Message ID.
          schema:
            type: string
        - $ref: '#/components/parameters/UserQueryParam'
      responses:
        '200':
          description: Successfully retrieved suggested questions.
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuggestedQuestionsResponse'
components:
  parameters:
    UserQueryParam:
      name: user
      in: query
      required: true
      description: >-
        User identifier. **Note**: The Service API does not share conversations
        created by the WebApp. Conversations created through the API are
        isolated from those created in the WebApp interface.
      schema:
        type: string
  schemas:
    SuggestedQuestionsResponse:
      type: object
      properties:
        result:
          type: string
          example: success
        data:
          type: array
          items:
            type: string
  securitySchemes:
    ApiKeyAuth:
      type: http
      scheme: bearer
      bearerFormat: API_KEY
      description: API Key authentication.

````

---

> To find navigation and other pages in this documentation, fetch the llms.txt file at: https://docs.dify.ai/llms.txt