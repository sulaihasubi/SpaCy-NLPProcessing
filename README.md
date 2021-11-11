Tokenization using spaCy
========================
[![Built with spaCy](https://img.shields.io/badge/made%20with%20❤%20and-spaCy-09a3d5.svg)](https://spacy.io)

[spaCy](https://github.com/explosion/spaCy) is a library for advanced Natural Language Processing in Python and Cython. It's built on the very latest research, and was designed from day one to be used in real products. (Source: [spaCy](https://github.com/explosion/spaCy))

Introduction
------------
Tokenizer is a tool that splits a given text into tokens using regular expressions. The process of tokenizing a text into segments of words and punctuation in Spacy is done in several processes. It reads text from left to right. To begin, the tokenizer separated the text on whitespace in the same way that the split() method does. The tokenizer then checks to see whether the substring fits the tokenizer exception rules.

## ⏳ Install spaCy

For detailed installation instructions and other operating system, can be refer
[here](https://spacy.io/usage).

- **Operating system**: macOS / OS X · Linux · Windows (Cygwin, MinGW, Visual
  Studio)
- **Python version**: Python 3.6+ (only 64 bit)
- **Package managers**: [pip] · [conda] (via `conda-forge`)

[pip]: https://pypi.org/project/spacy/
[conda]: https://anaconda.org/conda-forge/spacy

Installation for macOS (my operating system):

```
# Download best-matching version of specific model for your spaCy installation
python -m spacy download en_core_web_sm

pip install -U pip setuptools wheel
pip install -U spacy
python -m spacy download en_core_web_sm
```
## 📦 Loading & Using Models
To load a model, use [`spacy.load()`](https://spacy.io/api/top-level#spacy.load)
with the model name or a path to the model data directory.

```python
import glob
import spacy

nlp = spacy.load(name='en_core_web_sm')
```

Define your local path where you put the text files.
```python
path = '/Users/risehill/Documents/09-NLPProcessing/TextExtracted/steeples1998.txt'
```
## 👾 Let's get through the Codes!
```python
for file in glob.glob(path):
    with open(file, encoding='utf-8', errors='ignore') as file_in:
        text = file_in.read()
```
In this line of code, the text in paragraph converted into one string everytime it is found any new line
```python
# Replace the newline as one string
 Newtext = text.replace('\n', ' ')
# Check number of text contents in original Text files
 print(len(Newtext))
```

Check the tokenisation details:
```python
text_cleans.append(CleanText)
        print('-----------------------------------------------------------------------------------------------------------')
        print('CHECK TOKENISATION DETAILS')
        print('-----------------------------------------------------------------------------------------------------------')
        # Checking the details of the tokens
        for line in lines:
            line = nlp(line)
            for token in TextCleaned:
                my_doc_cleaned = [token for token in line if not token.is_stop and not token.is_punct and not token.is_space]
                analyzeToken ='{:<5}{:<15}{:<15}{:<15}{:<15}{:<15}'.format(token.i, token.idx, token.text_with_ws, token.is_space, token.is_punct, token.is_stop,)
                analyzeToken2 = '{:<15}{:<15}{:<15}{:<15}{:<15}{:<15}'.format(token.i, token.text, token.is_alpha, token.shape_,  token.is_ascii, token.is_digit)
                analyzeToken3 = '{:<5}{:<15}{:<15}{:<15}{:<15}{:<15}{:<15}'.format(token.i, token.text, token.like_num,
                                                                                   token.like_url, token.like_email,
                                                                                   token.is_ascii, token.is_digit)
                analyzeToken4 = '{:<5}{:<15}{:<15}{:<15}{:<15}{:<15}{:<15}'.format(token.i, token.text, token.is_left_punct,
                                                                                   token.is_right_punct, token.is_bracket,
                                                                                   token.is_quote, token.is_currency)
                analyzeToken5 = '{:<15}{:<15}{:<15}'.format(token.i, token.text, token.text.istitle())
                print(analyzeToken)
```
