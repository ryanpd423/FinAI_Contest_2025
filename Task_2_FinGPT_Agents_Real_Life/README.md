## FinAI Contest Task 2 - FinGPT Agents in Real Life

### 🧠 Task Overview

This task is to fine-tune LLMs and develop financial agents for financial analytics, including the CFA exam, BloombergGPT’s public benchmark tasks, and XBRL tasks. We encourage participants to use LoRA and reinforcement fine-tuning.

- **CFA exam**: The CFA (Chartered Financial Analyst) exam is a globally recognized exam for financial analysts. It covers a wide range of financial topics, such as investment, economics, and quantitative methods.
- **BloombergGPT**: Compare the performance of your model with BloombergGPT on its public financial benchmarks.
- **XBRL**: XBRL (eXtensible Business Reporting Language) is a standard language for electronic communication of business and financial data. It has been widely used in regulatory filings, such as SEC filings.

#### 🎯 Objective

Your primary goal is to fine-tune or train a language model for financial analytics across the CFA exam, BloombergGPT benchmark tasks, and XBRL tasks. You may also enhance your agent by integrating external tools, such as a retrieval-augmented knowledge base (RAG), to improve its analytical and question-answering capabilities.

#### 💡 What You Need To Do

1. **Collect and Prepare Your Raw Training Data**  
   Participants need to collect raw data given the source provided below.

2. **Develop FinGPT Agents**  
   Use your collected data to fine-tune your own LLM for financial analytics. You can use FinGPT framework to fine-tune your model. We encourage participants to use LoRA and reinforcement fine-tuning. You can also enhance your agent by integrating external tools, such as RAG. You can view [**FinLoRA documentation**](https://finlora-docs.readthedocs.io/en/latest/index.html) to learn more about LoRA and some financial tasks.

3. **Submit Your Agent**  
   Submit your agent following the competition guidelines. Make sure your model is:

   - Capable of answering complex domain-specific questions.
   - Robust in interpreting structured data and reasoning over it.

4. **Benchmarking Phase**  
   After submission, we will use our question sets to evaluate your model's performance on CFA exams, BloombergGPT benchmark tasks, and XBRL tasks.

---

### 📊 Question Set Overview

These question sets contain question-answer pairs collected and organized for evaluating model capabilities across CFA exams, BloombergGPT benchmark tasks, and XBRL tasks. These question sets are sampled from the test split of the datasets, which are used to benchmark your agent's performance. You **SHOULD NOT** use it or the entire test split for fine-tuning or training.

#### CFA Exams

| **Exam Level** | **# Exams** | **Questions/Exam** | **Total** | **Description**                                                                                                                                                  |
| -------------- | ----------- | ------------------ | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Level I        | 3           | 180                | 540       | Level I has multiple-choice questions to test a candidate’s understanding of core concepts in finance, investment tools, and ethical and professional standards. |
| Level II       | 2           | 88                 | 176       | Level II has multiple-choice questions with contextual scenario, emphasizing the application of concepts and analytical skills.                                  |

| **Topic**               | **Level I** | **Level II** | **Total** |
| ----------------------- | ----------- | ------------ | --------- |
| Ethics                  | 81          | 24           | 105       |
| Quantitative Methods    | 43          | 12           | 55        |
| Economics               | 41          | 12           | 53        |
| Financial Reporting     | 66          | 24           | 90        |
| Corporate Issuers       | 41          | 12           | 53        |
| Equity Investments      | 67          | 24           | 91        |
| Fixed Income            | 65          | 24           | 89        |
| Derivatives             | 43          | 12           | 55        |
| Alternative Investments | 36          | 12           | 48        |
| Portfolio Management    | 57          | 20           | 77        |
| **Total**               | **540**     | **176**      | **716**   |

#### BloombergGPT [1] Public Benchmark Datasets

| **Dataset**                            | **Size** | **Metrics**    | **# of shots** | **Dataset Link**                                                   | **Description**                                                                                                                                                                                                                        |
| -------------------------------------- | -------- | -------------- | -------------- | ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Financial Phrasebank Dataset (FPB) [2] | 970      | F1             | 5              | [Link](https://huggingface.co/datasets/ChanceFocus/en-fpb)         | The Financial Phrasebank Dataset includes a sentiment classification task on sentences from financial news. Any news that could benefit/hurt an investor is considered positive/negative and neutral otherwise.                        |
| FiQA SA [3]                            | 235      | F1             | 5              | [Link](https://huggingface.co/datasets/ChanceFocus/flare-fiqasa)   | This is a sentiment analysis task to predict the aspect-specific sentiment in English financial news and microblog headlines, which were published as a part of the 2018 challenge on financial question answering and opinion mining. |
| Headline [4]                           | 20.5k      | F1             | 5              | [Link](https://huggingface.co/datasets/FinGPT/fingpt-headline-cls) | This is a binary classification task of whether a news headline in the gold commodity domain includes certain information. This human-annotated dataset consists of English news headlines about “gold”.                               |
| NER [5]                                | 3.5k      | F1             | 20             | [Link](https://huggingface.co/datasets/FinGPT/fingpt-ner-cls)      | This is a named entity recognition task on financial data gathered for credit risk assessment from financial agreements filed with the SEC.                                                                                            |
| ConvFinQA [6]                          | 1.49k      | Match Accuracy |                | [Link](https://huggingface.co/datasets/FinGPT/fingpt-convfinqa)    | Given input from S&P 500 earnings reports that includes text and at least one table with financial data, the task is to answer conversational questions that require numerical reasoning over the input.                               |

We will sample 150 questions from the test split for each dataset for our evaluation.

#### 📁 XBRL Dataset

| **Dataset**                                 | **Size** | **Metrics** | **Dataset Link**                                                  | **Description**                                                                                                                                                                                                                            |
| ------------------------------------------- | -------- | ----------- | ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| XBRL tag extraction                         | 2.9k      | Accuracy    | [Link](https://huggingface.co/datasets/wangd12/XBRL_analysis)     | Extract a specific XBRL tag from a raw XBRL text segment given a natural language description of the tag                                                                                                                                   |
| XBRL value extraction                       | 2.5k      | Accuracy    | [Link](https://huggingface.co/datasets/wangd12/XBRL_analysis)     | Extract a numeric value from the raw XBRL text segment given a natural language description of the value.                                                                                                                                  |
| XBRL formula construction                   | 835      | Accuracy    | [Link](https://huggingface.co/datasets/wangd12/XBRL_analysis)     | First identify and select multiple relevant facts (and their corresponding XBRL tags) from the XBRL data, and then construct a standard financial formula.                                                                                 |
| XBRL formula calculation                    | 835      | Accuracy    | [Link](https://huggingface.co/datasets/wangd12/XBRL_analysis)     | Build on the previous task and requires the LLM to substitute the actual numeric values into the formula and compute the final result.                                                                                                     |
| Financial Numeric Identification (FinNI)[7] | 6.6k (sample 200)     | F1          | [Link](https://github.com/The-FinAI/FinTagging/tree/main/subdata) | Focus on identifying numerical values in a financial document and assigning each a coarse-grained value data type. This corresponds to detecting the Fact and Type components of each triplet {Fact,Type,Tag} defined in the overall task. |
| Financial Concept Linking (FinCL) [7]       | 52.6k (sample 500)     | Accuracy    | [Link](https://github.com/The-FinAI/FinTagging/tree/main/subdata) | Semantically ground each identified numerical entity by linking it to a concept in a predefined financial taxonomy, which is the Tag component of each triplet {Fact,Type,Tag} defined in the overall task.                                |

For all question sets, we sample some questions from the test split. Participants should NOT use the test split to fine-tune their model. For FinNI and FinCL tasks, participants can utilize these [resources](https://github.com/The-FinAI/FinTagging/blob/main/annotation/TrainingSet_Annotation.json) as training data.

##### 📂 How to Download XBRL Filings

To construct or extend your training dataset with real-world XBRL filings, participants may utilize the following data sources:

##### 📥 1. Company-Level Financial Statements

You can manually retrieve XBRL filings for individual companies via the U.S. Securities and Exchange Commission (SEC):

1. Visit the [SEC EDGAR Company Search](https://www.sec.gov/edgar/searchedgar/companysearch).
2. Search by company name or ticker symbol.
3. Filter by filing types such as 10-K, 10-Q, etc.
4. Click on a specific filing.
5. Look for files with extensions like:
   - `.xml`
   - `.xsd`
   - `.xbrl`
   - or links labeled "Interactive Data".
6. Download the corresponding XBRL instance and taxonomy files.

> 💡 This method is ideal for collecting filings from specific companies or filing types in a controlled manner.

##### ⚙️ 2. XBRL Terminology & Standards

As a starting point, you may also use the provided web crawling script to automate the retrieval of XBRL-related documents from the [XBRL International Glossary](https://www.xbrl.org/guidance/xbrl-glossary/). This source provides standardized definitions and explanations of XBRL terms. These documents help the model better understand the semantics and structure of XBRL as a framework.

- 📎 Provided Code: [xbrl_webcrawl.ipynb](./xbrl_webcrawl.ipynb)

This script offers a basic template to:

- Scrape and parse glossary terms.
- Crawl linked resources or downloadable attachments related to XBRL filings.
- Extend it further for large-scale automated crawling from additional sources (e.g., SEC bulk data feeds, company repositories, etc.).

> 💡 This data helps build XBRL term comprehension tasks, enabling models to understand and explain technical terms used in filings. Participants are encouraged to adapt and extend the script to suit their own dataset construction needs.

- 📎 Provided Code: [task_2_finetune.ipynb](./task_2_finetune.ipynb)
  This script offers a basic template for fine-tuning:
- The notebook is simplified.
- For more detailed instructions, please check the tutorials under the FinLoRA docs here: https://finlora-docs.readthedocs.io/en/latest/index.html.
- The full process for a **simplified** Buffett Agent model we created can be found here: https://finlora-docs.readthedocs.io/en/latest/tutorials/buffett_agent.html.

Note: We will additionally test on a subset of the FiNER-139 and FNXL datasets. Please use the batched versions provided in this folder for fine-tuning to avoid overfitting. To test, please use the code from https://github.com/Open-Finance-Lab/FinLoRA/blob/main/test/xbrl.py.

---

### 📥 Submission Requirement

### 📊 Metrics

The model evaluation in each domain is the average score of all tasks.

#### 📘 Note for Participants

Participants are encouraged to use the above sources as a starting point to construct their own training/fine-tuning datasets. Your model's performance will strongly depend on the quality and comprehensiveness of your self-collected training data. These sources can help you build a rich and task-aligned dataset for model training, ensuring better performance on regulatory reasoning and question answering.

To ensure fair comparison and practical deployment, it is recommended that the model size should not exceed 8B parameters.

[1] Shijie Wu, Ozan Irsoy, Steven Lu, Vadim Dabravolski, Mark Dredze, Sebastian Gehrmann, Prabhanjan Kambadur, David Rosenberg, Gideon Mann. BloombergGPT: A Large Language Model for Finance. arXiv: 2303.17564, 2023.

[2] Pekka Malo, Ankur Sinha, Pekka J. Korhonen, Jyrki Wallenius, and Pyry Takala. Good debt or bad debt: Detecting semantic orientations in economic texts. J. Assoc. Inf. Sci. Technol., 65(4):782–796, 2014. doi: 10.1002/asi.23062. URL https://doi.org/10. 1002/asi.23062.

[3] Macedo Maia, Siegfried Handschuh, Andr´ e Freitas, Brian Davis, Ross McDermott, Manel Zarrouk, and Alexandra Balahur. Www’18 open challenge: Financial opinion mining and question answering. In Pierre-Antoine Champin, Fabien Gandon, Mounia Lalmas, and Panagiotis G. Ipeirotis, editors, Companion of the The Web Conference 2018 on The Web Conference 2018, WWW 2018, Lyon , France, April 23-27, 2018, pages 1941–1942. ACM, 2018. doi: 10.1145/3184558.3192301. URL https://doi.org/10.1145/3184558. 3192301.

[4] Ankur Sinha and Tanmay Khandait. Impact of news on the commodity market: Dataset and results. CoRR, abs/2009.04202, 2020. URL https://arxiv.org/abs/2009.04202.

[5] Julio Cesar Salinas Alvarado, Karin Verspoor, and Timothy Baldwin. Domain adaption of named entity recognition to support credit risk assessment. In Proceedings of the Australasian Language Technology Association Workshop 2015, pages 84–90, Parramatta, Australia, December 2015. URL https://aclanthology.org/U15-1010.

[6] Zhiyu Chen, Shiyang Li, Charese Smiley, Zhiqiang Ma, Sameena Shah, and William Yang Wang. ConvFinQA: Exploring the chain of numerical reasoning in conversational finance question answering. In Proceedings of the 2022 Conference on Empirical Methods in Natural Language Processing, pages 6279–6292, Abu Dhabi, United Arab Emirates, December 2022. Association for Computational Linguistics. URL https://aclanthology. org/2022.emnlp-main.421.

[7] Yan Wang, Yang Ren, Lingfei Qian, Xueqing Peng, Keyi Wang, Yi Han, Dongji Feng, Xiao-Yang Liu, Jimin Huang, and Qianqian Xie. FinTagging: An LLM-ready Benchmark for Extracting and Structuring Financial Information. arXiv: 2505.20650, 2025.

[8] Wang, Y., Ren, Y., Qian, L., Peng, X., Wang, K., Han, Y., ... & Xie, Q. (2025). FinTagging: An LLM-ready Benchmark for Extracting and Structuring Financial Information. arXiv preprint arXiv:2505.20650.
