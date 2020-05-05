---
page_type: sample
languages:
  - csharp
name: Optimize indexing with the push API
description: In Azure Cognitive Search, you can push data from any data source to an index. In this C# sample, learn how to index more efficiently.
products:
  - azure
  - azure-cognitive-search
urlFragment: optimize-data-indexing
---

# Optimize indexing with the push API

![Flask sample MIT license badge](https://img.shields.io/badge/license-MIT-green.svg)

Azure Cognitive Search supports [two basic approaches](https://docs.microsoft.com/azure/search/search-what-is-data-import) for importing data into a search index: *pushing* your data into the index programmatically, or pointing an [Azure Cognitive Search indexer](https://docs.microsoft.com/azure/search/search-indexer-overview) at a supported data source to *pull* in the data.

This .NET Core console app builds off of the code used in the [Quickstart](https://docs.microsoft.com/azure/search/search-get-started-dotnet) and uses the [Azure Cognitive Search .NET SDK](https://docs.microsoft.com/dotnet/api/?term=microsoft.azure.search) to create an index and efficiently load it with documents using the push model.

The app shows how to:

- Test different batch sizes to understand the optimal batch size for indexing your data
- Efficiently index data by:
  - [Pushing](https://docs.microsoft.com/azure/search/search-what-is-data-import#pushing-data-to-an-index) data to the index in batches
  - Sending multiple batches concurrently
  - Implementing an [exponential backoff retry strategy](https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/implement-retries-exponential-backoff)

The index is modeled on a subset of the Hotels dataset, reduced for readability and comprehension. Index definition and documents are included in the code.

> **Note:**  Depending on your network transfer speeds, you may need to run this sample from within your Azure Environment to get the most out of Azure Cognitive Search's indexing speed.
>
>Spinning up an [Azure VM](https://azure.microsoft.com/services/virtual-machines/) that comes with Visual Studio installed, such as a [Data Science VM](https://azure.microsoft.com/services/virtual-machines/data-science-virtual-machines/) is an easy way to do this. Be sure to deploy the VM in the same data center as your search service.

## Contents

| File/folder | Description |
|-------------|-------------|
| `OptimizeDataIndexing.sln`       | .NET Core console solution file |
| `OptimizeDataIndexing`       | Source files |
| `CONTRIBUTING.md` | Guidelines for contributing to the sample. |
| `README.md` | This README file. |
| `LICENSE`   | The license for the sample. |

## Prerequisites

- [Visual Studio](https://visualstudio.microsoft.com/downloads/)
- [Azure Cognitive Search service](https://docs.microsoft.com/azure/search/search-create-service-portal)

## Setup

1. Clone or download this sample repository.
1. Extract contents if the download is a zip file. Make sure the files are read-write.

### Running quickstart

1. Open the OptimizeDataIndexing.sln project in Visual Studio
1. Update the appsettings.json with the service and api details of your search service
1. Compile and Run the project

## Next steps

You can learn more about Azure Cognitive Search on the [official documentation site](https://docs.microsoft.com/azure/search).

The documentation provides additional guidance on [indexing large data sets](https://docs.microsoft.com/azure/search/search-howto-large-index).