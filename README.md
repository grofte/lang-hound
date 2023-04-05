# lang-hound
A machine learning model for detecting what language a given text is in.

## Usage / Getting started

## Domain

### 

You can get really far in language detection simply by tallying the character bigrams. Sometimes you even have an alphabet, syllabary, or logography that is only used by one language which makes things very easy. Other times languages are very similar and distinguishing them can be hard or impossible. Especially for short texts you can have multiple languages that perfectly match, e.g. "Okay." could work in a number of languages. It will not be possible for a model to give a good predition on such data no matter how clever the neural network is designed or how much data you feed it. There you will have to fall back on context or metadata to give a good answer or you may have to give up. "Okay." is not that bad since it means the same in most languages but there could be other examples where the language cannot be determined but the meaning changes depending on the language. Unfortunately.

A strong meta data point for which language(s) are used could be the keyboard language setting. Geographic location could help. Email addresses could be helpful and so could usernames.

The biggest challenge for language detection is code switching where a person writes a text in multiple languages. It can also happen that an automatic system adds text in a different language to an existing text. Two ways around that might be defining the problem as multilabel instead of multiclass or as span classification where the model would return the begin and end index of each language in the text. We would have to have or construct data with multiple languages for that so I am going to park that for now.

The current gold standard for language detection is the APIs from [Google](https://cloud.google.com/translate/docs/advanced/detecting-language-v3) and [Amazon](https://docs.aws.amazon.com/comprehend/latest/dg/how-languages.html)

## Data

Most data is unbalanced, unverified, and will make you unhappy.

To have fairly verified data I am going to go with text from Wikipedia.

### WiLI-2018 - Wikipedia Language Identification database

WiLI-2018, [data](https://zenodo.org/record/841984) and [paper](https://arxiv.org/abs/1801.07779), has Wikipedia articles from 235 languages - 1000 from each language. That's not a lot of data but at least it is balanced.

### Full Wikipedia dump

Tensorflow Datasets has cleaned up versions of all of Wikipedia, split by language, [here](https://www.tensorflow.org/datasets/catalog/wikipedia#wikipedia20230201aa_default_config). Its massive size makes it a pain to handle and to balance it you would probably have to aggresively downsample the majority languages, i.e. randomly skip most of the data from languages like English to avoid having it dominating the training. Once everything in this project works well it might be an idea to switch from the small WiLI-2018 dataset to this instead but let us hold off on that.

## Model

## MLOps

## Contributing

## Acknowledgements

## Frequently Asked Questions (FAQ)

I have not had a single question. Not one. I must be infallible.
