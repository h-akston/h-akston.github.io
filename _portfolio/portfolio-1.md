---
title: "XRI Global: LLMs for low-resource languages"
excerpt: "At XRI global, I helped develop a scoring system for assessing the impact of digital divide on any low-resource language. I also built a solution for aggregating LLMs that support low-resource languages, curated a collections of benchmarks for evaluating LLM performance on low-resource languages and measured the performance of the models using the Global MMLU dataset<br/><img src='/images/500x300.jpg'>"
collection: portfolio
---

As you're describing the content of your internship, be sure to describe how you were able to apply th e concepts and skills you acquired from HLT courses to your internship. You'll also want to describe the things that you learned from the internship itself that might help you in future work.

## Identifying and updating LLMs that support low-resource languages
There are more than 8,500 languages according to [Glottolog](https://glottolog.org/glottolog/language). On Hugging Face, the largest repository of language models, it is possible to filter results for approximately 4,800 natural languages. There is a problem though: the results need to be in a format that would allow us to use them for a downstream task, such as visualization or loading the models for benchmarking. One additional difficulty is that Hugging Face uses two version of ISO language codes, ISO 639-1 and ISO 639-3, which means that for some languages a user would get a different result based on just luck - the two versions look exactly the same on the website interface. We needed information on all models claiming to support a given low-resource language, and we needed a solution that would allow for easy updating as new models were added to Hugging Face. This meant building a custom API interface.

Many courses in the Human Language Technology highlight the importance of reading and following documentation. And thanks to working on a team project for a Data Mining course I had a hands-on experience with getting data from an API. 

* **Length**: A summary of the project goals, technology used, and outcomes, as appropriate for a general technical audience, between 1000 and 3000 words (not counting code)
* **Content**: student’s experience demonstrates the learning outcomes for the MSHLT program [^note]
* **Code**: Code is contained in the site, or a link to the code (such as in a GitHub repository) exists on the site.
* **Professionalism**: Free of grammatical, mechanical, and stylistic issues
* **Above and beyond**: How well does this component communicate the most relevant features?

[^note]: The learning outcomes of the MSHLT program are:
    
    1. Students will demonstrate programming skills for the workplace.
    2. Students will be able to use fundamental algorithms and concepts in Natural Language Processing.
    3. Students will show knowledge of tools and packages used in Natural Language Processing.
