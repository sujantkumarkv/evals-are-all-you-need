# **The State of AI Benchmarks in Core Scientific Domains: A Comprehensive Review of Methodologies, Datasets, and Critical Challenges**

## **Executive Summary**

The evaluation of artificial intelligence models in core scientific disciplines presents a paradox of rapidly advancing performance on established metrics and persistent, fundamental gaps in their ability to contribute to genuine discovery. This report provides a comprehensive review of the current landscape of AI benchmarks, evaluation frameworks, and datasets across mathematics, physics, chemistry, biology, and medicine. The analysis reveals a central tension: while AI systems boast impressive scores on standardized, complex benchmarks like GPQA and SWE-bench, a growing body of evidence suggests that these evaluations often measure a model's "skill" at a fixed task rather than the "intelligence" required for true scientific inquiry and the efficient acquisition of new knowledge.1

A primary challenge identified across multiple domains is the problem of "unrealistic" benchmarks, which can lead to overoptimistic performance metrics. Critiques of widely used datasets, such as those in drug discovery, highlight systemic flaws like data contamination, where test molecules are too similar to those in the training set, allowing models to "memorize" rather than "generalize".3 This is compounded by a lack of transparency, a focus on easily quantifiable outputs over nuanced reasoning, and the "black box" nature of many models, which hinders their acceptance in fields where causal understanding is paramount.4

Despite these challenges, the report identifies several promising trends. There is a discernible shift away from static, textbook-style evaluations toward "living" and iterative frameworks that more closely simulate the scientific process.6 The development of specialized benchmarks, such as the Theoretical Physics Benchmark (TPBench) and the agentic ChemGraph framework, is crucial for diagnosing specific computational weaknesses in models.9 Furthermore, community-wide, blind experiments like the Critical Assessment of Structure Prediction (CASP) have served as a definitive model for how a well-designed evaluation can not only measure progress but also accelerate an entire field, as seen with the success of AlphaFold.11 The future of AI evaluation in science lies in fostering a more principled, problem-driven approach that prioritizes reproducibility, interpretability, and the measurement of an AI's ability to act as a true partner in the process of discovery.

## **Introduction: The Evolving Landscape of AI for Science Evaluation**

For centuries, the fundamental practice of science has remained largely unchanged, relying on a systematic and logical method of observation, hypothesis, and experimentation.13 However, the advent of artificial intelligence (AI) and machine learning (ML) is fundamentally altering this process, promising to accelerate discovery and drive innovation at an unprecedented scale.13 As AI's influence expands across society, from healthcare to the economy, it becomes critically important to develop robust and reliable methods for assessing its technical progress and societal impact.5

Benchmarks have emerged as a foundational tool in this new landscape, playing a central role in the development and regulation of AI systems.5 They provide crucial feedback signals on model performance and capabilities, shaping the direction of AI development. Businesses invest significant resources to achieve high benchmark scores, and governments are increasingly incorporating them into regulatory frameworks, such as the EU AI Act and the US AI Executive Order.5 The primary purpose of this report is to move beyond a simple cataloging of these benchmarks. It aims to provide a comprehensive and analytical review of the current state of AI evaluation in core scientific domains, including mathematics, physics, chemistry, materials science, biology, and medicine.

This analysis synthesizes information from a diverse range of sources, including authoritative institutional reports from Stanford HAI and NIST 15, academic preprints from arXiv 6, community code repositories on GitHub 18, and peer-reviewed journals.11 The report's structure is designed to first examine the foundational frameworks and general-purpose evaluations before delving into detailed, domain-specific critiques. A central theme woven throughout the document is the critical assessment of whether a given benchmark truly measures a model's capacity for scientific discovery or merely its ability to perform a set of predefined tasks. By examining the methodologies, datasets, and inherent limitations of these evaluations, this report seeks to provide a definitive, expert-level perspective on the state of the art in AI for science.

## **Foundational Frameworks and General-Purpose Benchmarks**

The evaluation of AI in scientific domains is supported by both major institutional initiatives and community-driven, open-source programs. These foundational frameworks provide a high-level view of the field's progress and set the stage for more specialized evaluations.

Major institutional efforts, such as the Stanford HAI's AI Index, serve as a macro-level barometer for the state of global AI.15 The 2025 AI Index Report, for example, highlights record growth in AI capabilities and investment.2 It notes that performance on demanding benchmarks like MMMU, GPQA, and SWE-bench has increased sharply, with scores rising by 18.8, 48.9, and 67.3 percentage points, respectively, over the past year.2 The report also emphasizes that model development is becoming increasingly global, with China closing the performance gap on major benchmarks like MMLU and HumanEval.2

In parallel, the National Institute of Standards and Technology (NIST) focuses on developing the scientific foundation for AI measurements, evaluations, and standards.16 NIST's efforts in AI Test, Evaluation, Validation and Verification (TEVV) are central to its mission of cultivating trust in AI technologies.16 The agency's work is anchored in its AI Risk Management Framework (AI RMF), which aims to create reliable and widely accepted methods to measure and evaluate AI systems, including those used in government agencies.16

Beyond these national-level initiatives, community-driven projects provide the hands-on tools for scientific AI research. The MLCommons Science working group, for instance, encourages the curation of large-scale scientific datasets and the engineering of ML benchmarks that operate on them.22 This group aims to assemble and distribute scientific data in a systematic manner and pose quantifiable targets, which are defined as a dataset, objective criteria, and an example implementation.22 Similarly, SciML-Bench is an open-source toolkit aimed at the 'AI for Science' research community.20 It provides a flexible, lightweight framework for benchmarking AI algorithms and comparing software and hardware systems across domains like materials, life sciences, and particle physics.20

While these general and foundational frameworks track and support progress, a significant limitation is revealed when their results are applied to the complexities of scientific discovery. The impressive scores on benchmarks like GPQA and SWE-bench, as featured in the AI Index 2, can be misleading. A YouTube seminar on the Scientific Discovery Evaluation (SDE) Framework explicitly argues that traditional benchmarks like GPQA fall short for real scientific research.7 This is because they focus on "textbook-style Q\&A," which is fundamentally different from the "iterative scientific discovery workflows" that involve hypothesis generation, experimentation, observation, and refinement.7 The core issue is that these high-scoring models are demonstrating a capacity for "skill" in performing a specific task, but not the "general intelligence" required to efficiently acquire new skills and perform original research.1 The development of the SDE Framework is a direct response to this deficiency, highlighting a critical need to evolve evaluation methods to align with the true nature of scientific inquiry.

## **Domain-Specific Benchmark Deep Dives**

The general critiques of AI benchmarks become even more pronounced within specific scientific disciplines, where the nuances of problem-solving require specialized evaluation frameworks. The following sections provide a detailed analysis of key benchmarks and datasets across core scientific domains.

### **Mathematics and Physics**

The fields of mathematics and physics have pioneered some of the most rigorous and specialized benchmarks, primarily due to the clear, verifiable nature of their problems.

#### **Automated Theorem Proving (ATP)**

Automated theorem proving, a subfield of automated reasoning, has long been a key goal of AI.23 The quality of ATP systems has benefited immensely from the existence of a large library of standard benchmark examples.23

* **MiniF2F**: Developed by OpenAI and Facebook Research, MiniF2F is a formal mathematics benchmark that translates exercise statements from mathematics olympiads (AMC, AIME, IMO) and undergraduate classes into formal systems like Lean and Metamath.24 Its structure, with a  
  held-out test set, is designed to prevent data leakage and provide a fair evaluation.24  
* **ProofNet**: This benchmark is designed for autoformalization and formal proving of undergraduate-level mathematics.26 It contains 371 examples drawn from popular pure mathematics textbooks, challenging models to reason over a large knowledge base rather than a small set of elementary facts, a common limitation of competition-based problems.27  
* **Goedel-Prover-V2**: This open-source model series demonstrates a powerful approach to advancing performance on these benchmarks.28 Its success is attributed to three key innovations:  
  **scaffolded data synthesis**, which trains the model on progressively more difficult synthetic problems; **verifier-guided self-correction**, which allows the model to iteratively revise proofs using feedback from the Lean compiler; and **model averaging**, which helps maintain the diversity of the model's outputs.28 The flagship Goedel-Prover-V2-32B model achieved a 90.4% accuracy on MiniF2F and solved 86 problems on PutnamBench, surpassing much larger models with significantly smaller compute budgets.28 This shows that progress is not solely dependent on model scale but can be achieved through smarter, more principled training methods.

#### **Reasoning in Fundamental Physics**

The development of benchmarks in physics goes beyond simple problem-solving to address the challenges of reasoning on research-level questions.

* **TPBench (Theoretical Physics Benchmark)**: This benchmark, introduced in an arXiv preprint, is designed to evaluate AI's capability to solve problems in high-energy theory and cosmology.9 Its first iteration contains 57 novel problems, from undergraduate to research level, that do not come from public problem collections, a crucial design choice to prevent data contamination.9 The study found that while impressive progress has been made with recent models, research-level problems remain "mostly unsolved," with common failure modes including algebraic mistakes, logical errors, and hallucinations.9  
* **"Towards a Large Physics Benchmark"**: A more recent arXiv preprint introduces a "living benchmark" that is developed by and for the scientific community.6 It builds on philosophical concepts of scientific understanding and creativity, with a scoring system that assesses not just correctness but also difficulty and "surprise".6 The key innovation is the proposal for physicists to contribute questions alongside new publications, ensuring the benchmark remains relevant and challenging in perpetuity.6

This progression in mathematical and physics benchmarks reveals a direct response to the limitations of fixed evaluations. The community has recognized that static, public benchmarks are easily overfitted and quickly become obsolete.1 By creating novel, private, and now "living" benchmarks, the field is evolving to evaluate an AI's capacity for genuine, unscripted reasoning that mirrors the unpredictable nature of real-world scientific advancement.

### **Chemistry and Materials Science**

The evaluation of AI in chemistry and materials science is characterized by efforts to simulate the complex, multi-step nature of molecular design and discovery.

#### **Molecular Design and Drug Discovery**

A critical analysis of the disconnect between AI benchmarks and real-world drug discovery processes is a central theme in recent research.

* **The Lo-Hi Benchmark**: A paper titled "Lo-Hi: Practical ML Drug Discovery Benchmark" provides a detailed critique of existing, widely used benchmarks like MoleculeNet and Therapeutic Data Commons (TDC).3 The authors argue that these benchmarks are "unrealistic and overoptimistic" because their data splits often result in highly similar molecules across the train and test sets.3 For example, the MoleculeNet HIV dataset, despite recommending a scaffold split, was found to have 56% of test molecules with a Tanimoto similarity over 0.4 to a training neighbor.3 This leads to a scenario where models are not truly generalizing but are simply memorizing and interpolating minor changes, which fails to reflect the real-world challenge of finding truly novel molecules.  
* **The Lo-Hi Solution**: The Lo-Hi benchmark was created to address this flaw by separating drug discovery into two distinct tasks: **Hit Identification (Hi)** and **Lead Optimization (Lo)**.3 The Hi task is designed to explicitly test for novelty, using a molecular splitting algorithm that ensures no molecule in the test set is highly similar to those in the training set.3 The Lo task, a ranking problem, evaluates a model's ability to predict minor fluctuations in molecular activity, which is crucial for refining a candidate drug.3

This critique underscores a fundamental problem of construct validity in a widely-cited field. The continued use of flawed benchmarks, despite the availability of more rigorous alternatives, has created a misleading illusion of progress. By explicitly designing a benchmark to test for the core scientific goal of novelty and generalization, the Lo-Hi paper provides a more truthful and actionable evaluation framework.

#### **Computational Chemistry Workflows**

Beyond molecular properties, new benchmarks are emerging to evaluate a model's ability to execute complex, multi-step scientific procedures.

* **QCBench**: This Quantitative Chemistry benchmark comprises 350 computational chemistry problems designed to assess LLM's ability to perform "rigorous, step-by-step quantitative reasoning".17 The evaluation on 19 different LLMs revealed a consistent performance degradation as task complexity increased, highlighting a critical gap between language fluency and scientific computation accuracy.17  
* **ChemGraph**: The ChemGraph framework, an LLM-based molecular simulation framework, is evaluated using a dataset that provides scripts and tools for benchmarking multi-step workflows.10 The evaluation script compares an LLM's generated workflow against a manually constructed reference workflow, computing accuracy metrics for tool usage, order, and correctness.10 This type of evaluation moves beyond simple Q\&A to assess a model's agentic reasoning and its capacity to manage a multi-step process.

### **Biology and Medicine**

The evaluation landscape in biology and medicine is characterized by a mix of mature, community-wide challenges and a reliance on large, public data repositories.

#### **Protein Structure Prediction**

The field of protein structure prediction offers a unique and definitive case study in the success of AI benchmarking.

* **CASP (Critical Assessment of Structure Prediction)**: Launched in 1994, CASP is a community-wide, biennial experiment that is widely considered the "gold standard" and a "world championship" for evaluating protein structure prediction methods.11 Its rigorous, independent, and blind testing protocol ensures that predictors have no prior information about the target protein's structure at the time of prediction.12  
* **The CASP14 Breakthrough**: In the most recent experiment, deep learning methods from one research group consistently delivered computed structures that rivaled experimental ones in accuracy.11 This result was so significant that the paper declares it a "solution to the classical protein folding problem, at least for single proteins".11 The primary evaluation metric, the GDT-TS (Global Distance Test—Total Score), provides a numerical score for the quality of the prediction.12  
* **The Impact of AlphaFold**: Following the open-sourcing of AlphaFold in 2021, CASP15 in 2022 saw "virtually all of the high-ranking teams" using AlphaFold or its modifications.12 This sequence of events—a rigorous blind test, a historic breakthrough, and the subsequent open-sourcing of the winning methodology—illustrates a positive feedback loop where effective benchmarking not only measures progress but also serves as a catalyst for widespread scientific advancement.

#### **Genomics and Bioinformatics**

The evaluation of AI in genomics is multifaceted, focusing on sequence classification, variant effect prediction, and linguistic tasks.

* **AlphaGenome**: A new AI tool from Google DeepMind, AlphaGenome, achieves state-of-the-art performance on a wide range of genomic prediction benchmarks.31 It uses a unified deep learning model to predict how single variants or mutations in DNA sequences impact gene regulation, achieving improvements of up to 25.5% over previous models in directional accuracy.32  
* **Genomic Benchmarks**: The ML-Bioinfo-CEITEC/genomic\_benchmarks GitHub repository is a key open-source resource that collects benchmarks for the classification of genomic sequences.19 The repository provides datasets for specific tasks, such as distinguishing coding sequences from intergenomic sequences, and provides baselines for models like HyenaDNA.19  
* **GeneTuring**: This benchmark evaluates LLMs on foundational bioinformatics tasks like gene name extraction and gene alias identification.33 It uses a Jaccard index to evaluate the performance of models, demonstrating a movement toward specialized, task-specific metrics that go beyond simple accuracy to assess semantic correctness in a scientific context.33

#### **Medical Imaging and Diagnostics**

In medical imaging, evaluation relies heavily on large, publicly available datasets that function as de facto benchmarks.

* **Public Repositories**: The field is built on comprehensive repositories that enable the training and validation of AI models.34 Major examples include the NIH Chest X-Ray Dataset, which contains over 100,000 anonymized images; The Cancer Imaging Archive (TCIA), which hosts a large collection of cancer-specific medical images; and the Stanford AIMI Collections, which include the CheXpert Plus dataset.34  
* **Benchmark Datasets**: Specialized datasets, such as the MedSegBench repository for segmentation tasks and a diagnostic MRI dataset with 40 classes of diseases, serve as crucial resources for developing and testing algorithms for specific clinical applications.34 The reliance on these repositories underscores the fact that in this domain, the sheer scale and diversity of the data are foundational to the evaluation process, as models are judged on their ability to generalize across a vast range of real-world clinical conditions.

### **Table 1: Key Benchmarks in Core Scientific Domains**

| Domain | Benchmark/Framework Name | Primary Purpose | Key Datasets | Representative Models |
| :---- | :---- | :---- | :---- | :---- |
| Mathematics | MiniF2F | Automated theorem proving of school/university problems | AMC, AIME, IMO exercises | Goedel-Prover-V2, DeepSeek-Prover-V2 |
|  | ProofNet | Autoformalization and formal proving of undergraduate math | Undergraduate pure mathematics textbooks | Not specified |
|  | PutnamBench | Automated theorem proving of advanced math problems | Putnam Competition problems | Goedel-Prover-V2 |
| Physics | TPBench | Evaluating AI reasoning in theoretical physics | 57 novel problems in high-energy theory, cosmology | GPT-4o, DeepSeek-R1, o3-mini |
|  | Large Physics Benchmark | "Living" benchmark for fundamental physics research | Machine learning challenges, analytical problems | Not specified |
| Chemistry | Lo-Hi | Practical ML drug discovery benchmark | Lo-Hi, derived from public data | State-of-the-art and classic ML models |
|  | QCBench | Evaluating quantitative reasoning in chemistry | 350 computational chemistry problems | 19 LLMs, including GPT-4o, Llama |
|  | ChemGraph | Benchmarking agentic workflows for molecular simulation | data\_from\_pubchempy.json, manual\_workflow.json | GPT-4o-mini, Claude-3.5-haiku, GPT-4o |
| Biology | CASP | Independent, blind assessment of protein structure prediction | Novel, unpublished protein sequences | AlphaFold, virtually all high-ranking teams |
|  | AlphaGenome | Predicting variant effects on gene regulation | ENCODE, GTEx, 4D Nucleome, FANTOM5 | AlphaGenome, Enformer |
| Medicine | NIH Chest X-Ray | Diagnostic AI for chest radiography | 100,000+ anonymized chest X-rays | Various computer vision models |
|  | MedSegBench | Medical image segmentation tasks | Diverse medical images for segmentation | Not specified |

## **Critical Analysis: The Gaps Between Evaluation and Scientific Progress**

Despite the proliferation of specialized benchmarks and the impressive scores models are achieving, a critical examination reveals several systemic flaws that prevent current evaluation practices from fully capturing the essence of scientific progress. These issues can be synthesized into three major categories.

### **The Problem of Unrealistic Benchmarks**

A recurring problem is that many benchmarks, even those designed for scientific domains, are susceptible to data contamination and overfitting. The Lo-Hi paper's critique of widely used drug discovery benchmarks exemplifies this challenge.3 The paper demonstrates that datasets like MoleculeNet and Therapeutic Data Commons (TDC) contain highly similar molecules across different data splits, leading to "overly optimistic and impractical estimations" of a model's performance.3 This problem is analogous to a student who has memorized all the answers from past exams rather than genuinely understanding the underlying concepts.1

This is more than a simple technical issue; it points to a misalignment of incentives. The push for high scores on a limited set of benchmarks can lead to the "gaming" of results, where models are optimized for a specific metric rather than for genuine scientific utility.5 The result is a false sense of progress, as a model may perform well on a leaderboard but fail when confronted with the truly novel, unseen problems of real-world research.

### **Table 2: Comparative Analysis of Molecular Benchmarks**

| Benchmark | Key Tasks | Strengths | Identified Limitations |
| :---- | :---- | :---- | :---- |
| **MoleculeNet** (ESOL, HIV) | Molecular property prediction, hit identification | Widely used, large datasets, diverse tasks | Unrealistic train-test splits; highly similar molecules in different partitions; leads to "overly optimistic" estimations. |
| **Therapeutic Data Commons** (TDC.CYP2D6\_Veith) | Single-instance learning, hit identification | Novel platform, large dataset for its task | Unsuitable for Hit Identification due to high similarity between train and test sets; binary labels unsuitable for Lead Optimization. |
| **Lo-Hi** | **Hit Identification (Hi)**, **Lead Optimization (Lo)** | Separates tasks for realistic evaluation; uses novel splitting algorithm to prevent data leakage and enforce true novelty. | Newer benchmark; may not have as wide an adoption yet as older benchmarks. |

### **The "Black Box" Challenge**

In scientific research, trust and causal understanding are paramount. A major impediment to the adoption of AI models in fields like chemistry and materials science is their "black box" nature.4 While deep neural networks can achieve remarkable accuracy, they often fail to provide insight into the underlying reasons for their predictions.4 This lack of transparency is a critical hurdle, hindering regulatory acceptance and reducing trust among human researchers.4

The development of interpretable and physics-informed machine learning frameworks is a direct response to this challenge.36 For example, in materials science, researchers are developing models that not only make accurate predictions but also "understand the scientific rationale behind them," ensuring that the designed materials meet both theoretical and practical performance benchmarks.36 This movement reflects the scientific community's demand that AI models provide not just an answer, but a verifiable and explainable path to that answer.

### **The Reproducibility Crisis**

Reproducibility is a minimal prerequisite for the creation of new knowledge and scientific progress.21 However, the provided research highlights that reproducing a machine learning model trained by another research team can be "prohibitively difficult" even with unrestricted access to raw data and code.21 This is due to a combination of incomplete documentation, randomness inherent to the analysis procedure, and the sheer complexity of modern models.21

The existence of open-source resources, such as the Genomic Benchmarks GitHub repository 19 and the provision of scripts and evaluation tools with new frameworks like ChemGraph 10, are crucial steps toward addressing this crisis. These initiatives provide a shared, transparent foundation for the community, but the challenge of ensuring full reproducibility across different teams and hardware remains a significant hurdle.

### **Table 3: Major Public Datasets for AI in Medicine & Biology**

| Domain | Dataset Name | Modality/Content | Size/Scope | Key Applications |
| :---- | :---- | :---- | :---- | :---- |
| **Medical Imaging** | **NIH Chest X-Ray Dataset** | Anonymized chest X-ray images | Over 100,000 images from 30,000+ patients | Developing and validating AI algorithms in chest radiography. |
|  | **The Cancer Imaging Archive (TCIA)** | Cancer-specific medical images | Large archive of de-identified medical images | Oncology research and development. |
|  | **MedSegBench** | Medical images for segmentation | Comprehensive collection across various modalities | Developing and testing segmentation algorithms. |
|  | **Benchmark Diagnostic MRI and Medical Imaging Dataset** | MRI scans of the brain, neuro, and spine | 34,192 images with 40 disease classes | Image recognition, classification, and segmentation. |
| **Genomics** | **GenBank** (via NCBI) | Nucleic acid sequences | Not specified | Central resource for sequence data. |
|  | **Genomic Benchmarks** | Genomic sequences for classification | 8 datasets (e.g., human\_nontata\_promoters) | Benchmarking models for classification of genomic sequences. |
|  | **Genome in a Bottle (GIAB)** | Human genomes | Pilot genome and two trios of diverse ancestry | Benchmarking for analytical validation and technology development. |

### **Table 4: Systemic Flaws in AI Benchmarking**

| Flaw/Challenge | Description | Example from Research Material |
| :---- | :---- | :---- |
| **Data Contamination** | Test data is too similar to training data, allowing models to memorize rather than generalize, leading to overoptimistic performance. | The Lo-Hi paper's critique of the MoleculeNet and TDC benchmarks, which show high similarity between train and test sets.3 |
| **Misaligned Incentives** | Benchmarks incentivize behaviors that lead to high scores but do not necessarily reflect true scientific progress or utility. | The focus on "skill" over "intelligence" and the "gaming of benchmark results" as discussed in various critiques.1 |
| **Lack of Interpretability** | Many models, particularly deep neural networks, are "black boxes" that do not provide a rationale for their predictions, which is a major barrier to scientific trust. | The recurring challenge of the "black box" nature of AI models in drug discovery and the need for interpretable models in materials science.4 |
| **Reproducibility Issues** | It is often "prohibitively difficult" to reproduce a machine learning study due to incomplete documentation, restricted data access, and inherent randomness. | The challenges highlighted in the review of reproducibility in machine learning studies and the critical role of open-source resources.21 |

## **Future Directions and Recommendations**

The current landscape of AI evaluation in science, as illuminated by this analysis, suggests a clear path forward that moves beyond the limitations of existing paradigms. The key to unlocking AI's full potential for discovery lies in a fundamental shift in how its performance is measured.

First, the development of **agentic and iterative benchmarks** is paramount. The Scientific Discovery Evaluation (SDE) Framework, which assesses LLMs on the complete scientific discovery loop—including hypothesis generation, experimentation, observation, and refinement—is a prime example of this future-forward approach.7 Such frameworks provide a more faithful representation of the scientific process than static, question-and-answer benchmarks.

Second, the field should move toward **community-wide, neutral standards** for evaluation. The success of CASP serves as a powerful model for this approach.11 A rigorous, independent, and blind evaluation, managed by a neutral body, can provide a more credible and authoritative assessment of the state of the art than benchmarks released by the developers of a new method.37 Initiatives like the MLCommons Science working group, which aims to bring together experts from academia, industry, and government, are crucial for this endeavor.22

Finally, the focus must shift from a "benchmark-driven" to a "problem-driven" development paradigm. This means prioritizing the creation of AI systems that can solve the novel, unstructured problems that human researchers face in their daily work.1 The impressive progress of the Goedel-Prover-V2, which uses smarter, data-efficient methods to solve challenging problems, demonstrates that genuine advancement can occur without simply scaling up model size.28

## **Conclusion**

The evidence presented in this report indicates that AI has made remarkable technical strides and is poised to be the most transformative technology of the 21st century.15 Yet, a critical disconnect persists between the capabilities celebrated on leaderboards and the actual utility required for scientific discovery. The primary challenge is not a lack of AI power but a lack of appropriate, rigorous, and relevant evaluation methodologies.

The journey from a flawed benchmark like MoleculeNet to a pragmatic, utility-focused benchmark like Lo-Hi, and from a fixed set of problems in physics to the concept of a "living benchmark," illustrates a maturation in the field's understanding of its own goals. The gold standard established by CASP demonstrates that a well-designed evaluation can serve as a powerful engine of progress, transforming a field and accelerating discovery. The future of AI for science will not be measured by the scores it achieves on a test, but by its capacity to become a trusted, transparent, and collaborative partner in the pursuit of new knowledge.

#### **Works cited**

1. \[R\] \[D\] The Disconnect Between AI Benchmarks and Math Research \- Reddit, accessed on August 23, 2025, [https://www.reddit.com/r/MachineLearning/comments/1jjn3v6/r\_d\_the\_disconnect\_between\_ai\_benchmarks\_and\_math/](https://www.reddit.com/r/MachineLearning/comments/1jjn3v6/r_d_the_disconnect_between_ai_benchmarks_and_math/)  
2. The 2025 AI Index Report | Stanford HAI, accessed on August 23, 2025, [https://hai.stanford.edu/ai-index/2025-ai-index-report](https://hai.stanford.edu/ai-index/2025-ai-index-report)  
3. Lo-Hi: Practical ML Drug Discovery Benchmark, accessed on August 23, 2025, [https://arxiv.org/html/2310.06399](https://arxiv.org/html/2310.06399)  
4. What impact does AI have on computational chemistry in drug discovery?, accessed on August 23, 2025, [https://synapse.patsnap.com/article/what-impact-does-ai-have-on-computational-chemistry-in-drug-discovery](https://synapse.patsnap.com/article/what-impact-does-ai-have-on-computational-chemistry-in-drug-discovery)  
5. Can We Trust AI Benchmarks? An Interdisciplinary Review of Current Issues in AI Evaluation, accessed on August 23, 2025, [https://arxiv.org/html/2502.06559v1](https://arxiv.org/html/2502.06559v1)  
6. \[2507.21695\] Towards a Large Physics Benchmark \- arXiv, accessed on August 23, 2025, [https://arxiv.org/abs/2507.21695](https://arxiv.org/abs/2507.21695)  
7. From MIT PhD to AI Startup: Creating Better Benchmarks for AI-Driven Scientific Research" \- YouTube, accessed on August 23, 2025, [https://www.youtube.com/watch?v=epi\_ZfSR\_YY](https://www.youtube.com/watch?v=epi_ZfSR_YY)  
8. From MIT PhD to AI Startup: Creating Better Benchmarks for AI-Driven Scientific Research" \- YouTube, accessed on August 23, 2025, [https://m.youtube.com/watch?v=epi\_ZfSR\_YY](https://m.youtube.com/watch?v=epi_ZfSR_YY)  
9. Theoretical Physics Benchmark (TPBench)--a Dataset and Study of ..., accessed on August 23, 2025, [https://arxiv.org/abs/2502.15815](https://arxiv.org/abs/2502.15815)  
10. Evaluation Dataset for ChemGraph: An Agentic Framework for ..., accessed on August 23, 2025, [https://zenodo.org/records/15579317](https://zenodo.org/records/15579317)  
11. Critical Assessment of Methods of Protein Structure Prediction (CASP) – Round XIV \- PMC, accessed on August 23, 2025, [https://pmc.ncbi.nlm.nih.gov/articles/PMC8726744/](https://pmc.ncbi.nlm.nih.gov/articles/PMC8726744/)  
12. CASP \- Wikipedia, accessed on August 23, 2025, [https://en.wikipedia.org/wiki/CASP](https://en.wikipedia.org/wiki/CASP)  
13. AI for Science, accessed on August 23, 2025, [https://ai4sciencecommunity.github.io/](https://ai4sciencecommunity.github.io/)  
14. Best AI Research Tools for Academics and Researchers \- Litmaps, accessed on August 23, 2025, [https://www.litmaps.com/learn/best-ai-research-tools](https://www.litmaps.com/learn/best-ai-research-tools)  
15. AI Index | Stanford HAI, accessed on August 23, 2025, [https://hai.stanford.edu/ai-index](https://hai.stanford.edu/ai-index)  
16. Artificial intelligence | NIST, accessed on August 23, 2025, [https://www.nist.gov/artificial-intelligence](https://www.nist.gov/artificial-intelligence)  
17. QCBench: Evaluating Large Language Models on Domain-Specific ..., accessed on August 23, 2025, [https://www.arxiv.org/abs/2508.01670](https://www.arxiv.org/abs/2508.01670)  
18. ChemFoundationModels/ChemLLMBench: What can Large Language Models do in chemistry? A comprehensive benchmark on eight tasks \- GitHub, accessed on August 23, 2025, [https://github.com/ChemFoundationModels/ChemLLMBench](https://github.com/ChemFoundationModels/ChemLLMBench)  
19. ML-Bioinfo-CEITEC/genomic\_benchmarks: Benchmarks for ... \- GitHub, accessed on August 23, 2025, [https://github.com/ML-Bioinfo-CEITEC/genomic\_benchmarks](https://github.com/ML-Bioinfo-CEITEC/genomic_benchmarks)  
20. stfc-sciml/sciml-bench: SciML Benchmarking Suite for AI for ... \- GitHub, accessed on August 23, 2025, [https://github.com/stfc-sciml/sciml-bench](https://github.com/stfc-sciml/sciml-bench)  
21. Challenges to the Reproducibility of Machine Learning Models in Health Care \- PMC, accessed on August 23, 2025, [https://pmc.ncbi.nlm.nih.gov/articles/PMC7335677/](https://pmc.ncbi.nlm.nih.gov/articles/PMC7335677/)  
22. Science \- MLCommons, accessed on August 23, 2025, [https://mlcommons.org/working-groups/research/science/](https://mlcommons.org/working-groups/research/science/)  
23. Automated theorem proving \- Wikipedia, accessed on August 23, 2025, [https://en.wikipedia.org/wiki/Automated\_theorem\_proving](https://en.wikipedia.org/wiki/Automated_theorem_proving)  
24. openai/miniF2F: Formal to Formal Mathematics Benchmark \- GitHub, accessed on August 23, 2025, [https://github.com/openai/miniF2F](https://github.com/openai/miniF2F)  
25. An updated version of miniF2F with lots of fixes and informal statements / solutions. \- GitHub, accessed on August 23, 2025, [https://github.com/facebookresearch/miniF2F](https://github.com/facebookresearch/miniF2F)  
26. ProofNet: Autoformalizing and Formally Proving Undergraduate-Level Mathematics | Request PDF \- ResearchGate, accessed on August 23, 2025, [https://www.researchgate.net/publication/368829671\_ProofNet\_Autoformalizing\_and\_Formally\_Proving\_Undergraduate-Level\_Mathematics](https://www.researchgate.net/publication/368829671_ProofNet_Autoformalizing_and_Formally_Proving_Undergraduate-Level_Mathematics)  
27. ProofNet: Autoformalizing and Formally Proving Undergraduate ..., accessed on August 23, 2025, [https://arxiv.org/abs/2302.12433](https://arxiv.org/abs/2302.12433)  
28. (PDF) Goedel-Prover-V2: Scaling Formal Theorem Proving with ..., accessed on August 23, 2025, [https://www.researchgate.net/publication/394323255\_Goedel-Prover-V2\_Scaling\_Formal\_Theorem\_Proving\_with\_Scaffolded\_Data\_Synthesis\_and\_Self-Correction](https://www.researchgate.net/publication/394323255_Goedel-Prover-V2_Scaling_Formal_Theorem_Proving_with_Scaffolded_Data_Synthesis_and_Self-Correction)  
29. GOEDEL-Prover-v2: Scaling Formal Theorem Proving With Scaffolded Data Synthesis and Self-Correction \- YouTube, accessed on August 23, 2025, [https://www.youtube.com/watch?v=QKgjEOGgwwI](https://www.youtube.com/watch?v=QKgjEOGgwwI)  
30. \[2310.06399\] Lo-Hi: Practical ML Drug Discovery Benchmark \- arXiv, accessed on August 23, 2025, [https://arxiv.org/abs/2310.06399](https://arxiv.org/abs/2310.06399)  
31. AlphaGenome: AI for better understanding the genome \- Google ..., accessed on August 23, 2025, [https://deepmind.google/discover/blog/alphagenome-ai-for-better-understanding-the-genome/](https://deepmind.google/discover/blog/alphagenome-ai-for-better-understanding-the-genome/)  
32. AlphaGenome: DeepMind's New AI Model for Unlocking Genome Function \- CBIRT, accessed on August 23, 2025, [https://cbirt.net/alphagenome-deepminds-new-ai-model-for-unlocking-genome-function/](https://cbirt.net/alphagenome-deepminds-new-ai-model-for-unlocking-genome-function/)  
33. Benchmarking large language models for genomic knowledge with GeneTuring \- PMC, accessed on August 23, 2025, [https://pmc.ncbi.nlm.nih.gov/articles/PMC10054955/](https://pmc.ncbi.nlm.nih.gov/articles/PMC10054955/)  
34. Medical Imaging Datasets: Complete Guide to Healthcare Data Resources (2025), accessed on August 23, 2025, [https://collectiveminds.health/articles/medical-imaging-datasets-complete-guide-to-healthcare-data-resources](https://collectiveminds.health/articles/medical-imaging-datasets-complete-guide-to-healthcare-data-resources)  
35. Benchmark Diagnostic MRI and Medical Imaging Dataset \- Mendeley Data, accessed on August 23, 2025, [https://data.mendeley.com/datasets/d73rs38yk6](https://data.mendeley.com/datasets/d73rs38yk6)  
36. Artificial Intelligence for Materials Science \- mpie.de, accessed on August 23, 2025, [https://www.mpie.de/4867299/artificial\_intelligence](https://www.mpie.de/4867299/artificial_intelligence)  
37. Essential guidelines for computational method benchmarking \- PMC \- PubMed Central, accessed on August 23, 2025, [https://pmc.ncbi.nlm.nih.gov/articles/PMC6584985/](https://pmc.ncbi.nlm.nih.gov/articles/PMC6584985/)