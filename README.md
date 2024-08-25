# logicapp-formrecognizer
A reusable Logic App to infer a custom Azure Document Intelligence extraction model. This Azure Logic App is called when a pdf document is uploaded to storage account and produces a JSON file. It invokes a pre-trained custom Azure Document Intelligence extraction model in response to an Azure Event Grid event on the storage account

## Pre-requisites
- Requires a pre-trained [custom Document Intelligence extraction model] {https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/how-to-guides/build-a-custom-model?view=doc-intel-4.0.0}.
- The deployment workflow relies on secrets from a Azure Key Vault, set the key vault property enabledForTemplateDeployment to true.
- AFTER deploying the Logic App, at 'When doc is uploaded' trigger replace the existing event grid connector with a new one that uses Managed Identity authentication. Grant the Managed Identity of the Logic App EventGrid EventSubcription Contributor to the subscription.
