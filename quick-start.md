# 30-Minute Quick Start

> Dive into Dify through an example app

This step-by-step tutorial will walk you through creating a multi-platform content generator from scratch.

Beyond basic LLM integration, you'll discover how to use powerful Dify nodes to orchestrate sophisticated AI applications faster with less effort.

By the end of this tutorial, you'll have a workflow that takes whatever content you throw at it (text, documents, or images), adds your preferred voice and tone, and spits out polished, platform-specific social media posts in your chosen language.

The complete workflow is shown below. Feel free to refer back to this as you build to stay on track and see how all the nodes work together.

<img src="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_workflow_overview.png?fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=286ab7e6e202f5ebe1443e2895baa66c" alt="Quick Start Workflow Overview" title="Quick Start Workflow Overview" className="mx-auto" data-og-width="2398" width="2398" data-og-height="528" height="528" data-path="images/deeper_dive_workflow_overview.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_workflow_overview.png?w=280&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=2b9cf9753de110c72f1ce6cf735f531c 280w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_workflow_overview.png?w=560&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=7aa4deeae91dc38cdb8616d440682620 560w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_workflow_overview.png?w=840&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=5e2f5c589f74a1efa9249d5706ec3e3f 840w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_workflow_overview.png?w=1100&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=81d20280ceb9ad11d7ab6871229f4485 1100w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_workflow_overview.png?w=1650&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=576d9b4d44ae2aa7e46bad851c5eb277 1650w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_workflow_overview.png?w=2500&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=4e9ea0723199c222c3e78fa03968269a 2500w" />

## Step 1: Create a New Workflow

1. Go to **Studio**, then select **Create from blank** > **Workflow**.
2. Name the workflow `Multi-platform content generator` and click **Create**. You'll automatically land on the workflow canvas to start building.

## Step 2: Add and Configure Workflow Nodes

<Note>
  Keep any unmentioned settings at their default values.
</Note>

<Tip>
  Give nodes and variables clear, descriptive names to make them easier to identify and reference in the workflow.
</Tip>

### 1. User Input Node: Collect User Inputs

<Info>
  First, we need to define what information to gather from users, such as the draft text, target platforms, desired tone, and any reference materials.

  The User Input node is where we can easily set this up. Each input field we add here becomes a variable that all downstream nodes can reference and use.
</Info>

<img src="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_start.png?fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=ddae35baddbef35eb052d756c5c90621" alt="User Input Node" title="User Input Node" className="mx-auto" style={{ width:"71%" }} data-og-width="1826" width="1826" data-og-height="838" height="838" data-path="images/deeper_dive_start.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_start.png?w=280&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=54df708079d522c902ab6153bc7606f4 280w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_start.png?w=560&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=c4a5e3fe7708ccaf4a8e10691fe2302c 560w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_start.png?w=840&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=a54233cd7c8e23d4eb54d88293d4e8a8 840w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_start.png?w=1100&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=b89385bb2ee136d6eddaf84d952bc7b5 1100w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_start.png?w=1650&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=4218f821556c80d0b9ea56b9dc4390fe 1650w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_start.png?w=2500&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=4261d536ee50f4b706009886e59ffe27 2500w" />

Click the User Input node to open its configuration panel, then add the following input fields.

<Accordion title="Reference materials - text">
  * Field type: `Paragraph`
  * Variable Name: `draft`
  * Label Name: `Draft`
  * Max length: `2048`
  * Required: `No`
</Accordion>

<Accordion title="Reference materials - files">
  * Field type: `File list`
  * Variable Name: `user_file`
  * Label Name: `Upload File (≤ 10)`
  * Support File Types: `Document`, `Image`
  * Upload File Types: `Both`
  * Max number of uploads: `10`
  * Required: `No`
</Accordion>

<Accordion title="Voice and tone">
  * Field type: `Paragraph`
  * Variable Name: `voice_and_tone`
  * Label Name: `Voice & Tone`
  * Max length: `2048`
  * Required: `No`
</Accordion>

<Accordion title="Target platform">
  * Field type: `Short Text`
  * Variable Name: `platform`
  * Label Name: `Target Platform (≤ 10)`
  * Max length: `256`
  * Required: `Yes`
</Accordion>

<Accordion title="Language requirements">
  * Field type: `Select`
  * Variable Name: `language`
  * Label Name: `Language`
  * Options:
    * `English`
    * `日本語`
    * `简体中文`
  * Default value: `English`
  * Required: `Yes`
</Accordion>

### 2. Parameter Extractor Node: Identify Target Platforms

<Info>
  Since our platform field accepts free-form text input, users might type in various ways: `x and linkedIn`, `post on Twitter and LinkedIn`, or even `Twitter + LinkedIn please`. However, we need a clean and structured list, like `["Twitter", "LinkedIn"]`, that downstream nodes can work with reliably.

  This is the perfect job for the Parameter Extractor node. It uses an LLM to analyze users' natural language, recognize all these variations, and output a standardized array.
</Info>

<img src="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_paramater_extractor.png?fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=b86eaa344ab8b999fe3902b037926cad" alt="Paramater Extractor" title="Paramater Extractor" className="mx-auto" style={{ width:"73%" }} data-og-width="1594" width="1594" data-og-height="1144" height="1144" data-path="images/deeper_dive_paramater_extractor.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_paramater_extractor.png?w=280&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=4f038950160d0e6184782f32c23e5524 280w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_paramater_extractor.png?w=560&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=29c03f46b91f333642070b133b164d75 560w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_paramater_extractor.png?w=840&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=1db6790c5a00787f2d43cc854bbbbbf4 840w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_paramater_extractor.png?w=1100&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=20286f4a4b76ef1022b30844cad6267f 1100w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_paramater_extractor.png?w=1650&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=1a0bd156eb83b7c5f3b4e2733d008d34 1650w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_paramater_extractor.png?w=2500&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=3cef1b47371e40ad1057a52bcc331bcd 2500w" />

After the User Input node, add a Parameter Extractor node and configure it:

1. Choose a model.
2. Set `User Input/platform` as the input variable.
3. Add an extract parameter:
   1. Name: `platform`
   2. Type: `Array[String]`
   3. Description: `Identify and extract the platform(s) for which the user wants to create tailored content.`
   4. Required: `Yes`
4. In the instruction field, paste the following to guide the LLM in parameter extraction:

   ```markdown INSTRUCTION theme={null}
   # TASK DESCRIPTION
   Parse platform names from input and output as a JSON array.

   ## PROCESSING RULES
   - Support multiple delimiters: commas, semicolons, spaces, line breaks, "and", "&", "|", etc.
   - Standardize common platform name variants (twitter/X→Twitter, insta→Instagram, etc.)
   - Remove duplicates and invalid entries
   - Preserve unknown but reasonable platform names

   ## OUTPUT REQUIREMENTS
   - Success: ["Platform1", "Platform2"] 
   - No platforms found: [No platforms identified. Please enter a valid platform name.]

   ## EXAMPLES
   - Input: "twitter, linkedin" → ["Twitter", "LinkedIn"]
   - Input: "x and insta" → ["Twitter", "Instagram"]
   - Input: "invalid content" → [No platforms identified. Please enter a valid platform name.]
   ```

   <Check>
     Note that we've instructed the LLM to output a specific error message for invalid inputs, which will serve as the end trigger for our workflow in the next step.
   </Check>

### 3. IF/ELSE Node: Validate Platform Extraction Results

<Info>
  What if a user enters an invalid platform name, like `ohhhhhh` or `BookFace`? We don't want to waste time and tokens generating useless content.

  In such cases, we can use an IF/ELSE node to create a branch that stops the workflow early. We'll set a condition that checks for the error message from the Parameter Extractor node; if that message is detected, the workflow will route directly to an Output node and end.
</Info>

<img src="https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_if.png?fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=647f8b6ccd73d4b9a56225f0e1b57145" alt="If Condition" className="mx-auto" style={{ width:"80%" }} title="If Condition" data-og-width="1450" width="1450" data-og-height="672" height="672" data-path="images/deeper_dive_if.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_if.png?w=280&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=ab236223c9c39b35c4f46f615f8745dc 280w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_if.png?w=560&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=f03b4c0921a9bcdca138a50821ffd69b 560w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_if.png?w=840&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=04e16f218e2b85cbd900f68d254c8d74 840w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_if.png?w=1100&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=0dfeecb877f5c91ea64f2cc0210c5ae4 1100w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_if.png?w=1650&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=3536332413e271bb4d47888bfb864259 1650w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_if.png?w=2500&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=bf0ee98154eef39af28d9dc18d1049c4 2500w" />

1. After the Parameter Extractor node, add an IF/ELSE node.
2. On the IF/ELSE node's panel, define the IF condition:

   **IF** `Parameter Extractor/platform` `contains`  `No platforms identified. Please enter a valid platform name.`
3. After the IF/ELSE node, add an Output node to the IF branch.
4. On the Output node's panel, set `Parameter Extractor/platform` as the output variable.

### 4. List Operator Node: Separate Uploaded Files by Type

<Info>
  Our users can upload both images and documents as reference materials, but these two types require different handling: images can be interpreted directly by vision-enabled models, while documents must first be converted to text for an LLM to understand their content.

  To manage this, we'll use two List Operator nodes to filter and split the uploaded files into separate branches—one for images and one for documents.
</Info>

<img src="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_list_operator.png?fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=28642336cd55ab13dcabb9a806e9c457" alt="List Operator" className="mx-auto" style={{ width:"70%" }} title="List Operator" data-og-width="1526" width="1526" data-og-height="1200" height="1200" data-path="images/deeper_dive_list_operator.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_list_operator.png?w=280&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=41f57f4a1f9d684abe0ade7ed8f0fdae 280w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_list_operator.png?w=560&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=6ef8a0f3178d73e7813fb625fd519bff 560w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_list_operator.png?w=840&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=9d55dd879a63f8c23e4ff6f676d7cb68 840w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_list_operator.png?w=1100&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=47e98a2ad6ab95e3df1dc1fc8e9e9980 1100w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_list_operator.png?w=1650&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=62747b2cbb6ad95d5189c83ed38f16ee 1650w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_list_operator.png?w=2500&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=979b9fdd1714f3243d33139c3527a3f3 2500w" />

1. After the IF/ELSE node, add two List Operator nodes to the ELSE branch.
2. Rename one node to `Image` and the other to `Document`.
3. Configure the Image node:
   1. Set `User Input/user_file` as the input variable.
   2. Enable the filter condition: `{x}type` `in` `Image`
4. Configure the Document node:
   1. Set `User Input/user_file` as the input variable.
   2. Enable the filter condition: `{x}type` `in` `Doc`.

### 5. Doc Extractor Node: Extract Text from Documents

<Info>
  LLMs can't directly read uploaded files like PDF or DOCX. To use the information in these documents, we must first convert them into plain text that LLMs can process.

  This is exactly what a Doc Extractor node does. It takes document files as input and outputs clean, usable text for the next steps.
</Info>

1. After the Document node, add a Doc Extractor node.
2. On the Doc Extractor node's panel, set `Document/result` as the input variable.

### 6. LLM Node: Integrate All Reference Materials

<Info>
  When users provide multiple reference types—draft text, documents, and images—simultaneously, we need to consolidate them into a single, coherent summary.

  An LLM node will handle this task by analyzing all the scattered pieces to create a comprehensive context that guides subsequent content generation.
</Info>

<img src="https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_info_integrate.png?fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=88017b2fb2af34da3e8a7399748bf999" alt="Integrate Information" className="mx-auto" style={{ width:"78%" }} title="Integrate Information" data-og-width="2018" width="2018" data-og-height="610" height="610" data-path="images/deeper_dive_info_integrate.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_info_integrate.png?w=280&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=c011b169050a552cfc5734afc0687af1 280w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_info_integrate.png?w=560&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=dba5fbd416dcccda545649b7a07c9888 560w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_info_integrate.png?w=840&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=8e331aabfd065720d8711fa1c61cc31b 840w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_info_integrate.png?w=1100&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=dfeeb99dbf398bc0cadc0c82b8ce6ae0 1100w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_info_integrate.png?w=1650&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=5e8d1d95b9dce5b3af702b1c5a8e3948 1650w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_info_integrate.png?w=2500&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=3dc74825a041526d22c75764897326ad 2500w" />

1. After the Doc Extractor node, add an LLM node.
2. Connect the Image node to this LLM node as well.
3. Click the LLM node to configure it:
   1. Rename it to `Integrate Info`.
   2. Choose a model that supports vision (indicated by an eye icon).
   3. Enable **VISION** and set `Image/result` as the vision variable.
   4. In the system prompt field, paste the following:

      <Warning>
        In the prompt, to reference the `Doc Extractor/text` and `User Input/draft` variables in *PROVIDED MATERIALS*, type `{` or `/` and select from the list.

        <img src="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_reference_variable.png?fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=118f127f048c3e71a1776383f032edba" alt="Reference Variable" title="Reference Variable" className="mx-auto" style={{ width:"58%" }} data-og-width="732" width="732" data-og-height="294" height="294" data-path="images/deeper_dive_reference_variable.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_reference_variable.png?w=280&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=6a68e655c0184762da08645dc5233e84 280w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_reference_variable.png?w=560&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=0efcd52bbfe0a3a4c851b58c6785095c 560w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_reference_variable.png?w=840&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=07bc083ba6601f3eab866f01726cfbfc 840w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_reference_variable.png?w=1100&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=f6bbe588a1277e7bce330dbe34448b0a 1100w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_reference_variable.png?w=1650&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=48d2a5661af0c15002c1ed7d5676035b 1650w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_reference_variable.png?w=2500&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=0082ec8604141a015d18239ee1d273e6 2500w" />
      </Warning>

      ```markdown SYSTEM {2,3} theme={null}
      # PROVIDED MATERIALS
      Doc Extractor/text
      User Input/draft

      # ROLE & TASK
      You are a content strategist. Analyze the provided materials and create a comprehensive content foundation for multi-platform social media optimization.

      # ANALYSIS PRINCIPLES
      - Work exclusively with provided information—no external assumptions
      - Focus on extraction, synthesis, and strategic interpretation
      - Identify compelling and actionable elements
      - Prepare insights adaptable across different platforms

      # REQUIRED ANALYSIS
      Deliver structured analysis with:

      ## 1. CORE MESSAGE
      - Central theme, purpose, objective
      - Key value or benefit being communicated

      ## 2. ESSENTIAL CONTENT ELEMENTS
      - Primary topics, facts, statistics, data points
      - Notable quotes, testimonials, key statements
      - Features, benefits, characteristics mentioned
      - Dates, locations, contextual details

      ## 3. STRATEGIC INSIGHTS
      - What makes content compelling/unique
      - Emotional/rational appeals present
      - Credibility factors, proof points
      - Competitive advantages highlighted

      ## 4. ENGAGEMENT OPPORTUNITIES
      - Discussion points, questions emerging
      - Calls-to-action, next steps suggested
      - Interactive/participation opportunities
      - Trending themes touched upon

      ## 5. PLATFORM OPTIMIZATION FOUNDATION
      - High-impact: Quick, shareable formats
      - Professional: Business-focused discussions
      - Community: Interaction and sharing
      - Visual: Enhanced with strong visuals

      ## 6. SUPPORTING DETAILS
      - Metrics, numbers, quantifiable results
      - Direct quotes, testimonials
      - Technical details, specifications
      - Background context available
      ```

### 7. Iteration Node: Create Customized Content for Each Platform

<Info>
  Now that the integrated references and target platforms are ready, let's generate a tailored post for each platform using an Iteration node.

  The node will loop through the list of platforms and run a sub-workflow for each: first analyze the specific platform's style guidelines and best practices, then generate optimized content based on all available information.
</Info>

<img src="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_integration.png?fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=0dff1462d9ab58d4ed66453b5d51a15c" alt="Iteration Node" className="mx-auto" style={{ width:"62%" }} title="Iteration Node" data-og-width="1116" width="1116" data-og-height="798" height="798" data-path="images/deeper_dive_integration.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_integration.png?w=280&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=c6fb9955fb85b117a020c9122b93f18d 280w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_integration.png?w=560&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=8c237459013e04ee34171194148ee2bd 560w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_integration.png?w=840&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=02b79e202296a65afcb0c9546f55aaa5 840w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_integration.png?w=1100&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=d757e8ee0352f6be3acd573aeb5f6a07 1100w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_integration.png?w=1650&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=7a6440cf6c50de15087d54d49b84c0cb 1650w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_integration.png?w=2500&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=dab98c2d9db5862c99d99a96b4ce440d 2500w" />

1. After the Integrate Info node, add an Iteration node.
2. Inside the Iteration node, add an LLM node and configure it:
   1. Rename it to `Identify Style`.
   2. Choose a model.
   3. In the system prompt field, paste the following:

      <Warning>
        In the prompt, to reference the `Current Iteration/item` variable in *ROLE & TASK* and *OUTPUT FORMAT EXAMPLES*, type `{` or `/` and select from the list.
      </Warning>

      ````markdown SYSTEM {2,40} theme={null}
      # ROLE & TASK
      You are a social media expert. Analyze the platform "Current Iteration/item" and provide content creation guidelines.

      # ANALYSIS REQUIRED
      For the given platform, provide:

      ## 1. PLATFORM PROFILE
      - Platform type and category
      - Target audience characteristics

      ## 2. CONTENT GUIDELINES
      - Optimal content length (characters/words)
      - Recommended tone (professional/casual/conversational)
      - Formatting best practices (line breaks, emojis, etc.)

      ## 3. ENGAGEMENT STRATEGY
      - Hashtag recommendations (quantity and style)
      - Call-to-action best practices
      - Algorithm optimization tips

      ## 4. TECHNICAL SPECS
      - Character/word limits
      - Visual content requirements
      - Special formatting needs

      ## 5. PLATFORM-SPECIFIC NOTES
      - Unique features or recent changes
      - Industry-specific considerations
      - Community engagement approaches

      # OUTPUT REQUIREMENTS
      - For recognized platforms: Provide specific guidelines
      - For unknown platforms: Base recommendations on similar platforms
      - Focus on actionable, practical advice
      - Be concise but comprehensive

      # OUTPUT FORMAT EXAMPLES
      ```json  
      {  
        "platform_name": "Current Iteration/item",  
        "platform_type": "social_media/professional_network/visual_platform/microblogging",  
        "content_guidelines": {  
          "max_length": "character/word limit",  
          "optimal_length": "recommended range",  
          "tone": "professional/casual/conversational/authoritative",  
          "hashtag_strategy": "quantity and placement guidelines",  
          "formatting": "line breaks, emojis, mentions guidelines",  
          "engagement_focus": "comments/shares/likes/retweets",  
          "call_to_action": "appropriate CTA style"  
        },  
        "special_considerations": "Any unique platform requirements or recent changes",  
        "confidence_level": "high/medium/low based on platform recognition"  
      }
      ````
3. After the Identity Style node, add another LLM node and configure it:
   1. Rename it to `Create Content`.
   2. Choose a model.
   3. In the system prompt field, paste the following:

      <Warning>
        In the prompt, to reference the following variables, type `{` or `/` and select from the list.

        * `Identify Style/text` in *PLATFORM GUIDELINES*
        * `Integrate Info/text` in *SOURCE INFORMATION*
        * `User Input/voice_and_tone` in *VOICE & TONE (OPTIONAL)*
        * `User Input/language` in *LANGUAGE REQUIREMENT*
      </Warning>

      ```markdown SYSTEM {6,9,12,15} theme={null}
      # ROLE & TASK
      You are an expert social media content creator. Generate publication-ready content that matches platform guidelines, incorporates source information, and follows specified voice/tone and language requirements.

      # INPUT MATERIALS
      ## 1. PLATFORM GUIDELINES
      Identify Style/text

      ## 2. SOURCE INFORMATION
      Integrate Info/text

      ## 3. VOICE & TONE (OPTIONAL)
      User Input/voice_and_tone

      ## 4. LANGUAGE REQUIREMENT
      - Generate ALL content exclusively in: User Input/language
      - No mixing of languages whatsoever
      - Adapt platform terminology to the specified language

      # CONTENT REQUIREMENTS
      - Follow platform guidelines exactly (format, length, tone, hashtags)
      - Integrate source information effectively (key messages, data, value props)
      - Apply voice & tone consistently (if provided)
      - Optimize for platform-specific engagement
      - Ensure cultural appropriateness for the specified language

      # OUTPUT FORMAT
      - Generate ONLY the final social media post content. No explanations or meta-commentary. Content must be immediately copy-paste ready.
      - Maximum heading level: ## (H2) - never use # (H1)
      - No horizontal dividers: avoid ---

      # QUALITY CHECKLIST
      ✅ Platform guidelines followed
      ✅ Source information integrated  
      ✅ Voice/tone consistent (when provided)
      ✅ Language consistency maintained
      ✅ Engagement optimized
      ✅ Publication ready
      ```
   4. Enable structured output.

      <img src="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_structured_output.png?fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=d3e6871fdcf97442e7c937cba3f3a93b" alt="Structured Output" title="Structured Output" className="mx-auto" style={{ width:"64%" }} data-og-width="764" width="764" data-og-height="480" height="480" data-path="images/deeper_dive_structured_output.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_structured_output.png?w=280&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=eba71d3e2282210d3dfeb8937a28c983 280w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_structured_output.png?w=560&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=b6ad06f1c139f1a7e78f019e582738c2 560w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_structured_output.png?w=840&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=9e3cd9b5049c8ee56760d1e28cdd451c 840w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_structured_output.png?w=1100&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=679a761af013908b83314493b9223fa0 1100w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_structured_output.png?w=1650&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=e8747ddc2c9338b64a924448c9660e0d 1650w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_structured_output.png?w=2500&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=b8911341c9ee189f2fd98314fedb04d2 2500w" />

      1. Next to **OUTPUT VARIABLES**, toggle **STRUCTURED** on. The structured\_output variable will appear below.
      2. Next to **structured\_output**, click **Configure**.
      3. In the pop-up schema editor, click **Import From JSON** in the top-right corner, and paste the following:

         ```json  theme={null}
         {   
           "platform_name": "string",
           "post_content": "string"   
         }
         ```
4. Click the Iteration node to configure it:
   1. Set `Parameter Extractor/platform` as the input variable.
   2. Set `Create Content/structured_output` as the output variable.
   3. Enable **PARALLEL MODE** and set the maximum parallelism to `10`.

      <Check>
        This is why we included `(≤10)` in the label name for the target platform field back in the User Input node.
      </Check>

### 8. Template Node: Format the Final Output

<Info>
  The Iteration node generates a post for each platform, but its output is a raw array of data (e.g., `[{"platform_name": "Twitter", "post_content": "..."}]`) that isn't very readable. We need to present the results in a clearer format.

  That's where the Template node comes in—it allows us to format this raw data into well-organized text using [Jinja2](https://jinja.palletsprojects.com/en/stable/) templating, ensuring the final output is user-friendly and easy to understand.
</Info>

<img src="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_template.png?fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=b206c68c0e6cc7607c3ca0d725f66a9b" alt="Template Node" title="Template Node" style={{ width:"49%" }} className="mx-auto" data-og-width="794" width="794" data-og-height="896" height="896" data-path="images/deeper_dive_template.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_template.png?w=280&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=97893b99520ac2979dd34e40de192785 280w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_template.png?w=560&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=d83c8d44b9cbb7652e35499903efac67 560w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_template.png?w=840&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=22692a4596f8825dad989bd933eb1613 840w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_template.png?w=1100&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=62854ce66532c1bc55f3f2c3cf52e329 1100w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_template.png?w=1650&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=4fefd8a114ebcc2d4cbf915226f7de20 1650w, https://mintcdn.com/dify-6c0370d8/6mOfaeljpmK9sOmc/images/deeper_dive_template.png?w=2500&fit=max&auto=format&n=6mOfaeljpmK9sOmc&q=85&s=edbc6826b0972d44606e90b9c7d0a3a9 2500w" />

1. After the Iteration node, add a Template node.
2. On the Template node's panel, set `Iteration/output` as the input variable.
3. Paste the following Jinja2 code (**remember to delete the comments**).

   ```
   {% for item in output %}        # Loop through each platform-content pair in the input array
   # 📱 {{ item.platform_name }}   # Display the platform name as an H1 heading with a phone emoji
   {{ item.post_content }}        # Display the generated content for this platform
                                  # Add a blank line between platforms for better readability
   {% endfor %}                   # End the loop
   ```

   <Tip>
     While LLMs can handle output formatting as well, their outputs can be inconsistent and unpredictable. For rule-based formatting that requires no reasoning, the Template node gets things done in a more stable and reliable way at zero token cost.

     LLMs are incredibly powerful, but knowing when to use the right tool is key to building more reliable and cost-effective AI applications.
   </Tip>

### 9. Output Node: Return the Results to Users

1. After the Template node, add an Output node.
2. On the Output node's panel, set the `Template/output` as the output variable.

## Step 3: Test

Your workflow is now complete! Let’s test it out.

1. Make sure your Checklist is clear.

   <img src="https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_checklist_clear.png?fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=150593983c6b25264911f0d31e145e86" alt="Check Clecklist" className="mx-auto" style={{ width:"77%" }} title="Check Clecklist" data-og-width="878" width="878" data-og-height="446" height="446" data-path="images/deeper_dive_checklist_clear.png" data-optimize="true" data-opv="3" srcset="https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_checklist_clear.png?w=280&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=3ee9ef3967497e917a2aa32f428150f3 280w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_checklist_clear.png?w=560&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=22535f37d19fea8ec1a8e7f549eca87f 560w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_checklist_clear.png?w=840&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=68a235dcc68caa78cccabf4f7ad50fa9 840w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_checklist_clear.png?w=1100&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=d1ba773a108fce52d983d075816e8330 1100w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_checklist_clear.png?w=1650&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=03ed9fd307f1b524a0d479b3b36fed71 1650w, https://mintcdn.com/dify-6c0370d8/pukb9aJrVFLyeNW1/images/deeper_dive_checklist_clear.png?w=2500&fit=max&auto=format&n=pukb9aJrVFLyeNW1&q=85&s=312869dd0437c89253be5294bc620f3f 2500w" />
2. Check your workflow against the reference diagram provided at the beginning to ensure all nodes and connections match.
3. Click **Test Run** in the top-right corner, fill in the input fields, then click **Start Run**.

   To run a single node with cached inputs, click the **Run this step** icon at the top of its configuration panel.

   <Tip>
     To test how a node reacts to different inputs from previous nodes, you don't need to re-run the entire workflow. Just click **View cached variables** at the bottom of the canvas, find the variable you want to change from the list, and edit its value.
   </Tip>

   If you encounter any errors, check the **LAST RUN** logs of the corresponding node to identify the exact cause of the problem.

## Step 4: Publish & Share

Once the workflow runs as expected and you're happy with the results, click **Publish** > **Publish Update** to make it live and shareable.

<Warning>
  If you make any changes later, always remember to publish again so the updates take effect.
</Warning>

<Tip>
  After publishing, you can run a quick end-to-end test in the live environment to confirm that everything works the same as in **Studio**.
</Tip>


---

> To find navigation and other pages in this documentation, fetch the llms.txt file at: https://docs.dify.ai/llms.txt