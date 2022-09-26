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


## ⚙️ Setup

In this section you will learn how to set-up and configure an AzureML Managed Spark cluster in your AzureML workspace. 



## 🎓 Learn

Below are some sample notebooks:

- ...

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
