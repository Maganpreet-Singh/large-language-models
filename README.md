# Large Language Models — From Foundations to Transformers and LLM Systems

<div align="center">

### Learn the architecture. Implement the mathematics. Run the experiments.

![Python](https://img.shields.io/badge/Python-3.10%E2%80%933.12-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![NLP](https://img.shields.io/badge/NLP-Deep%20Learning-6A5ACD?style=for-the-badge)
![Transformers](https://img.shields.io/badge/Transformers-From%20Scratch-0A7B83?style=for-the-badge)
![Learning](https://img.shields.io/badge/Project-Educational%20%26%20Experimental-2F855A?style=for-the-badge)

**A hands-on learning repository covering attention, encoder–decoder networks, Transformer architecture, experiments, visualizations, and the wider large-language-model ecosystem.**

[Explore the repository](https://github.com/Maganpreet-Singh/large-language-models) · [Transformer notebook](https://github.com/Maganpreet-Singh/large-language-models/tree/main/Transformer) · [Encoder–Decoder experiments](https://github.com/Maganpreet-Singh/large-language-models/tree/main/Encoder%20Decoder)

</div>

---

## Contents

- [Overview](#overview)
- [What this repository is—and is not](#what-this-repository-is--and-is-not)
- [Learning objectives](#learning-objectives)
- [Repository at a glance](#repository-at-a-glance)
- [Project 1: Transformer from scratch](#project-1-transformer-from-scratch)
- [Project 2: Bahdanau and Luong attention](#project-2-bahdanau-and-luong-attention)
- [Transformer explained](#transformer-explained)
- [Attention mathematics](#attention-mathematics)
- [Encoder and decoder](#encoder-and-decoder)
- [Data and experiment design](#data-and-experiment-design)
- [Visualizations and outputs](#visualizations-and-outputs)
- [Environment setup](#environment-setup)
- [Run the notebooks](#run-the-notebooks)
- [Reproducibility and interpretation](#reproducibility-and-interpretation)
- [Troubleshooting](#troubleshooting)
- [Suggested learning path](#suggested-learning-path)
- [How to extend this repository](#how-to-extend-this-repository)
- [Responsible use and limitations](#responsible-use-and-limitations)
- [References and further study](#references-and-further-study)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## Overview

**Large Language Models** is a practical learning repository dedicated to understanding how modern language-model systems are built. It starts with sequence-to-sequence learning and attention mechanisms, then studies the Transformer architecture through notebooks, a small synthetic dataset, model artifacts, metrics, and interactive visualizations.

The goal is not to hide complexity behind a single high-level API. It is to make the moving parts visible: how text is converted into token IDs, how queries interact with keys and values, why attention scores are scaled, why decoder masking matters, how encoder and decoder blocks fit together, and how training outputs can be inspected.

The repository currently contains two major learning areas:

1. **Transformer** — a from-scratch educational encoder–decoder Transformer notebook and a self-attention notebook, together with data, reports, dependency information, and generated experiment artifacts.
2. **Encoder Decoder** — a notebook comparing Bahdanau (additive) and Luong (multiplicative) attention in a sequence-to-sequence setting, plus sample data, model files, visualizations, and CSV summaries.

Use this repository as a study companion. Read the explanations, run small experiments, inspect outputs, challenge assumptions, and change one variable at a time. The most valuable result is not a screenshot or a training score; it is being able to explain why the model behaves as it does.

> **Learning philosophy:** understand the equations, implement the components, test the assumptions, interpret the evidence, and only then scale up.

## What this repository is—and is not

### It is

- An educational implementation-focused project for students and practitioners learning deep learning and NLP.
- A place to study self-attention, scaled dot-product attention, multi-head attention, positional information, padding masks, causal masks, encoder blocks, decoder blocks, and autoregressive generation.
- A collection of small experiments that make attention behavior and model-training artifacts easier to inspect.
- A starting point for further experiments with more realistic data, pretrained models, fine-tuning, retrieval, and deployment.

### It is not

- A production-ready foundation model or a substitute for large-scale pretrained models.
- Evidence that a small synthetic dataset can teach general-purpose language understanding.
- A benchmark claim about state-of-the-art accuracy, language coverage, reasoning, or real-world translation quality.
- A guarantee that every notebook will run identically on every machine. TensorFlow, Python, hardware, package versions, notebook execution state, and random seeds can all affect outcomes.
- A claim that all listed future roadmap topics are already implemented. The repository structure and current files are the source of truth for what is currently present.

The Transformer notebook uses a **synthetic sequence dataset** to make training mechanics observable and reproducible. Synthetic tasks are useful for debugging architecture and learning the training loop, but performance on them must not be presented as real-world natural-language competence.

---

## Learning objectives

By studying and experimenting with the repository, you should aim to explain the following without relying on memorized definitions.

### Deep-learning mechanics

- What a tensor represents and how its dimensions change across a model.
- How forward propagation produces predictions and how a loss function measures error.
- How gradients flow through a computational graph during backpropagation.
- Why optimizer choice, learning rate, batch size, and initialization affect training.
- How training and validation results can reveal overfitting or underfitting.
- Why reproducibility requires more than setting one random seed.

### NLP representation

- How raw text becomes tokens and token IDs.
- Why tokenization strategy changes sequence length and vocabulary size.
- What embedding vectors represent and why learned embeddings are useful.
- Why models need information about token positions.
- How padding supports batches of unequal-length sequences.
- Why special tokens such as start-of-sequence, end-of-sequence, and padding tokens matter.

### Attention and Transformers

- How queries, keys, and values are used to compute attention.
- How scaled dot-product attention is computed.
- Why softmax converts scores into normalized weights.
- How multiple attention heads learn different projections.
- How encoder self-attention differs from decoder causal self-attention.
- How cross-attention lets a decoder use encoder representations.
- Why residual paths and layer normalization are used.
- How a feed-forward sublayer processes every sequence position.
- Why autoregressive inference differs from teacher-forced training.

### Experimental reasoning

- How to separate training metrics from test-set results.
- How to read a metric in the context of a dataset and task.
- Why token accuracy is not the same as sequence exact match.
- How to inspect attention maps without treating them as proof of explanation.
- How to compare models fairly using the same splits and evaluation procedure.
- How to report hardware, environment, data setup, hyperparameters, and limitations.

---

## Repository at a glance

The default branch is `main`. The principal project directories are shown below.

```text
large-language-models/
├── Encoder Decoder/
│   ├── Attention_Mechanisms_Bahdanau_Luong_TRAINED_COMPARISON.ipynb
│   ├── Data/
│   │   ├── Mini_English_Hindi_Attention_Dataset_DETAILED.csv
│   │   ├── attention_alignment_summary.csv
│   │   ├── bahdanau_attention_example.csv
│   │   └── luong_attention_example.csv
│   ├── Images/
│   │   └── generated attention/training/comparison figures
│   └── Tables/
│       ├── attention_summary.csv
│       ├── model_comparison.csv
│       ├── sample_predictions.csv
│       ├── sequence_evaluation.csv
│       ├── source_token_importance.csv
│       └── training_summary.csv
└── Transformer/
    ├── README.md
    ├── README_Transformer_From_Scratch.md
    ├── FINAL_REPORT_Transformer_Notebook.md
    ├── Transformer_From_Scratch_Encoder_Decoder.ipynb
    ├── self_attention.ipynb
    ├── requirements.txt
    ├── data/
    │   └── synthetic_sequences.csv
    ├── images/
    │   └── generated interactive HTML visualizations
    ├── outputs/
    │   ├── model_summary.txt
    │   └── predictions.csv
    └── transformer_from_scratch_outputs/
        ├── checkpoints/
        ├── data/
        ├── logs/
        ├── metrics/
        ├── model/
        └── plots_html/
```

This is a representative map of the principal files and folders, not an exhaustive inventory of every generated plot. Some artifact folders contain numerous HTML figures or supporting files.

### Which file should I open first?

| Goal | Recommended starting point |
|---|---|
| Understand the overall project | This root README |
| Study a complete encoder–decoder Transformer | [Transformer notebook](Transformer/Transformer_From_Scratch_Encoder_Decoder.ipynb) |
| Focus on self-attention concepts | [Self-attention notebook](Transformer/self_attention.ipynb) |
| Read the Transformer setup and output details | [Transformer project README](Transformer/README.md) |
| Review the notebook deliverables and stated verification limits | [Final build report](Transformer/FINAL_REPORT_Transformer_Notebook.md) |
| Compare additive and multiplicative attention | [Bahdanau vs. Luong notebook](Encoder%20Decoder/Attention_Mechanisms_Bahdanau_Luong_TRAINED_COMPARISON.ipynb) |
| Inspect the attention experiment metrics | [Model comparison CSV](Encoder%20Decoder/Tables/model_comparison.csv) |
| Inspect a compact Transformer dataset | [Synthetic sequence data](Transformer/data/synthetic_sequences.csv) |

GitHub can preview many Jupyter notebooks directly in the browser. For an interactive run, download or clone the repository and open the notebook in Jupyter or Google Colab.

---

## Project 1: Transformer from scratch

**Location:** [`Transformer/`](Transformer/)

The central project is an educational implementation of a Transformer encoder–decoder. The notebook is designed to expose the architecture and training process rather than simply loading a pretrained model and calling `generate()`.

### Main notebook

[`Transformer_From_Scratch_Encoder_Decoder.ipynb`](Transformer/Transformer_From_Scratch_Encoder_Decoder.ipynb)

The documented notebook implementation areas include:

- Synthetic dataset generation and train/validation/test splitting.
- Source and target vocabularies fitted using training data.
- Token and positional representations.
- Scaled dot-product attention.
- Custom multi-head attention.
- Sinusoidal positional encoding.
- Source padding masks, target padding masks, and causal masks.
- Encoder blocks and decoder blocks.
- Cross-attention from decoder states to encoder outputs.
- Teacher-forced training.
- Padding-aware sparse cross-entropy.
- A custom training loop with a warm-up learning-rate schedule.
- Gradient clipping.
- Validation-based checkpoint selection and early stopping.
- Greedy autoregressive decoding for evaluation.
- Per-task metrics, parameter analysis, attention figures, and predictions.
- Saved model configuration, vocabularies, weights, metrics, and HTML plots.
- Structural checks and optional small-batch or ablation experiments.

These are the areas documented for the notebook; execution and numerical results still depend on running it in a compatible environment. Read the project's [final build report](Transformer/FINAL_REPORT_Transformer_Notebook.md) for the recorded verification limitation.

### Self-attention notebook

[`self_attention.ipynb`](Transformer/self_attention.ipynb)

This notebook is a more focused entry point for learning how tokens exchange contextual information through attention. Use it before tackling a full encoder–decoder if you are still building intuition for the query, key, and value projections.

Suggested questions to investigate while reading:

1. What are the dimensions of (Q), (K), and (V)?
2. Why do we compute (QK^T)?
3. What changes when the key dimension grows?
4. What role does the scale factor play?
5. What does a row of attention weights mean?
6. How does a mask change the output?
7. What information is preserved by the weighted sum of values?
8. How does the multi-head version differ from a single head?

### Supporting artifacts

The Transformer project includes files intended to make experiments inspectable:

| Path | Purpose |
|---|---|
| `Transformer/data/synthetic_sequences.csv` | Synthetic sequence records used by the project |
| `Transformer/requirements.txt` | Python package constraints for the notebook |
| `Transformer/README_Transformer_From_Scratch.md` | Project-specific usage and output notes |
| `Transformer/FINAL_REPORT_Transformer_Notebook.md` | Notebook deliverables and verification caveats |
| `Transformer/transformer_from_scratch_outputs/checkpoints/` | Saved model weights, where generated |
| `Transformer/transformer_from_scratch_outputs/model/` | Configuration and source/target vocabulary artifacts |
| `Transformer/transformer_from_scratch_outputs/metrics/` | Metric files, prediction files, and training history |
| `Transformer/transformer_from_scratch_outputs/logs/` | Training summary files |
| `Transformer/transformer_from_scratch_outputs/plots_html/` | Interactive HTML visualizations |

Generated output folders should be treated as experiment artifacts, not permanent guarantees of quality. If code, data, library versions, or random seeds change, regenerate artifacts and keep their provenance clear.

---

## Project 2: Bahdanau and Luong attention

**Location:** [`Encoder Decoder/`](Encoder%20Decoder/)

This project compares two influential attention mechanisms used in sequence-to-sequence encoder–decoder models:

- **Bahdanau attention**, commonly described as additive attention.
- **Luong attention**, commonly described as multiplicative or dot-product-style attention.

Notebook: [`Attention_Mechanisms_Bahdanau_Luong_TRAINED_COMPARISON.ipynb`](Encoder%20Decoder/Attention_Mechanisms_Bahdanau_Luong_TRAINED_COMPARISON.ipynb)

### What the comparison is useful for

The experiment can help you examine how a decoder aligns its current state with encoder outputs, how attention weights are distributed over source tokens, how model size and training time differ in a particular implementation, and how token-level metrics compare.

The directory includes a small English–Hindi-style educational dataset, examples and summaries in CSV form, saved PyTorch model artifacts, visualizations, and comparison tables. Review the notebook's own dataset construction and code before making claims about the coverage or quality of the data.

### Additive attention: concept

A typical additive attention score combines a transformed decoder state with a transformed encoder state, applies a nonlinearity, and projects the result to a scalar score. The scores are normalized to weights and used to form a weighted context vector.

One common mathematical form is:

[
e_{t,i}=v_a^{T}\tanh(W_hh_i+W_ss_{t-1})
]

[
\alpha_{t,i}=\frac{\exp(e_{t,i})}{\sum_j\exp(e_{t,j})}
]

[
c_t=\sum_i\alpha_{t,i}h_i
]

Notation varies between papers and implementations. Here (h_i) is an encoder state, (s_{t-1}) is a decoder state, (alpha_{t,i}) is the normalized attention weight, and (c_t) is the context vector for a decoding step.

### Multiplicative attention: concept

A common dot-product score is:

[
e_{t,i}=s_t^{T}h_i
]

A general bilinear variant introduces a learned matrix:

[
e_{t,i}=s_t^{T}W_ah_i
]

The exact scoring variant should be read from the notebook's implementation. “Luong attention” can refer to more than one scoring option, so do not assume all multiplicative variants are identical.

### Existing comparison summary

The checked-in `Encoder Decoder/Tables/model_comparison.csv` records the following values for a particular run:

| Metric | Bahdanau | Luong |
|---|---:|---:|
| Best validation loss | 2.5035 | 2.6602 |
| Best validation accuracy | 0.4667 | 0.4667 |
| Training time (seconds) | 3.7086 | 1.5368 |
| Parameter count | 232,645 | 216,133 |
| Exact match | 0.0000 | 0.0000 |
| Token precision | 0.2500 | 0.2917 |
| Token recall | 0.2708 | 0.3125 |
| Token F1 | 0.2583 | 0.3000 |
| Attention entropy | 0.8219 | 0.9858 |
| Maximum attention weight | 0.5927 | 0.5170 |

**How to interpret these numbers:** they describe a specific experiment and should not be generalized into a universal ranking of the mechanisms. The reported exact-match score is zero for both models in that run, so the token-level values should not be mistaken for successful whole-sequence translation. Training times are hardware- and runtime-dependent. If you compare updated runs, record the environment and keep data splits, tokenization, training budget, and evaluation methods aligned.

### Useful files

- [Model comparison table](Encoder%20Decoder/Tables/model_comparison.csv)
- [Training summary](Encoder%20Decoder/Tables/training_summary.csv)
- [Sequence evaluation](Encoder%20Decoder/Tables/sequence_evaluation.csv)
- [Sample predictions](Encoder%20Decoder/Tables/sample_predictions.csv)
- [Attention summary](Encoder%20Decoder/Tables/attention_summary.csv)
- [Dataset](Encoder%20Decoder/Data/Mini_English_Hindi_Attention_Dataset_DETAILED.csv)

---

## Transformer explained

This section offers a concise conceptual guide to the major pieces represented in the notebooks. The notebooks remain the best place to inspect code-level details.

### From tokens to contextual representations

A Transformer processes batches of token IDs. An embedding table maps each token ID to a vector. Since attention by itself does not inherently encode the order of tokens, positional information is added to the token representation.

A high-level view:

```text
Text
  ↓
Tokenizer and vocabulary
  ↓
Token IDs + padding
  ↓
Token embeddings + positional information
  ↓
Encoder / decoder stack
  ↓
Contextual representations
  ↓
Projection to vocabulary logits
  ↓
Token probabilities
```

The actual data path depends on the task. An encoder-only architecture, a decoder-only language model, and an encoder–decoder model have different objectives and masking requirements.

### Query, key, and value

Attention uses learned projections of an input representation:

- **Query (Q):** the information a position uses to ask what it should attend to.
- **Key (K):** the representation used to score how relevant a position is to a query.
- **Value (V):** the content aggregated according to the attention weights.

These are computational roles, not literal questions or labels stored in the data. The projections are learned during training.

### Scaled dot-product attention

The fundamental operation is:

[
\operatorname{Attention}(Q,K,V)=\operatorname{softmax}\left(\frac{QK^T}{\sqrt{d_k}}+M\right)V
]

Where:

- (QK^T) produces similarity scores between query positions and key positions.
- (d_k) is the key-vector dimension used for scaling.
- (M) is an optional additive mask; disallowed positions receive a large negative value before softmax.
- Softmax produces normalized weights along the attention axis.
- Multiplication by (V) returns a weighted combination of value vectors.

The scale (1/\sqrt{d_k}) helps control score magnitude as the dimension changes, which can make optimization more stable. Implementations must take care with mask shapes, broadcasting, numerical stability, and the axis along which softmax is applied.

### Multi-head attention

Instead of running one attention operation in one representation space, multi-head attention creates multiple learned projections and performs attention in parallel. The results are concatenated and transformed by an output projection.

[
\operatorname{MultiHead}(Q,K,V)=\operatorname{Concat}(head_1,\ldots,head_h)W^O
]

Each head uses learned projection matrices for queries, keys, and values. Multiple heads give the model opportunities to represent different relationships, but they do not guarantee that each head will learn a clean, human-interpretable linguistic role.

### Positional information

Sinusoidal positional encoding is one approach to representing token positions. It creates deterministic position-dependent values at different frequencies. Other Transformers use learned positional embeddings or alternative position representations.

For the classic sinusoidal formulation:

[
PE(pos,2i)=\sin\left(\frac{pos}{10000^{2i/d_{model}}}\right)
]

[
PE(pos,2i+1)=\cos\left(\frac{pos}{10000^{2i/d_{model}}}\right)
]

The precise implementation should be checked against the notebook, particularly the handling of odd embedding dimensions, dtype, maximum sequence length, and broadcasting.

### Encoder block

A classic encoder layer includes self-attention and a position-wise feed-forward network, along with residual connections and layer normalization. Some implementations use post-normalization; others use pre-normalization. Those choices are not interchangeable implementation details and can affect optimization.

Conceptually:

```text
Input representations
   ↓
Multi-head self-attention
   ↓
Residual path + normalization
   ↓
Position-wise feed-forward network
   ↓
Residual path + normalization
   ↓
Output representations
```

Padding masks are important: padded source positions should not be treated as meaningful content when constructing attention over a batch.

### Decoder block

A classic encoder–decoder Transformer decoder uses:

1. **Masked self-attention** so a token does not access future target tokens.
2. **Cross-attention** so decoder positions can attend to the encoder outputs.
3. **Feed-forward processing**, residual connections, and normalization.

```text
Shifted target tokens
   ↓
Causal self-attention
   ↓
Residual path + normalization
   ↓
Cross-attention over encoder output
   ↓
Residual path + normalization
   ↓
Feed-forward network
   ↓
Residual path + normalization
   ↓
Vocabulary logits
```

A causal mask and a padding mask solve different problems. The causal mask prevents looking ahead in the target; the padding mask ignores padded positions. Correctly combining them is one of the most important implementation details to test.

### Teacher forcing and autoregressive inference

During teacher-forced training, the decoder is given the known target sequence shifted so it predicts the next token at each position. At inference, the target is not known in advance: the model generates one token, appends it to the decoder input, and continues until an end token or length limit is reached.

This difference matters. A good teacher-forced token-level metric does not automatically guarantee equally good free-running generation. Greedy decoding chooses the best next token at each step but is not necessarily globally optimal; beam search and sampling are alternative strategies with their own trade-offs.

---

## Attention mathematics

This section summarizes common shapes and operations that help when debugging a custom implementation.

Let:

- (B) = batch size
- (T_q) = query sequence length
- (T_k) = key/value sequence length
- (d_{model}) = model width
- (h) = number of attention heads
- (d_k) = per-head query/key width
- (d_v) = per-head value width

A common tensor layout for a single head is:

| Tensor | Typical shape |
|---|---|
| Queries | ((B,T_q,d_k)) |
| Keys | ((B,T_k,d_k)) |
| Values | ((B,T_k,d_v)) |
| Scores | ((B,T_q,T_k)) |
| Attention weights | ((B,T_q,T_k)) |
| Context output | ((B,T_q,d_v)) |

For multi-head attention, the head dimension is often represented explicitly as ((B,h,T,d_{head})), though frameworks can rearrange dimensions internally.

### Common implementation errors

- Multiplying tensors in the wrong order so the score tensor has the wrong axes.
- Scaling by the model width when the intended formula uses the per-head key dimension.
- Applying softmax along the query axis rather than over keys.
- Creating masks with incorrect rank or incompatible broadcast dimensions.
- Using a padding mask that suppresses valid tokens or fails to suppress padding.
- Forgetting the causal mask during decoder training.
- Using target labels that are not shifted relative to decoder inputs.
- Including padding positions in the loss or metrics unintentionally.
- Mixing sequence-first and batch-first tensor layouts.
- Assuming a visualization is correct because it renders without an exception.

When debugging, print shapes and dtypes at every major boundary. Use a tiny batch and a short sequence before training a full experiment. Validate simple invariants: attention weights over allowed positions should sum approximately to one; masked probabilities should be effectively zero; output dimensions should match the expected architecture; losses should be finite.

---

## Encoder and decoder

An encoder–decoder is useful for tasks where an input sequence conditions an output sequence, such as translation, summarization, and structured transformation. The architecture is general, but the quality of the results depends heavily on data coverage, model capacity, training procedure, and evaluation.

### Encoder responsibilities

- Convert the source sequence to contextual states.
- Allow valid source positions to exchange information through self-attention.
- Keep padded tokens from influencing valid sequence computations as intended.
- Return representations consumed by decoder cross-attention.

### Decoder responsibilities

- Represent previously available target tokens.
- Prevent information leakage from future target positions.
- Attend to encoder states where the architecture uses cross-attention.
- Produce logits over the target vocabulary for each next-token prediction.

### Vocabulary considerations

Source and target vocabularies may be independent. Special token IDs should be consistent throughout preprocessing, training, decoding, and saved artifacts. Build vocabularies using the training split only to avoid leakage from validation/test data. For real applications, subword tokenizers often offer better coverage and bounded vocabulary size than naive word tokenization, but tokenizer selection should follow the task.

### Why synthetic data is useful—and limited

Synthetic records can be generated quickly and can encode patterns that are easy to test. That makes them valuable for verifying whether an implementation can learn a known mapping. But synthetic data can also make tasks unusually regular or simplistic. It does not capture the diversity, ambiguity, noise, long-tail vocabulary, discourse, and cultural context found in natural language.

Use synthetic experiments to validate code and build intuition. Use suitable real-world data and carefully selected metrics to support claims about real-world performance.

---

## Data and experiment design

Reliable model experiments require disciplined data handling. A plausible-looking chart is not enough.

### Train, validation, and test splits

- **Training set:** used to optimize model parameters.
- **Validation set:** used for model selection, hyperparameter tuning, and early stopping.
- **Test set:** reserved for a final estimate after choices have been made.

Do not keep tuning to the test set and then report it as an untouched final evaluation. If the data is small, describe the uncertainty and consider suitable cross-validation or repeated-run analysis where appropriate.

### Vocabulary leakage

If a vocabulary or preprocessing statistic is derived from the full dataset before splitting, information from the validation/test sets can leak into training. Fit learned preprocessing artifacts only on the training split, then apply them to the other splits. The same principle applies to normalization statistics, feature selection, and learned encoders.

### Loss and metrics

A training loss measures the objective being optimized. It is not automatically a user-facing quality metric.

- **Token accuracy:** the fraction of evaluated token positions predicted correctly, subject to the implementation's masking rules.
- **Exact sequence match:** whether an entire predicted sequence matches the reference sequence under the specified normalization.
- **Precision / recall / F1:** require a clear definition of what counts as a positive token or event; explain the aggregation method.
- **Perplexity:** a language-model metric derived from average negative log-likelihood, meaningful only with clear tokenization and evaluation conventions.
- **Attention entropy:** summarizes the concentration or spread of a normalized attention distribution; it is not a direct measure of correctness.
- **Training duration:** depends on runtime, device, batching, implementation, package versions, and workload.

Always state whether padding and special tokens are included in metric calculations. For sequence generation, show representative successes and failures alongside aggregate numbers.

### Compare experiments fairly

For a comparison to support a useful conclusion, control or report:

- Dataset version and exact split.
- Tokenization and vocabulary construction.
- Model dimension, layer count, head count, and parameter count.
- Optimizer, learning rate schedule, batch size, epoch budget, and early-stopping condition.
- Random seeds and whether results are from one run or repeated runs.
- Hardware, accelerator use, package versions, and timing method.
- Decoding method and maximum generation length.
- Metric definitions, padding treatment, and text normalization.

Avoid calling a method “better” based only on a single score or a tiny synthetic sample. Phrase conclusions narrowly and identify what remains untested.

---

## Visualizations and outputs

The Transformer project stores numerous visualizations as HTML files under `Transformer/transformer_from_scratch_outputs/plots_html/` and additional figures under `Transformer/images/`. The Encoder Decoder experiments store PNG plots and CSV tables under their corresponding subfolders.

Depending on which notebook cells have been run, the files can include:

- Architecture and data-flow diagrams.
- Attention score, scaled-score, and attention-probability illustrations.
- Per-head encoder, decoder, and cross-attention views.
- Positional encoding curves and heatmaps.
- Embedding visualizations.
- Padding and causal mask diagrams.
- Dataset and sequence-length distributions.
- Training dashboards and learning curves.
- Parameter counts and parameter distributions.
- Error-analysis examples and model predictions.
- Comparisons across selected ablations.

### Open interactive HTML plots

1. Navigate to the relevant `plots_html` or `images` directory.
2. Open an HTML file in a browser, or download it from GitHub and open it locally.
3. If a plot uses an external JavaScript resource, an internet connection may be required depending on how the figure was exported.
4. If an HTML file is empty or very small, treat it as an unavailable artifact and regenerate the relevant plot from the notebook. Do not assume that a filename alone proves the plot was successfully created.

Some generated HTML plots can be several megabytes each. Consider using Git LFS or publishing selected, compressed artifacts rather than committing every duplicated interactive figure if repository size becomes a problem.

### Read the saved metrics

CSV and JSON files are useful for filtering, plotting, and comparing runs. Read the notebook and report to confirm what each field means. Never infer an undocumented metric definition solely from its filename.

When sharing an experiment publicly, include the model configuration, data setup, the command/notebook section used, environment, and limitations with the charts. A plot is more useful when another person can reproduce its meaning.

---

## Environment setup

The Transformer project provides a `requirements.txt` with recommended Python version guidance. The checked-in file currently recommends **Python 3.10–3.12** and includes TensorFlow plus numerical, plotting, notebook, and evaluation packages. The encoder–decoder attention notebook also contains saved PyTorch artifacts; those should be handled in an environment with a compatible PyTorch installation if you plan to reload them.

Dependency compatibility changes over time, so create an isolated environment rather than installing project dependencies into a global Python installation.

### 1. Clone the repository

```bash
git clone https://github.com/Maganpreet-Singh/large-language-models.git
cd large-language-models
```

### 2. Create a virtual environment

**Windows PowerShell**

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
```

If Python 3.12 is not installed, install a compatible Python release first and confirm it with `py --list`. If PowerShell blocks activation due to local policy, you may activate the environment using Command Prompt's `.venv\Scripts\activate.bat` instead; avoid changing machine-wide policy unnecessarily.

**macOS / Linux**

```bash
python3.12 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

### 3. Install Transformer notebook dependencies

```bash
python -m pip install -r "Transformer/requirements.txt"
```

If installation fails, check the exact Python version and the package's wheel support for your operating system and hardware. TensorFlow's supported Python and accelerator combinations vary across releases. Do not blindly upgrade every package to its newest major version when the project specifies bounded requirements.

### 4. Install PyTorch for the attention comparison (if needed)

The Encoder Decoder directory contains `.pt` model artifacts. Install a PyTorch build appropriate for your operating system and CPU/GPU configuration by following the official [PyTorch installation selector](https://pytorch.org/get-started/locally/). Then verify the install:

```bash
python -c "import torch; print(torch.__version__); print(torch.cuda.is_available())"
```

The `cuda.is_available()` output only indicates whether CUDA is available to that PyTorch installation at runtime; `False` does not prevent CPU execution.

### 5. Start Jupyter

```bash
python -m pip install jupyter
jupyter lab
```

Then open the notebook you want to study. Alternatively, use VS Code with its Python and Jupyter extensions.

### Google Colab

Colab can be convenient when a supported local TensorFlow setup or a GPU is not available. Upload the notebook or open it from GitHub, select a runtime, install the dependencies required by that notebook, and run cells in order. Runtime package versions may differ from the local environment, so record the version details for any results you share.

### Check versions

```bash
python --version
python -m pip show tensorflow numpy pandas plotly scikit-learn
```

For a concise environment report:

```python
import sys
print("Python:", sys.version)

try:
    import tensorflow as tf
    print("TensorFlow:", tf.__version__)
    print("Visible GPUs:", tf.config.list_physical_devices("GPU"))
except ImportError:
    print("TensorFlow is not installed in this environment.")
```

---

## Run the notebooks

### Run the complete Transformer notebook

1. Clone the repository.
2. Create and activate a virtual environment.
3. Install `Transformer/requirements.txt`.
4. Open `Transformer/Transformer_From_Scratch_Encoder_Decoder.ipynb`.
5. Read the introduction, configuration, and dataset sections before executing the training cells.
6. Run cells in notebook order.
7. Confirm that paths point to the expected project folders and that checkpoints/metrics are saved to the intended output directory.
8. Inspect training and validation curves before evaluating the final model.
9. Review the generated predictions and errors, not just the headline score.
10. Open the resulting HTML visualizations in a browser.

### Run the self-attention notebook

Open `Transformer/self_attention.ipynb` and focus on the data flow through the Q/K/V projections, score scaling, masks, softmax, and weighted values. Use very short inputs so you can manually verify calculations.

### Run the Bahdanau vs. Luong notebook

Open `Encoder Decoder/Attention_Mechanisms_Bahdanau_Luong_TRAINED_COMPARISON.ipynb`. Review the code that constructs the data, builds each attention model, trains them, computes metrics, and saves the comparison files. Ensure PyTorch and other notebook-specific dependencies are installed.

### Rerunning vs. inspecting existing outputs

- **Inspect existing outputs** when you want to understand artifacts already committed to the repository.
- **Rerun the notebook** when you want to verify the current code, regenerate figures, or produce metrics for a new environment.
- **Keep runs separate** when changing hyperparameters, code, data, or seeds. Record the configuration so an old output is not mistaken for a result from a newer run.
- **Avoid trusting stale checkpoints** if their architecture or vocabulary differs from your current notebook code.

Notebooks can contain stale cell output or an older state than the source code. For reproducible experiments, restart the kernel and run the notebook top-to-bottom in a clean environment.

---

## Reproducibility and interpretation

The Transformer notebook's final report states that its structure was generated and statically checked, but the build runtime did not have TensorFlow installed. As a result, the complete model forward pass, training, checkpoint creation, evaluation, and model-derived figures were **not executed in that build environment**. The notebook is intended to produce its metrics and model artifacts when run in a compatible TensorFlow environment.

This matters because checking that a notebook file is valid JSON or that code parses is not the same as verifying that training succeeds. Treat the report as a transparent boundary on what was verified, not as a claim of end-to-end execution.

For your own run, capture a small experiment record containing:

```text
Run name:
Date/time:
Git commit:
Python version:
OS and hardware:
TensorFlow / PyTorch versions:
Dataset files and split:
Random seed(s):
Model configuration:
Training configuration:
Best validation checkpoint:
Final test metrics:
Known errors or limitations:
```

### Suggested experiment log

| Experiment | Change | Hypothesis | Evidence to record |
|---|---|---|---|
| Baseline | Existing configuration | Establish a reference | Loss, metrics, runtime, model size |
| Head count | Change attention heads | Test representation trade-off | Validation score, runtime, parameter count |
| Embedding dimension | Change model width | Test capacity vs. cost | Loss curves, memory, metrics |
| Sequence length | Change maximum length | Test context effects | Runtime, truncation, task metrics |
| Masking | Verify/ablate masks carefully | Test leakage and padding behavior | Invariant checks, metrics |
| Learning rate | Change schedule values | Test optimization behavior | Stability, convergence, validation loss |
| Dataset size | Add controlled data | Test whether results scale with examples | Learning curves and generalization |

Ablations should be scientifically controlled. For example, changing embedding dimension also changes parameter count and compute; these effects should be reported rather than attributed to a single cause.

---

## Troubleshooting

### TensorFlow will not install

- Confirm that the active interpreter is the Python version you intended to use.
- Run `python -m pip --version` to ensure pip belongs to that interpreter.
- Use the package constraints in `Transformer/requirements.txt`.
- Check TensorFlow's current platform support and available wheels for the selected Python version.
- Avoid mixing conda and venv environments unless you know which interpreter is running the notebook kernel.
- Restart VS Code or Jupyter and select the kernel from the environment where dependencies were installed.

### The notebook imports packages in one terminal but not in Jupyter

The terminal and notebook may be using different interpreters. Install `ipykernel` into the virtual environment and register/select that environment as the notebook kernel. Check `sys.executable` from inside the notebook.

### Out-of-memory errors

- Reduce the batch size.
- Reduce sequence length or embedding dimension for a learning run.
- Close other processes using GPU memory.
- Use a smaller synthetic dataset while debugging.
- Avoid rendering or retaining many large interactive figures at once.
- Confirm that the notebook is not accidentally retaining tensors or duplicate model instances.

These changes alter the experiment, so record them when reporting the results.

### A mask has the wrong shape

Write down the shape of the scores tensor and the intended mask semantics. Determine which axis represents batch, head, query, and key. Check whether the framework expects a boolean mask, an additive mask, or a particular polarity. Add small tests with a sequence where the expected masked positions are obvious.

### The loss becomes NaN or infinite

Check inputs for invalid values, confirm that target IDs are in vocabulary bounds, inspect loss masking, review the learning rate, and ensure the score/softmax calculation is numerically stable. Try one tiny batch and verify a single forward/backward step before restarting a large run.

### Training runs but predictions are poor

Possible causes include a toy dataset with weak signal, too few training steps, an inappropriate decoding path, source/target token misalignment, inconsistent special-token IDs, incorrect target shifting, a mask bug, or a metric that does not match the task. Inspect individual predictions and compare them with the actual mapping/task before increasing model size.

### GitHub notebook preview fails

Download the notebook and open it locally, or use Google Colab's GitHub import flow. Oversized output cells can make previews slow; clearing and rerunning output locally may help. Preserve any outputs that are important evidence before clearing them.

### An interactive plot appears blank

Confirm that the HTML file is not empty, then regenerate the figure from the relevant notebook cell. Depending on how the HTML was exported, its JavaScript dependencies may require an internet connection. A plot path being present in the directory is not proof that the plot contains valid data.

### Checkpoint loading fails

Verify that the model architecture, TensorFlow/PyTorch version, expected file format, and vocabulary/configuration match the checkpoint. A weights file alone may not contain all architecture metadata. Avoid loading an untrusted model artifact from an unknown source.

---

## Suggested learning path

The repository is easier to understand if you approach it in layers.

### Stage 1 — Build the mental model

Review embeddings, tensor shapes, matrix multiplication, softmax, gradients, loss functions, and train/validation/test splits. If a concept is unclear, pause and implement it as a tiny standalone example.

### Stage 2 — Learn attention in isolation

Open the self-attention notebook. Work through Q/K/V projections, score matrices, scaling, masking, and weighted aggregation. Use tiny matrices whose results you can calculate by hand.

### Stage 3 — Study sequence-to-sequence attention

Open the Bahdanau/Luong notebook. Compare how each score function produces alignment weights and a context vector. Separate architectural behavior from data limitations and training-budget effects.

### Stage 4 — Trace the full Transformer

Read the encoder–decoder notebook section by section: data preparation, vocabulary creation, embeddings and positions, attention layers, masking, residual paths, feed-forward layers, loss, training, checkpointing, and inference.

### Stage 5 — Run and explain an experiment

Run a baseline from a clean kernel. Explain the loss curve, inspect predictions, verify masks, and state the limitations. Change one hyperparameter at a time and preserve the previous run's record.

### Stage 6 — Move toward realistic tasks

After you understand the educational implementation, use a well-documented dataset with appropriate licensing and evaluation. Compare the small custom implementation with a suitable pretrained model. Account for compute needs, training data, tokenizer choices, and task-specific metrics.

### Stage 7 — Explore LLM application engineering

A natural progression beyond this repository is:

- Tokenization and pretrained model inference.
- Fine-tuning and parameter-efficient methods such as LoRA, where appropriate.
- Embedding-based semantic retrieval.
- Retrieval-Augmented Generation (RAG).
- Evaluation of grounding, factuality, latency, and cost.
- Basic serving, monitoring, and safety checks.

These are recommended next steps, not a statement that each topic already has an implementation in the current repository.

---

## How to extend this repository

Good contributions make the experiments clearer, more reproducible, and easier to verify.

### Technical extensions

- Add unit tests for attention shapes, mask behavior, and padding invariants.
- Add a tiny deterministic numerical example that validates the attention output.
- Compare greedy decoding with beam search on an explicitly defined evaluation set.
- Add a clearly documented real-data experiment with dataset provenance and license.
- Include per-run configuration files and environment snapshots.
- Separate source code from generated model outputs.
- Add CI that validates notebook JSON and performs lightweight import or structural checks.
- Add memory/runtime profiling for CPU and GPU runs.
- Add a clear model card for any trained model artifact that is intended for reuse.
- Improve HTML artifact handling to avoid committing empty plots or duplicate bulky files.

### Documentation extensions

- Add a glossary of symbols and tensor dimensions.
- Link every visualization to the notebook cell or code path that generated it.
- Explain how every metric is calculated and whether padding/special tokens are excluded.
- Include a “known limitations” subsection for each experiment.
- Add a quick-start cell for each notebook that verifies dependencies and output paths.
- Keep the root README focused on navigation, goals, architecture, and reproducibility; place long implementation details in project-specific documentation.

### Data and model hygiene

- Document the origin, license, construction, and intended use of each dataset.
- Never commit API keys, credentials, private data, or sensitive training samples.
- Avoid committing large model checkpoints unless there is a clear reason.
- Use Git LFS or external artifact storage when appropriate, and document access instructions.
- Treat model artifacts as untrusted inputs until their source and expected format are understood.

---

## Responsible use and limitations

This repository is intended for education and experimentation. A small model trained on synthetic data can help validate learning code, but it cannot establish robust language ability, fairness, factual accuracy, security, or suitability for deployment.

When moving from experiments to applications:

- Respect dataset, model, and software licenses.
- Avoid including sensitive or personally identifiable information in data, outputs, notebooks, and logs.
- Evaluate errors and failure modes rather than relying on averages alone.
- Clearly disclose the model, dataset, and limitations when sharing outputs.
- Do not assume that attention weights are faithful explanations of every model decision.
- Treat generated content as model output that may be incomplete or wrong.
- Do not deploy a system in a high-stakes setting based solely on a small learning experiment.

---

## References and further study

The following primary resources are useful for deepening your understanding. Read the original papers for the mathematical formulation and use modern framework documentation for current APIs.

### Papers

1. **Attention Is All You Need** — Vaswani et al. (2017). Introduces the Transformer architecture.  
   https://arxiv.org/abs/1706.03762
2. **Neural Machine Translation by Jointly Learning to Align and Translate** — Bahdanau, Cho, and Bengio (2014/2015). Introduces learned attention for neural machine translation.  
   https://arxiv.org/abs/1409.0473
3. **Effective Approaches to Attention-based Neural Machine Translation** — Luong, Pham, and Manning (2015). Studies attention scoring variants and input-feeding.  
   https://arxiv.org/abs/1508.04025
4. **BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding** — Devlin et al. (2018/2019).  
   https://arxiv.org/abs/1810.04805
5. **Language Models are Few-Shot Learners** — Brown et al. (2020).  
   https://arxiv.org/abs/2005.14165

### Framework and tooling documentation

- TensorFlow: https://www.tensorflow.org/learn
- Keras: https://keras.io/
- PyTorch: https://pytorch.org/docs/stable/
- Hugging Face Transformers: https://huggingface.co/docs/transformers
- Hugging Face Datasets: https://huggingface.co/docs/datasets
- Jupyter: https://jupyter.org/documentation
- Google Colab: https://colab.research.google.com/
- Git LFS: https://git-lfs.com/

Links are provided as starting points; library APIs and compatibility requirements can change over time.

---

## Contributing

Contributions are welcome when they make the project more correct, transparent, reproducible, or educational.

1. Fork the repository.
2. Create a focused feature branch.
3. Keep notebook outputs purposeful and avoid committing accidental, massive output dumps.
4. Add or update documentation when behavior changes.
5. Run the relevant notebook or tests in a compatible environment.
6. Include the environment details and steps used to verify any claimed result.
7. Submit a pull request with a concise summary, rationale, and known limitations.

For architecture or metric changes, show what changed and how it was evaluated. Do not report an experiment as executed if only static validation has been performed.

---

## License

No root-level license file was verified while preparing this README. Unless the repository adds a license, assume the default copyright rules apply and do not assume that others have permission to reuse, redistribute, or relicense the code. Add an appropriate license file if you intend to permit reuse.

---

## Author

**Maganpreet Singh**

Repository: https://github.com/Maganpreet-Singh/large-language-models

This repository is a growing study of the ideas and engineering behind attention and Transformer models. The best way to use it is to stay curious, check the math, inspect the tensors, reproduce the results, and keep the conclusions honest.

<div align="center">

**Understand the internals. Build with intention. Verify the evidence.**

</div>
