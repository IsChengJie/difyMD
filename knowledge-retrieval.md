# Knowledge Retrieval

## Introduction

You can use the Knowledge Retrieval node to integrate existing knowledge bases into your Chatflows or Workflows. The node searches specific knowledge for information relevant to queries and outputs results as contextual content for use in downstream nodes (e.g., LLM).

Below is an example of using the Knowledge Retrieval node in a Chatflow:

1. The **User Input** node collects the user query.

2. The **Knowledge Retrieval** node searches the selected knowledge base(s) for content related to the user query and outputs the retrieval results.

3. The **LLM** node generates a response based on both the user query and retrieved knowledge.

4. The **Answer** node returns the LLM's response to the user.

<img src="https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/knowledge_retrieval_node_example.png?fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=1dd4654bcf879eb5cf5d18c849b93428" alt="Knowledge Retrieval Node Use Case" data-og-width="2022" width="2022" data-og-height="580" height="580" data-path="images/knowledge_retrieval_node_example.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/knowledge_retrieval_node_example.png?w=280&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=5c9aac147d9c0aa2773d92c95cac2ca7 280w, https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/knowledge_retrieval_node_example.png?w=560&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=c11591ac45a2b2b19bc349fc0b7d33f4 560w, https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/knowledge_retrieval_node_example.png?w=840&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=dcb0cbd7edf0860da59894e2e50e8471 840w, https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/knowledge_retrieval_node_example.png?w=1100&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=45cf988bf195571341646b3974238569 1100w, https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/knowledge_retrieval_node_example.png?w=1650&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=f3d82ed095bd81cd08c784f314f53711 1650w, https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/knowledge_retrieval_node_example.png?w=2500&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=0006da07581126733c506141b3c66c78 2500w" />

<Info>
  Before using the Knowledge Retrieval node, make sure at least one knowledge base is available. To learn about creating knowledge bases, see [Knowledge](/en/use-dify/knowledge/readme#create-knowledge).
</Info>

<Note>
  On Dify Cloud, knowledge retrieval operations are subject to rate limits based on the subscription plan. For more information, see [Knowledge Request Rate Limit](/en/use-dify/knowledge/knowledge-request-rate-limit).
</Note>

## Configuration

To make the Knowledge Retrieval node work properly, you need to specify:

* *What* it should search for (the query)

* *Where* it should search (the knowledge base)

* *How* to process the retrieval results (the node-level retrieval settings)

You can also use document metadata to enable filter-based searches and further improve retrieval precision.

### Specify the Query

Provide the query content that the node should search for in the selected knowledge base(s).

* **Query Text**: Select a text variable. For example, use `userinput.query` to reference user input in Chatflows, or a custom text-type user input variable in Workflows.

* **Query Images**: Select an image variable, e.g., the image(s) uploaded by the user through a User Input node, to search by image. The image size limit is 2 MB.

  <Tip>
    For self-hosted deployments, you can adjust the image size limit via the environment variable `ATTACHMENT_IMAGE_FILE_SIZE_LIMIT`.
  </Tip>

  <Info>
    The **Query Images** option is available only when at least one multimodal knowledge base are added.

    Such knowledge bases are marked with a **Vision** icon, indicating that they are using a multimodal embedding model.
  </Info>

### Select Knowledge to Search

Add one or more existing knowledge bases for the node to search for content relevant to the query content.

When multiple knowledge bases are added, knowledge is first retrieved from all of them simultaneously, then combined and processed according to the [node-level retrieval settings](#configure-node-level-retrieval-settings).

<Info>
  Knowledge bases marked with a **Vision** icon support cross-modal retrieval—retrieving both text and images based on semantic relevance.
</Info>

<Tip>
  Click the **Edit** icon next to any added knowledge base to modify its settings directly within the Knowledge Retrieval node.

  To learn more about these settings, see [Manage Knowledge Settings](/en/use-dify/knowledge/manage-knowledge/introduction).
</Tip>

### Configure Node-Level Retrieval Settings

Further fine-tune how the node processes retrieval results after they are fetched from the knowledge base(s).

<Info>
  There are two layers of retrieval settings—the knowledge base level and the knowledge retrieval node level.

  Think of them as two consecutive filters: the knowledge base settings determine the initial pool of results, and the node settings further rerank the results or narrow down the pool.
</Info>

* **Rerank Settings**

  * **Weighted Score**: The relative weight between semantic similarity and keyword matching during reranking. Higher semantic weight favors meaning relevance, while higher keyword weight favors exact matches.

    <Info>
      **Weighted Score** is available only when all added knowledge bases are high-quality ones.
    </Info>

  * **Rerank Model**: The rerank model to re-score and reorder all the results based on their relevance to the query.

  <Note>
    If any multimodal knowledge bases are added, select a multimodal rerank model (marked with a **Vision** icon) as well. Otherwise, retrieved images will be excluded from reranking and the final output.
  </Note>

* **Top K**: The maximum number of top results to return after reranking. When a rerank model is selected, this value will be automatically adjusted based on the model's maximum input capacity (how much text the model can process at once).

* **Score Threshold**: The minimum similarity score for returned results. Results scoring below this threshold are excluded. Use higher thresholds for stricter relevance or lower thresholds to include broader matches.

### Enable Metadata Filtering

Use existing document metadata to restrict retrieval to specific documents within your knowledge base, improving retrieval precision.

With metadata filtering enabled, the Knowledge Retrieval node only searches documents that match the specified metadata conditions, rather than searching across the entire knowledge base. This is especially useful for targeted searching in large and diverse knowledge bases.

<Info>
  To learn more about creating and managing document metadata, see [Metadata](/en/use-dify/knowledge/metadata).
</Info>

## Output

The Knowledge Retrieval node outputs the retrieval results as a variable named `result`, which is an array of retrieved document chunks containing their content, metadata, title, and other attributes.

When the retrieval results contain image attachments, the `result` variable also includes a field named `files` containing image metadata.

## Use with LLM Nodes

To use the retrieval results as context to answer user questions in an LLM node:

1. In the **Context** field, select the `result` variable of the Knowledge Retrieval node.

2. In the prompt field, reference both the `Context` variable and the user input variable (e.g., `userinput.query` in Chatflows).

3. (Optional) If the LLM supports vision capabilities (marked with a **Vision** icon), enable **Vision** to let it interpret the retrieved images.

   <Info>
     Once **Vision** is enabled, the LLM automatically processes the retrieved images. You don't need to manually reference the `Context` variable again in the **Vision** input field.
   </Info>

<img src="https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/llm_node_configuration_example.png?fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=1987aaba02a0e2ad4559162986a68ca9" alt="LLM Node Configuration Example" width="400" data-og-width="808" data-og-height="800" data-path="images/llm_node_configuration_example.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/llm_node_configuration_example.png?w=280&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=e25e38892c451a1b3247cf1d24e538ee 280w, https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/llm_node_configuration_example.png?w=560&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=fad3d4a3e5ba3a0b5a039778b8274cf3 560w, https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/llm_node_configuration_example.png?w=840&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=7228032b285094f3f8bb0c3a3230c851 840w, https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/llm_node_configuration_example.png?w=1100&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=8d63ae57f1307292810972f0aac842be 1100w, https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/llm_node_configuration_example.png?w=1650&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=4d20246d2862bfa34541ec3fbfd84d1b 1650w, https://mintcdn.com/dify-6c0370d8/KonJEa1w7OADKBFj/images/llm_node_configuration_example.png?w=2500&fit=max&auto=format&n=KonJEa1w7OADKBFj&q=85&s=2e89b3244910175e5ce153d63991cbc5 2500w" />


---

> To find navigation and other pages in this documentation, fetch the llms.txt file at: https://docs.dify.ai/llms.txt