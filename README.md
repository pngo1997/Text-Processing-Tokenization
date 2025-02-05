# 📊 Text Processing & Tokenization  

## 📜 Overview  
This project focuses on **text analysis and tokenization**, computing key statistics from a plain text document while following **custom tokenization rules**. The program processes input text to generate:  

- 📑 **Total number of paragraphs**  
- ✍️ **Total number of sentences**  
- 📝 **Total number of words/tokens** (after tokenization)  
- 🔍 **Total number of unique words/tokens**  
- 📊 **Ranked word frequency counts** (sorted in descending order)  

Additionally, visualizes **Zipf’s Law**, plotting word frequency vs. rank in a log-log chart.  

## 🚀 1️⃣ Implementation Details  

### **Text Processing Rules**  
✅ **Sentence Segmentation**: Uses `nltk.sent_tokenize()`.  
✅ **Word Tokenization**: Uses `nltk.word_tokenize()`, then further processes tokens:  
  - **Punctuation Handling**:  
    - Leading/trailing punctuation **separated**, but **kept**.  
    - Internal punctuation within words **retained** (e.g., `$3.19 → "$", "3.19"`).  
  - **Contractions Expansion**:  
    - `"don't" → "do", "not"`  
    - `"they'll" → "they", "will"`  
    - `"let's" → "let", "us"`  
    - `"I'm" → "I", "am"`  
    - Multi-contraction handling: `"shouldn't've" → "should", "not", "have"`.
      
✅ **Normalization**:  
  - Convert all words to **lowercase**.  
  - **No stemming or stopword removal**.
    
✅ **Word Frequency Calculation**:  
  - Compute **unique word counts**.  
  - Sort words **by frequency (descending)**, then **alphabetically (ascending) if tied**.
    
## 🚀 2️⃣ **Zipf’s Law Visualization**:  
  - Generate **log-log plot** of word frequency vs. rank.  
  - Expected **Zipfian curve** showing a power-law distribution.
  - Zipf's Law curve shows the token's frequency distribution in descending order of ranking. First ranked word (start from left) has the highest occurrence, and gradually decrease with lower rankings. The initial steep indicates that the text corpus has high occurrences of common words, and flatten tails indicates approximately more than 50% of less common words. The curve shows a comprehensive view of words distribution in a text which is extremely helpful as a preliminary step to conduct further advanced tasks.
![Zipf Law](https://github.com/pngo1997/Images/blob/main/Zipf's%20Law.png)  

## 📌 Summary  
✅ Implemented text processing & tokenization with custom rules.

✅ Expanded contractions, normalized words, and retained punctuations.

✅ Analyzed word frequency distribution and generated Zipf’s Law plot.
