# GraphRAG Benchmark Datasets

This repository contains the data assets used for benchmarking in the paper  
**[Optimizing open-domain question answering with graph-based retrieval augmented generation](https://arxiv.org/abs/2503.02922)**.

## 📂 Repository Structure

To explore or run benchmarks:

1. Navigate to the `data/` directory or the relevant subdirectory of interest.
2. Unzip the benchmark dataset you're interested in.
3. Follow the steps below to run the [GraphRAG](https://github.com/microsoft/graphrag) pipeline on these datasets.

## 🚀 Getting Started with GraphRAG

1. **Install GraphRAG:**

```bash
pip install graphrag
```

Refer to the GraphRAG Getting [Started Guide](https://microsoft.github.io/graphrag/get_started/) for additional context.

2. **Prepare Your Workspace:**

Create a new directory to hold your input files (e.g., for the Kevin Scott podcast benchmark):

```
mkdir -p ./kevin_scott_podcasts/input
```

Place the unzipped input files into the input folder.

3. **Initialize the GraphRAG Workspace:**

```
graphrag init --root ./kevin_scott_podcasts
```

This command creates two files inside the `./kevin_scott_podcasts/` folder:
- `.env`: contains the GRAPHRAG_API_KEY environment variable, which should be set to your OpenAI or Azure OpenAI API key.
If using managed identity or another form of authentication, you may delete this file.
- `settings.yaml`: configures the GraphRAG pipeline. You may edit this to customize your pipeline behavior.

4. **Run the Indexing Pipeline:**

```
graphrag index --root ./kevin_scott_podcasts
```

Please note that indexing time varies based on the size of the dataset and may take several minutes to several hours.


5. **Query the Dataset:**

You can now run queries against your indexed dataset. For example, to perform global search:

```
graphrag query \
  --root ./kevin_scott_podcasts \
  --method global \
  --query "What is the nationality of Scott Derrickson?"
```

## 📊 Benchmark Queries

The exact queries used in the paper are included as .csv files in the `data` directory.

## 🤝 Contributing

We welcome contributions and suggestions!

By submitting a pull request, you agree to the [Microsoft Contributor License Agreement](https://cla.opensource.microsoft.com). A CLA bot will automatically check for compliance.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
