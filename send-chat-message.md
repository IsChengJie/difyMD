# Send Chat Message

> Send a request to the advanced chat application, supporting various file types and workflow events.



## OpenAPI

````yaml en/api-reference/openapi_chatflow.json post /chat-messages
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
  /chat-messages:
    post:
      tags:
        - Chatflow
      summary: Send Chat Message
      description: >-
        Send a request to the advanced chat application, supporting various file
        types and workflow events.
      operationId: sendAdvancedChatMessage
      requestBody:
        description: Request body to send an advanced chat message.
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/AdvancedChatRequest'
            examples:
              streaming_with_file_and_workflow:
                summary: Streaming mode example with image file
                value:
                  inputs:
                    user_name: Alice
                  query: Analyze this document and tell me its sentiment.
                  response_mode: streaming
                  conversation_id: conv_12345
                  user: user_alice
                  files:
                    - type: document
                      transfer_method: remote_url
                      url: https://example.com/mydoc.pdf
                  auto_generate_name: true
      responses:
        '200':
          description: >-
            Successful response. The content type and structure depend on the
            `response_mode`.

            - `blocking`: `application/json` with `ChatCompletionResponse`.

            - `streaming`: `text/event-stream` with `ChunkAdvancedChatEvent`
            stream.
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ChatCompletionResponse'
            text/event-stream:
              schema:
                type: string
                description: >-
                  A stream of Server-Sent Events. See `ChunkAdvancedChatEvent`
                  for structures.
              examples:
                workflow_events_example:
                  summary: Example stream including workflow events
                  value: >+
                    data: {"event": "workflow_started", "task_id": "task_abc",
                    "workflow_run_id": "wf_run_1", "data": {"id": "wf_run_1",
                    "workflow_id": "wf_def_xyz", "sequence_number": 1,
                    "created_at": 1705395332}}


                    data: {"event": "node_started", "task_id": "task_abc",
                    "workflow_run_id": "wf_run_1", "data": {"id": "node_run_1",
                    "node_id": "node_start", "node_type": "start", "title":
                    "Start Node", "index": 0, "inputs": {}, "created_at":
                    1705395333}}


                    data: {"event": "message", "task_id": "task_abc",
                    "message_id": "msg_123", "conversation_id": "conv_123",
                    "answer": "Processing... ", "created_at": 1705395334}


                    data: {"event": "node_finished", "task_id": "task_abc",
                    "workflow_run_id": "wf_run_1", "data": {"id": "node_run_1",
                    "node_id": "node_start", "node_type": "start", "title":
                    "Start Node", "index": 0, "status": "succeeded",
                    "elapsed_time": 0.5, "created_at": 1705395333}}


                    data: {"event": "message_end", "task_id": "task_abc",
                    "message_id": "msg_123", "conversation_id": "conv_123",
                    "metadata": {"usage": {"total_tokens": 10}}}


                    data: {"event": "workflow_finished", "task_id": "task_abc",
                    "workflow_run_id": "wf_run_1", "data": {"id": "wf_run_1",
                    "workflow_id": "wf_def_xyz", "status": "succeeded",
                    "elapsed_time": 2.5, "total_tokens": 150, "total_steps": 3,
                    "created_at": 1705395332, "finished_at": 1705395335}}

        '400':
          $ref: '#/components/responses/BadRequestGeneric'
        '404':
          $ref: '#/components/responses/ConversationNotFound'
        '500':
          $ref: '#/components/responses/InternalServerError'
components:
  schemas:
    AdvancedChatRequest:
      type: object
      required:
        - query
        - user
      properties:
        query:
          type: string
          description: User input/question content.
        inputs:
          type: object
          description: >-
            Key/value pairs for app variables. For file type variables, value
            should be an InputFileObject.
          additionalProperties:
            oneOf:
              - type: string
              - type: number
              - type: boolean
              - $ref: '#/components/schemas/InputFileObjectAdvanced'
          default: {}
        response_mode:
          type: string
          enum:
            - streaming
            - blocking
          default: streaming
          description: Response mode. Cloudflare timeout is 100s for blocking.
        user:
          type: string
          description: >-
            User identifier. **Note**: The Service API does not share
            conversations created by the WebApp. Conversations created through
            the API are isolated from those created in the WebApp interface.
        conversation_id:
          type: string
          description: Conversation ID to continue.
        files:
          type: array
          items:
            $ref: '#/components/schemas/InputFileObjectAdvanced'
          description: List of files for Vision-capable models or general file input.
        auto_generate_name:
          type: boolean
          default: true
          description: Auto-generate conversation title.
    ChatCompletionResponse:
      type: object
      description: Response for blocking mode chat.
      properties:
        event:
          type: string
          example: message
        task_id:
          type: string
          format: uuid
        id:
          type: string
          format: uuid
          description: Unique ID of this response event.
        message_id:
          type: string
          format: uuid
        conversation_id:
          type: string
          format: uuid
        mode:
          type: string
          example: chat
        answer:
          type: string
        metadata:
          $ref: '#/components/schemas/ResponseMetadata'
        created_at:
          type: integer
          format: int64
    InputFileObjectAdvanced:
      type: object
      required:
        - type
        - transfer_method
      properties:
        type:
          type: string
          enum:
            - document
            - image
            - audio
            - video
            - custom
          description: >-
            Type of the file. 'document' covers TXT, MD, PDF, HTML, XLSX, DOCX,
            CSV, EML, MSG, PPTX, XML, EPUB. 'image' covers JPG, PNG, GIF, WEBP,
            SVG. 'audio' covers MP3, M4A, WAV, WEBM, AMR. 'video' covers MP4,
            MOV, MPEG, MPGA.
        transfer_method:
          type: string
          enum:
            - remote_url
            - local_file
          description: >-
            Transfer method, `remote_url` for file URL / `local_file` for file
            upload
        url:
          type: string
          format: url
          description: File URL (when the transfer method is `remote_url`)
        upload_file_id:
          type: string
          description: >-
            Uploaded file ID, which must be obtained by uploading through the
            File Upload API in advance (when the transfer method is
            `local_file`)
      anyOf:
        - properties:
            transfer_method:
              enum:
                - remote_url
            url:
              type: string
              format: url
          required:
            - url
          not:
            required:
              - upload_file_id
        - properties:
            transfer_method:
              enum:
                - local_file
            upload_file_id:
              type: string
          required:
            - upload_file_id
          not:
            required:
              - url
      example:
        type: image
        transfer_method: remote_url
        url: https://example.com/image.png
    ResponseMetadata:
      type: object
      properties:
        usage:
          $ref: '#/components/schemas/Usage'
        retriever_resources:
          type: array
          items:
            $ref: '#/components/schemas/RetrieverResource'
    ErrorResponse:
      type: object
      properties:
        status:
          type: integer
          nullable: true
        code:
          type: string
          nullable: true
        message:
          type: string
    Usage:
      type: object
      properties:
        prompt_tokens:
          type: integer
        prompt_unit_price:
          type: string
        prompt_price_unit:
          type: string
        prompt_price:
          type: string
        completion_tokens:
          type: integer
        completion_unit_price:
          type: string
        completion_price_unit:
          type: string
        completion_price:
          type: string
        total_tokens:
          type: integer
        total_price:
          type: string
        currency:
          type: string
        latency:
          type: number
          format: double
    RetrieverResource:
      type: object
      properties:
        position:
          type: integer
        dataset_id:
          type: string
          format: uuid
        dataset_name:
          type: string
        document_id:
          type: string
          format: uuid
        document_name:
          type: string
        segment_id:
          type: string
          format: uuid
        score:
          type: number
          format: float
        content:
          type: string
  responses:
    BadRequestGeneric:
      description: Bad Request. Check parameters.
      content:
        application/json:
          schema:
            $ref: '#/components/schemas/ErrorResponse'
    ConversationNotFound:
      description: Conversation not found.
      content:
        application/json:
          schema:
            $ref: '#/components/schemas/ErrorResponse'
    InternalServerError:
      description: Internal server error.
      content:
        application/json:
          schema:
            $ref: '#/components/schemas/ErrorResponse'
  securitySchemes:
    ApiKeyAuth:
      type: http
      scheme: bearer
      bearerFormat: API_KEY
      description: API Key authentication.

````

---

> To find navigation and other pages in this documentation, fetch the llms.txt file at: https://docs.dify.ai/llms.txt