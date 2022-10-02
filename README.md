# Azure Machine Learning Responsible AI Tools in Private Preview
This is a repository that holds information about the private previews of Azure Machine Learning's Responsible AI and model evaluations tools.

Implementing Responsible AI in practice requires rigorous engineering. But rigorous engineering can be tedious, manual, and time-consuming without the right tooling and infrastructure. Azure Machine Learning provides a comprehensive dashboard, called Responsible AI dashboard,to help you implement Responsible AI in practice effectively and efficiently. It brings together several mature model assessment and understanding tools in the areas of model performance analysis, error analysis, data exploration, model interpretability, model fairness assessment, and what-if perturbation and counterfactual analysis.

Please see [this concept doc](https://learn.microsoft.com/en-us/azure/machine-learning/concept-responsible-ai-dashboard) to learn more about the model assessment tools supported within the Responsible AI dashboard.


## Currently in Private Preview (HERE)

**private preview**|**description**
-|-
Responsible AI dashboard for text data|Assess and understand your NLP models, currently supporting text multi-class classification scenarios.
Responsible AI dashboard for image data|Assess and understand your NLP models, currently supporting image multi-class classification scenarios.
## Currently in Public Preview

**public preview**|**description**
-|-
[Responsible AI dashboard for tabular data](https://learn.microsoft.com/en-us/azure/machine-learning/concept-responsible-ai-dashboard)|Responsible AI dashboard supporting regression and classification models trained on tabular data. Please see how you can generate a dashboard [via Azure ML's SDK/CLI](https://learn.microsoft.com/en-us/azure/machine-learning/how-to-responsible-ai-dashboard-sdk-cli?tabs=yaml) or via [Azure ML studio UI](https://learn.microsoft.com/en-us/azure/machine-learning/how-to-responsible-ai-dashboard).
[Responsible AI scorecard for tabular data](https://learn.microsoft.com/en-us/azure/machine-learning/how-to-responsible-ai-scorecard)|Responsible AI scorecard is a PDF report you can easily configure, generate, download, and share with your technical and non-technical stakeholders to educate them about your data and model health and compliance, and to help build trust. You can also use the scorecard in audit reviews to inform the stakeholders about the characteristics of your model.

## ❗Important

**Features contained in this repository are in private preview. Preview versions are provided without a service level agreement, and they are not recommended for production workloads. Certain features might not be supported or might have constrained capabilities. For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/en-us/support/legal/preview-supplemental-terms/).**

## Prerequisites

1. An Azure subscription. If you don't have an Azure subscription, [create a free account](https://aka.ms/AMLFree) before you begin.
2. A terminal. [Install and set up the CLI (v2)](https://docs.microsoft.com/azure/machine-learning/how-to-configure-cli) before you begin.



## 👋 Introduction

The Responsible AI dashboard is a single pane of glass bringing together, in a comprehensive view, various new and pre-existing tools for model assessment and debugging. The dashboard integrates these tools with [Azure Machine Learning CLI v2, Azure Machine Learning Python SDK v2](concept-v2.md), and [Azure Machine Learning studio](overview-what-is-machine-learning-studio.md). The components covered in the Responsible AI dashboard include:  

- Data explorer, to understand and explore your dataset distributions and statistics.
- Model overview and fairness assessment, to evaluate the performance of your model and evaluate your model's overall fairness issues (how your model's predictions affect diverse groups of people).
- Error analysis, to view and understand how errors are distributed in your dataset.  
- Model interpretability, to understand your model's predictions and how those overall and individual predictions are made.
- Counterfactual what-if, to observe how feature perturbations would affect your model predictions.

While our Responsible AI dashboard supporting tabular data scenarios (classification and regression models trained on tabular data) is currently in public preview in Azure Machine Learning, we have expanded the dashboard to be able to debug text and image classification scenarios. The dashboard currently covers multi-class classification scenarios on image and text data and will be expanded to include image and text multi-label and binary classification scenarios and image objection detection scenarios by early 2023. 


## ⚙️ Setup

In this section you will learn how to run one AzureML pipeline to register a model and another pipeline to create an RAI dashboard for text and image data.

In your azureml workspace, please create an AMLCompute CPU cluster called "cpucluster". This cluster will be used to run the CPU jobs submitted.

To run the DPv2 components, please first run az login:

```
az login
```

Then, we can setup an environment:

```
conda create -y -n dpv2 python=3.8
conda activate dpv2
```

We can install the azure-cli and azure-ai-ml packages to submit jobs to AzureML workspaces:

```
pip install azure-cli
pip install azure-ai-ml
```


The az extension will need to be installed using:

```
az extension add --source https://azuremlsdktestpypi.blob.core.windows.net/wheels/sdk-cli-v2/ml-latest-py3-none-any.whl --yes
```

The extension can then be updated using:

```
az extension update -n ml
```

You can also check the az extension version using:

```
az version
```

You will need to set the subscription id where you will be submitting the job to:

```
az account set -s $SubId
```

Navigate to the CLI directory in the examples folder:

```
cd examples\CLI
```

# Running DPv2 Text Components

To submit the yaml jobs, please run the training yaml first to create the model:

```
az ml job create --file test_text_pipeline_train.yaml --workspace <YOUR_WORKSPACE> --resource-group <YOUR_RESOURCE_GROUP>
```

Then you can run the RAI pipeline to create the dashboard:

```
az ml job create --file test_text_pipeline_rai.yaml --workspace <YOUR_WORKSPACE> --resource-group <YOUR_RESOURCE_GROUP>
```

# Running DPv2 Vision Components

To submit the yaml jobs, please run the training yaml first to create the model:

```
az ml job create --file test_vision_pipeline_train.yaml --workspace <YOUR_WORKSPACE> --resource-group <YOUR_RESOURCE_GROUP>
```

Then you can run the RAI pipeline to create the dashboard:

```
az ml job create --file test_vision_pipeline_rai.yaml --workspace <YOUR_WORKSPACE> --resource-group <YOUR_RESOURCE_GROUP>
```

## 🎓 Learn

Below are some sample notebooks:

- Coming soon! Please use the instructions above to generate the RAI dashboard with the sample YAML files provided in this repository.

## 🛣️ Coming soon

⭐ Support for text multi-label and binary classification models.<br>
⭐ Support for image multi-label and binary classification models.<br>
⭐ Support for image object detections models.<br>
⭐ AutoML Computer Vision and AutoML NLP integrations.<br>


## ✉️ Feedback and Support
If you have feedback or require support during this private preview, please send us an [email](mailto:mesameki@microsoft.com).

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
