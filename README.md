# Antidote CasiMedicos Datasets

In this repository we present various datasets based on the CasiMedicos project, a community of medical professionals who collaboratively, 
voluntarily, and free of charge, publishes written explanations about the possible
answers included in the Resident Medical Intern exams, or Médico Interno Residente (MIR) in Spanish. These exams aim to assess medical
students by means of a multiple-choice questionnaire sometimes contextualized by a short clinical case.

CasiMedicos Project MIR 2.0's objective is to generate a resource that
helps future medical doctors to study towards the MIR examinations. Thus, the original commented MIR exams (published every year by the Spanish Ministry of Health), including the explanations, are released in the 
[CasiMedicos Project MIR 2.0 website](https://www.casimedicos.com/mir-2-0/).

+ **casimedicos-raw**: the clean plain text documents including the original MIR exam and the explanations written by Spanish medical doctors.
+ **casimedicos-exp**: manual annotation of explanation spans, linking the parts in the explanation to the possible answers they refer to.
+ **casimedicos-arg**: manual annotation of argumentative structures, including argument components and relations, discourse markers, medical treatments and diagnosis.

These datasets have been developed within the [ANTIDOTE CHIST-ERA project](https://univ-cotedazur.eu/antidote).

## casimedicos-raw

After crawling, cleaning, and organizing the data, we obtained 1,561 commented questions corresponding to the years 2011-2014, 2016, and 2018-2022.
Selecting those questions which included clinical cases before the question reduced the number of documents from 1,561 to 622. It should be noted that the answers
are quite heterogeneous. Some are very elaborate and rich, while others are too simple.

+ [download casimedicos-raw](https://huggingface.co/datasets/HiTZ/casimedicos-exp)

**If you use casimedicos-raw please cite the following paper:**
````bibtex
@inproceedings{Agerri2023HiTZAntidoteAE,
  title={HiTZ@Antidote: Argumentation-driven Explainable Artificial Intelligence for Digital Medicine},
  author={Rodrigo Agerri and I{\~n}igo Alonso and Aitziber Atutxa and Ander Berrondo and Ainara Estarrona and Iker Garc{\'i}a-Ferrero and Iakes Goenaga and Koldo Gojenola and Maite Oronoz and Igor Perez-Tejedor and German Rigau and Anar Yeginbergenova},
  booktitle={SEPLN 2023: 39th International Conference of the Spanish Society for Natural Language Processing.},
  year={2023}
}
````

## casimedicos-exp

For this dataset we selected the documents generated in **casimedicos-raw**, namely, those that include a
clinical case to contextualize the question, possible answers and the given explanations.

The process of manually annotating the corpus consisted of specifying where the explanations of the correct and incorrect answers begin and end. 

In order to obtain grammatically complete correct answer explanations, annotating full sentences or subordinate clauses was preferred over
shorter spans. The annotation took the equivalent of a person's month work
(4 weeks, 160 hours). The dataset is provided in two different versions: 

1. [casimedicos-exp-squad-format](https://huggingface.co/datasets/HiTZ/casimedicos-squad): formatted for extractive correct answer explanations following the SQUAD format.

Please **cite the previous and the following** paper if you also use [casimedicos-squad]((https://huggingface.co/datasets/HiTZ/casimedicos-squad), namely, the manual annotations linking the 
explanations with the correct and incorrect possible answers ("explanations" attribute in the jsonl data):

```bibtex
@article{GOENAGA2024102985,
title = {Explanatory argument extraction of correct answers in resident medical exams},
journal = {Artificial Intelligence in Medicine},
volume = {157},
pages = {102985},
year = {2024},
issn = {0933-3657},
doi = {https://doi.org/10.1016/j.artmed.2024.102985},
author = {Iakes Goenaga and Aitziber Atutxa and Koldo Gojenola and Maite Oronoz and Rodrigo Agerri},
}```

2. [MedExpQA](https://huggingface.co/datasets/HiTZ/MedExpQA): casimedicos-exp with RAG for Medical QA. Please **cite the following paper** if you use [casimedicos-exp](https://huggingface.co/datasets/HiTZ/casimedicos-exp) or [MedExpQA](https://huggingface.co/datasets/HiTZ/MedExpQA):

```bibtex
@article{ALONSO2024102938,
title = {MedExpQA: Multilingual benchmarking of Large Language Models for Medical Question Answering},
journal = {Artificial Intelligence in Medicine},
volume = {155},
pages = {102938},
year = {2024},
issn = {0933-3657},
doi = {https://doi.org/10.1016/j.artmed.2024.102938},
author = {Iñigo Alonso and Maite Oronoz and Rodrigo Agerri},
}```

## casimedicos-arg

1. [Download CasiMedicos-Arg](https://huggingface.co/datasets/HiTZ/casimedicos-arg)

[CasiMedicos-Arg](https://huggingface.co/datasets/HiTZ/casimedicos-arg) is, to the best of our knowledge, the first multilingual dataset for Medical Question Answering where correct and incorrect diagnoses for a clinical case are enriched with a natural language explanation written by doctors. The [casimedicos-exp](https://huggingface.co/datasets/HiTZ/casimedicos-exp) have been manually annotated with argument components (i.e., premise, claim) and argument relations (i.e., attack, support). Thus, Multilingual CasiMedicos-arg dataset consists of 558 clinical cases (English, Spanish, French, Italian) with explanations, where we annotated 5021 claims, 2313 premises, 2431 support relations, and 1106 attack relations.

If you **use CasiMedicos-Arg** please cite the following paper:

```bibtex
@inproceedings{sviridova-etal-2024-casimedicos,
    title = {{CasiMedicos-Arg: A Medical Question Answering Dataset Annotated with Explanatory Argumentative Structures}},
    author = "Sviridova, Ekaterina  and
      Yeginbergen, Anar  and
      Estarrona, Ainara  and
      Cabrio, Elena  and
      Villata, Serena  and
      Agerri, Rodrigo",
    booktitle = "Proceedings of the 2024 Conference on Empirical Methods in Natural Language Processing",
    year = "2024",
    url = "https://aclanthology.org/2024.emnlp-main.1026",
    pages = "18463--18475"
}```

## License

 <p xmlns:cc="http://creativecommons.org/ns#" >This work is licensed under <a href="https://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""></a></p> 

## Contact Details

Rodrigo Agerri (rodrigo.agerri@ehu.eus)
