# Kontrast Dataset
* Paper: [Evaluating GPT’s Ability to Understand Syntactic Minimal Pairs in Korean](https://doi.org/10.29403/LI.28.3.5)
* Authors: [Jina Song](https://english.hongik.ac.kr/english/0201.do?mode=view&deptCd=AAD140&S1=2024&S2=10024), [Eunbi Cho](https://github.com/EunB2), [Sanghoun Song](http://corpus.mireene.com/)
* [HuggingFace](https://huggingface.co/datasets/EunB2/Kontrast-ForcedChoice_160pairs)🤗

This dataset, **Kontrast**, contains Korean syntactic minimal pairs used to evaluate the syntactic competence of large language models (LLMs), including GPT-3.5, GPT-4, and GPT-4o.

## Main Concept
The dataset consists of **syntactic minimal pairs**, where each pair includes:
* **An acceptable sentence**
* **A less acceptable sentence** (due to a syntactic violation)

These pairs help assess whether language models align with **native Korean speaker judgments** regarding syntactic acceptability.

## Data Description
This dataset consists of three subsets based on different experimental tasks:

1. **Forced Choice Task (`ForcedChoice_160pairs.xlsx`)**
   - **160 sentence pairs** where one sentence is grammatically more acceptable than the other.
   - The model is asked to choose the more acceptable sentence.
   - **Columns:**
     - `id`: Unique identifier for the sentence pair.
     - `sentence_A`: The more acceptable sentence.
     - `sentence_B`: The less acceptable sentence.
     - `gold_label`: Correct answer (either `A` or `B`).

2. **Yes/No Task (`YesNo_320sentences.xlsx`)**
   - **320 individual sentences** labeled as acceptable (`예`) or unacceptable (`아니오`).
   - The model is asked to determine whether each sentence is acceptable.
   - **Columns:**
     - `id`: Unique identifier for each sentence.
     - `sentence`: The sentence being evaluated.
     - `gold_label`: Acceptability judgment (`예` or `아니오`).

3. **Likert Scale Task (`LikertScale_320sentences.xlsx`)**
   - **320 individual sentences**, each rated based on **acceptability judgments** by human annotators.
   - The model assigns a score between **1 and 5**, where:
     - **1 = 전혀 수용 불가능함 (Totally unacceptable)**
     - **2 = 수용 불가능함 (Unacceptable)**
     - **3 = 보통임 (Neutral)**
     - **4 = 수용 가능함 (Acceptable)**
     - **5 = 매우 수용 가능함 (Very acceptable)**
   - **Columns:**
     - `id`: Unique identifier for each sentence.
     - `sentence`: The sentence being evaluated.
     - `gold_label`: Acceptability judgment (`정문` or `비문`).

### Example Data
#### **Forced Choice Task**
| ID | Acceptable Sentence (A) | Less Acceptable Sentence (B) | Correct Answer |
|----|-------------------------|-----------------------------|----------------|
| 1  | 서울은 한국의 수도이다. | 서울은 한국의 수도뿐이다. | A |
| 2  | 철수가 어제 준 것은 영희에게 책이야. | 철수가 어제 영희에게 준 것은 책이야. | B |

#### **Yes/No Task**
| ID | Sentence | Judgment |
|----|---------|----------|
| 1  | 철수가 어제 영희에게 준 것은 책이야. | 예 |
| 2  | 빈번히 일어나는 유괴 사건이 우리를 슬펐게 한다. | 아니오 |

#### **Likert Scale Task**
| ID | Sentence | Judgment |
|----|---------|----------|
| 1  | 서울은 한국의 수도이다. | 정문 |
| 2  | 영이가 예쁘지 않고 있다. | 비문 |

## Citation
```
@article{song2024evaluating,
  author    = {Jina Song and Eunbi Cho and Sanghoun Song},
  title     = {Evaluating GPT’s Ability to Understand Syntactic Minimal Pairs in Korean},
  journal   = {Language and Information},
  volume    = {28},
  number    = {3},
  pages     = {83-109},
  year      = {2024},
  publisher = {The Korean Society for Language and Information}
}
```

## License
TBD 
