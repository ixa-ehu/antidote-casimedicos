# Antidote CasiMedicos Datasets

In this repository we present various datasets based on the CasiMedicos project, a community of medical professionals who collaboratively, 
voluntarily, and free of charge, publishes written explanations about the possible
answers included in the Resident Medical Intern exams, or Médico Interno Residente (MIR) in Spanish. These exams aim to assess medical
students by means of a multiple-choice questionnaire sometimes contextualized by a short clinical case.

CasiMedicos Project MIR 2.0's objective is to generate a resource that
helps future medical doctors to study towards the MIR examinations. Thus, the original commented MIR exams (published every year by the Spanish Ministry of Health), including the explanations, are released in the 
[CasiMedicos Project MIR 2.0 website](https://www.casimedicos.com/mir-2-0/).

Based on the original Spanish CasiMedicos data, we have generated three different variants of the Antidote CasiMedicos datasets for 4 languages, **English, French, Italian and Spanish**.

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

For this dataset we selected the docments generated in **casimedicos-raw**, namely, those that include a
clinical case to contextualize the question, possible answers and the given explanations.

The process of manually annotating the corpus consisted of specifying where the explanations of the correct and incorrect answers begin and end. 

In order to obtain grammatically complete correct answer explanations, annotating full sentences or subordinate clauses was preferred over
shorter spans. The annotation took the equivalent of a person's month work
(4 weeks, 160 hours). The dataset is provided in two different following forms: 

1. [casimedicos-exp-squad-format](https://github.com/ixa-ehu/antidote-casimedicos/raw/main/casimedicos-exp-squad-format.tar.gz): formatted for extractive correct answer explanations following the SQUAD format.
2. [casimedicos-exp-jsonl-format](https://huggingface.co/datasets/HiTZ/casimedicos-exp): including **casimedicos-raw** and annotations for incorrect and correct answers in jsonl format.

Please **cite the previous and the following** paper if you also use **casimedicos-exp**, namely, the manual annotations linking the 
explanations with the correct and incorrect possible answers ("explanations" attribute in the jsonl data):

```bibtex
@misc{goenaga2023explanatory,
      title={Explanatory Argument Extraction of Correct Answers in Resident Medical Exams}, 
      author={Iakes Goenaga and Aitziber Atutxa and Koldo Gojenola and Maite Oronoz and Rodrigo Agerri},
      year={2023},
      eprint={2312.00567},
      archivePrefix={arXiv}
}
```

## casimedicos-arg

TBA

## Contact Details

Rodrigo Agerri (rodrigo.agerri@ehu.eus)
