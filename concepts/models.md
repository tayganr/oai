# Azure OpenAI Models

## :loudspeaker: Introduction

With the Azure OpenAI service, you can access various models that have different features and costs. You can also adjust the original base models slightly to suit your needs better with fine-tuning.

## :computer: REST API (Inference)

URL: https://your-resource-name.openai.azure.com/openai

| API | Endpoint | Description |
| -- | -- | -- |
| Completions | /deployments/`{deployment-id}`/completions | Creates a completion for the provided prompt, parameters and chosen model. |
| Chat Completions | /deployments/`{deployment-id}`/chat/completions | Creates a completion for the chat message. |
| Embeddings | /deployments/`{deployment-id}`/embeddings | Get a vector representation of a given input that can be easily consumed by machine learning models and algorithms. |

Swagger Files

* [inference/stable/2022-12-01](https://github.com/Azure/azure-rest-api-specs/blob/main/specification/cognitiveservices/data-plane/AzureOpenAI/inference/stable/2022-12-01/inference.json)
* [inference/preview/2023-03-15-preview](https://github.com/Azure/azure-rest-api-specs/blob/main/specification/cognitiveservices/data-plane/AzureOpenAI/inference/preview/2023-03-15-preview/inference.json)
* [authoring/stable/2022-12-01](https://github.com/Azure/azure-rest-api-specs/blob/main/specification/cognitiveservices/data-plane/AzureOpenAI/authoring/stable/2022-12-01/azureopenai.json)
* [authoring/preview/2023-03-15-preview](https://github.com/Azure/azure-rest-api-specs/blob/main/specification/cognitiveservices/data-plane/AzureOpenAI/authoring/preview/2023-03-15-preview/azureopenai.json)

## :rocket: Model Summary

| Model | Version | Max Tokens | Completions | Chat Completions | Embeddings
| -- | -- | -- | -- | -- | -- |
| gpt-35-turbo | 0301 | 4,096 | ✅ | ✅ | |
| gpt-4 | 0314 | 8,192 | | ✅ | |
| gpt-4-32k | 0314 | 32,768 | | ✅ | |
| text-embedding-ada-002 | 2 | 8,191 | | | ✅ |

> Things to note:
>
> * When deciding between models such as `text-davinci-003` and `gpt-35-turbo`, it is important to consider that GPT 3.5 is optimised for chat and comes in at 1/10th the cost. Also, while `gpt-35-turbo` is optimised for chat, it works very well for traditional completion tasks, therefore `gpt-35-turbo` is generally recommended over the standard models because of its lower cost. For more information, see [OpenAI Models](https://platform.openai.com/docs/models/overview).
> * As of March 2023, OpenAI deprecated Codex models (e.g. `code-cushman-001` and `code-davinci-002`) with the community guided towards the Chat Completion API's such as `gpt-35-turbo` and `gpt-4`. For more details, see OpenAI guide on [Code completion](https://platform.openai.com/docs/guides/code).
> * `text-embedding-ada-002` has unified and superseded previous embedding models (e.g. `text-similarity`, `text-search-query`, and `text-search-doc`). For more details, see OpenAI blog post [New and improved embedding model](https://openai.com/blog/new-and-improved-embedding-model).