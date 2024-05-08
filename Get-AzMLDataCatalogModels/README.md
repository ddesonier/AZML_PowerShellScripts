# Get-AzMLDataCatalogModels
### Function Overview
The `Get-ModelsInfoByModelName` function queries an Azure Machine Learning registry to retrieve details about models. It takes three mandatory parameters:

1. `$ResourceGroup`: Specifies the Azure resource group where the registry is located.
2. `$Registry`: Specifies the name of the Azure Machine Learning registry.
3. `$ModelArray`: An array containing model names to query.

### Function Steps
1. Retrieves a list of models from the specified registry.
2. For each model:
    - If a "latest version" exists, retrieves detailed information using the `az ml model show` command.
    - If no version information is available, adds the model to the investigation list.
3. Writes the model information to a CSV file named `models_<timestamp>.csv`.
4. Writes the investigation list to a CSV file named `investigate_<timestamp>.csv`.

### Prerequisites
Before using the `Get-ModelsInfoByModelName` function, ensure the following prerequisites are met:

1. **Azure CLI**: Make sure you have the Azure Command-Line Interface (CLI) installed on your system. You can download it from the official Azure CLI website: [Azure CLI Installation](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli)

2. **Azure Subscription**: You need an active Azure subscription to work with Azure resources. If you don't have one, sign up for a free Azure account: [Azure Free Account](https://azure.com/free)

3. **Resource Group and Registry**:
   - Create an Azure resource group where your Azure Machine Learning registry will reside.
   - Set up an Azure Machine Learning registry within your resource group.
   - Note the names of the resource group and registry for use as parameters in the function.

4. **Model Names**:
   - Prepare an array of model names that you want to query using the function.
   - Ensure that these model names exist in your Azure Machine Learning registry.

5. **Permissions**:
   - Ensure that you have appropriate permissions to access the specified resource group and registry.
   - You should be able to execute Azure CLI commands and retrieve model information.

### Example Usage
```powershell
Get-ModelsInfoByModelName -ResourceGroup \"myResourceGroup\" -Registry \"myRegistry\" -ModelArray @(\"Model1\", \"Model2\")
```

This example retrieves model details for the specified models in the given registry. Feel free to adapt the function to your specific use case! 😊
