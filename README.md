# ChallengeClinicalQA
Repo for the paper [Benchmarking Large Language Models on Answering and Explaining Challenging Medical Questions](https://arxiv.org/pdf/2402.18060.pdf)

### Datasets
- [Medbullets](https://github.com/HanjieChen/ChallengeClinicalQA/tree/main/medbullets)
- [JAMA Clinical Challenge](https://jamanetwork.com/collections/44038/clinical-challenge)

We do not publicly release the JAMA Clinical Challenge data due to license constraints. Instead, we provide [URLs](https://github.com/HanjieChen/ChallengeClinicalQA/blob/main/jama_links.json) to the articles and a [scraper](https://github.com/HanjieChen/ChallengeClinicalQA/blob/main/jama_scraper.py) that you can use to obtain the data with the appropriate license. Please check your license to ensure you have access to JAMA articles (Full Text) before you run the script.

Install the required dependencies
````
pip install -r requirements.txt
````

Scrape the data
````
python jama_scraper.py
````

The data will be saved in `jama_raw.csv` and `jama_raw.json` files.

-------
We thank [awxlong](https://github.com/awxlong) for providing [fetch_jama_cases](https://github.com/HanjieChen/ChallengeClinicalQA/blob/main/fetch_jama_cases.py) to scrape updated links for new data. 

Scrape updated links

````
python fetch_jama_cases.py
````

The updated links will be saved in ``jama_links_updated.json``. 


### Reference
If you find this repository helpful, please cite our paper:
```bibtex
@inproceedings{chen-etal-2025-benchmarking,
    title = "Benchmarking Large Language Models on Answering and Explaining Challenging Medical Questions",
    author = "Chen, Hanjie  and
      Fang, Zhouxiang  and
      Singla, Yash  and
      Dredze, Mark",
    editor = "Chiruzzo, Luis  and
      Ritter, Alan  and
      Wang, Lu",
    booktitle = "Proceedings of the 2025 Conference of the Nations of the Americas Chapter of the Association for Computational Linguistics: Human Language Technologies (Volume 1: Long Papers)",
    month = apr,
    year = "2025",
    address = "Albuquerque, New Mexico",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.naacl-long.182/",
    doi = "10.18653/v1/2025.naacl-long.182",
    pages = "3563--3599",
    ISBN = "979-8-89176-189-6",
    abstract = "LLMs have demonstrated impressive performance in answering medical questions, such as achieving passing scores on medical licensing examinations. However, medical board exams or general clinical questions do not capture the complexity of realistic clinical cases. Moreover, the lack of reference explanations means we cannot easily evaluate the reasoning of model decisions, a crucial component of supporting doctors in making complex medical decisions. To address these challenges, we construct two new datasets: JAMA Clinical Challenge and Medbullets. JAMA Clinical Challenge consists of questions based on challenging clinical cases, while Medbullets comprises simulated clinical questions. Both datasets are structured as multiple-choice question-answering tasks, accompanied by expert-written explanations. We evaluate seven LLMs on the two datasets using various prompts. Experiments demonstrate that our datasets are harder than previous benchmarks. In-depth automatic and human evaluations of model-generated explanations provide insights into the promise and deficiency of LLMs for explainable medical QA."
}
```
