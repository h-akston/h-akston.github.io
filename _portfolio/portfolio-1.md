---
title: "XRI Global: LLMs for low-resource languages"
excerpt: "At XRI global, I helped develop a scoring system for assessing the impact of digital divide on any low-resource language. I also built a solution for aggregating LLMs that support low-resource languages, curated a collection of benchmarks for evaluating LLM performance on low-resource languages and measured the performance of the models using the Global MMLU dataset<br/><img src='/images/500x300.jpg'>"
collection: portfolio
---

At XRI Global, I was part of a team working on a project to assess the depth of divide between high-resource languages and low-resource languages when it came to AI: translation, speech recognition and generation, conversational models. I worked on all things related to language models: building a solution for aggregating LLMs that support low-resource languages, curating a collection of benchmarks for evaluating LLM performance on low-resource languages and measuring the performance of the models using the Global MMLU dataset.

Our team presented this work at the International Conference on Language Technologies for All in Paris in February 2025. <br/><img src='/images/conference.png'>

**[Publication abstract](https://www.lt4all2025.eu/2025/02/24/lt4all-2025-book-of-abstracts-now-available/)**
**[Our Github repository](https://github.com/XRILLC/inclusiveai)**
**[Live demo](https://inclusiveai-app.vercel.app/)**


## Identifying and updating LLMs that support low-resource languages
There are more than 8,500 languages according to [Glottolog](https://glottolog.org/glottolog/language). On Hugging Face, the largest repository of language models, it is possible to filter results for approximately 4,800 natural languages. There is a problem though: the results need to be in a format that would allow us to use them for a downstream task, such as visualization or loading the models for benchmarking. One additional difficulty is that Hugging Face uses two version of ISO language codes, ISO 639-1 and ISO 639-3, which means that for some languages a user would get a different result based on just luck - the two versions look exactly the same on the website interface. We needed information on all models claiming to support a given low-resource language, and we needed a solution that would allow for easy updating as new models were added to Hugging Face. This meant building a custom API interface.

Many courses in the Human Language Technology highlight the importance of reading and following documentation. And thanks to working on a team project for a Data Mining course I had a hands-on experience with getting data from an API.

Our solution would have to meet a few important requirements:
* **Filtering certain models out**: Certain language models have limited conversational abilities, so our team needed a way to filter these out using a simple keyword, where "BLOOM" would filter out any BLOOM-based models in our final results.
* **Append and overwrite modes**: Our program would have to be able to append to an existing file, effectively updating an existing database of models, or write a new file, for example for a different subset of languages or for a single language.
* **Sort by language and by model**: Our team needed two types of output. One where the model would be the first column, making it easy to how many models there are, what languages they support and to compare models among themselves. The other output would have to be sorted by language, listing all available models for each language, enabling us to compare languages in terms of number/type of available language models.

I used huggingface_hub library to interact with Hugging Face API and pandas to manipulate data and export it as a .csv file. The program met all the requirements and is capable of indexing 500+ models in less than 5 minutes!

Full code for my solution with comments can be found in [our GitHub repository](https://github.com/XRILLC/inclusiveai/tree/main/llm_benchmarks) in llm_benchmarks/hugging_face_scrape

## Scoring system for assessing the severity of digital divide
Within our team at XRI Global we developed a scoring system to assess how far ahead or behind a given language is in terms of access to such technologies as translation, ASR, TTS, large language models. At the center of our scoring system were BLEU scores and ChRF scores (both machine translation metrics), WER numbers (a speech-to-text metric) and whether text-to-speech models are available for that language. Our scoring system has a maximum score of 100 and a minimum score of 0. The lower the score, the more affected a given language is by the digital divide. That's what our scoring system looks like:
<br/><img src='/images/scoring.png'>



## Curating a collection of LLM benchmarks for low-resource languages

## Benchmarking the performance of LLMs using the Global MMLU dataset

