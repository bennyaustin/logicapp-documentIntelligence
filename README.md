# logicapp-formrecognizer
A reusable Logic App to infer a custom Azure Document Intelligence extraction model. This Azure Logic App is called when a pdf document is uploaded to storage account and produces a JSON file. It invokes a pre-trained custom Azure Document Intelligence extraction model in response to an Azure Event Grid event on the storage account

## Pre-requisites
- Requires a pre-trained [custom Document Intelligence extraction model] {https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/how-to-guides/build-a-custom-model?view=doc-intel-4.0.0}.
- The deployment workflow relies on secrets from a Azure Key Vault, set the key vault property enabledForTemplateDeployment to true.
- AFTER deploying the Logic App, at 'When doc is uploaded' trigger replace the existing event grid connector with a new one that uses Managed Identity authentication as shown below. Grant the Managed Identity of the Logic App EventGrid EventSubcription Contributor to the subscription.
  
<img width="317" alt="change connection" src="https://github.com/user-attachments/assets/c480dd06-d958-4917-9c94-0c194f5270a4">
<img width="318" alt="add new" src="https://github.com/user-attachments/assets/92ceba9c-a6c0-40e3-bd68-c2a5e6b1b37d">
<img width="319" alt="mi" src="https://github.com/user-attachments/assets/2c3ec5f8-36e2-4a09-8336-1873b31e11ce">
