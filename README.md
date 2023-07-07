# Antidote CasiMedicos Datasets

In this repository we present various datasets based on the CasiMedicos project, a community of medical professionals who collaboratively, 
voluntarily, and free of charge, publishes written explanations about the possible
answers included in the Resident Medical Intern exams, or Médico Interno Residente (MIR) in Spanish. These exams aim to assess medical
students by means of a multiple-choice questionnaire sometimes contextualized by a short clinical case.

CasiMedicos Project MIR 2.0's objective is to generate a resource that
helps future medical doctors to study towards the MIR examinations. Thus, the original commented MIR exams (published every year by the Spanish Ministry of Health), including the explanations, are released in the 
[CasiMedicos Project MIR 2.0 website](https://www.casimedicos.com/mir-2-0/).

Based on the original CasiMedicos data, we have generated three different variants of the Antidote CasiMedicos datasets:

+ **casimedicos-raw**: the clean plain text documents including the original MIR exam and the explanations written by Spanish medical doctors.
+ **casimedicos-exp**: manual annotation explanation spans, linking the parts in the explanation to the possible answers they refer to.
+ **casimedicos-arg**: manual annotation of argumentative structures, including argument components and relations, discourse markers, medical treatments and diagnosis.

These datasets have been developed within the [ANTIDOTE CHIST-ERA project](https://univ-cotedazur.eu/antidote).

## casimedicos-raw

After crawling, cleaning, and organizing the data, we obtained 1,561 commented questions corresponding to the years 2011-2014, 2016, and 2018-2022.
Selecting those questions which included clinical cases before the question reduced the number of documents from 1,561 to 622. It should be noted that the answers
are quite heterogeneous. Some are very elaborate and rich, while others are too simple.

+ [download casimedicos-raw](casimedicos-raw.tar.gz)

**If you use casimedicos-raw please cite the following paper:**

+ Rodrigo Agerri, Iñigo Alonso, Aitziber Atutxa, Ander Berrondo, Ainara Estarrona, Iker Garcia-Ferrero, Iakes Goenaga, Koldo Gojenola, Maite Oronoz, Igor Perez-Tejedor, German Rigau, Anar Yeginbergenova (2023).
[HiTZ@Antidote: Argumentation-driven Explainable Artificial Intelligence for Digital Medicine](https://arxiv.org/pdf/2306.06029). In SEPLN 2023: 39th International Conference of the Spanish Society for Natural Language Processing.

## casimedicos-exp

For this dataset we selected the docments generated in casimedicos-raw, namely, those that include a
clinical case to contextualize the question, possible answers
and the given explanations.

The process of manually annotating the corpus consisted of specifying where
the explanation of the correct answer (A) begins and ends. 

In order to obtain grammatically complete correct answer explanations, annotating full sentences or subordinate clauses was preferred over
shorter spans. The annotation took the equivalent of a person's month work
(4 weeks, 160 hours). The dataset is provided in two forms: 

1. [download-casimedicos-exp-squad-format](casimedicos-exp-squad-format.tar.gz): formatted for extractive correct answer explanations following the SQUAD format.
2. [download-casimedicos-exp-all](casimedicos-exp-jsonl.tar.gz): jsonl files containing the annotations for both correct and incorrect answers.

**If you use casimedicos-exp data please cite the following paper:** 

+ Iakes Goenaga, Aitziber Atutxa, Koldo Gojenola, Maite Oronoz, Rodrigo Agerri (2023). Explanatory Argument Extraction of Correct Answers in Resident Medical Exams. In Arxiv.


## casimedicos-arg

TBA

## Contact Details

Rodrigo Agerri (rodrigo.agerri@ehu.eus)
