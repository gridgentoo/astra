
Оригинальный репозитарий Astra : :    
https://github.com/alfasoftware/astra  

[Astra] & [перезаписи кода в AST, Truffle API]
инструмент для масштабного рефакторинга Java-программ.  
https://docs.google.com/document/d/1b9pA4M6RjzX-GFxqDqndSv5ElZ1LmzGfTwKTWXunZDk/   

Реверс инжиниринг архитектуры GraalVM  
https://drive.google.com/drive/u/0/folders/1gmd7rLer5a5JppGYtckBThVkcXnti-0G  

[Sourcegraph] движок для навигации по исходным текстам  
https://github.com/gridgentoo/sourcegraph  

[Sourcegraph + AI]  движок для навигации по исходным текстам  
https://docs.google.com/document/d/1bP-_YpqcE_fYfeSfp8CaswHKhX8ksh6lK_PVdWssuec/   
 
С использванием Kubeflow подготовлен пример движка для поиска кода (Go, Java, Python, JavaScript, Ruby)
Предложенный набор данных включает более 2 млн связок "код-комментарий", подготовленных на основе исходных текстов существующих открытых библиотек. Код охватывает полный исходный текст отдельных функций или методов, а комментарий описывает выполняемые функцией действия (приводится детальная документация). В настоящее время наборы данных подготовлены для языков Python, JavaScript, Ruby, Go, Java и PHP. Предоставлены примеры использования предложенных наборов данных для обучения различных типов нейронных сетей, включая Neural-Bag-Of-Words, RNN, Self-Attention (BERT) и 1D-CNN+Self-Attention Hybrid.
Для развития механизмов поиска на естественном языке дополнительно подготовлен набор CodeSearchNet Challenge, включающий 99 типовых запросов с около 4 тысячами экспертных аннотаций, описывающих наиболее вероятные привязки к коду в наборе данных CodeSearchNet Corpus, охватывающем около 6 млн методов и функций (размер набора около 20 Гб).
[Kubeflow] для поиска кода (Go, Java, Python, JavaScript, Ruby)   
https://github.com/gridgentoo/kubeflow_CodeSearchNet  

![Astra logo](images/AlfaAstra-01.png)

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Build Status](https://travis-ci.com/alfasoftware/astra.svg?branch=main)](https://travis-ci.com/alfasoftware/astra)

## What is Astra?
**Astra** is a Java tool for analysing and refactoring Java source code. 

For example:

* "_References to type A should instead reference type B_"
* "_Callers of method A should add an additional argument B_"
* "_Find classes which are annotated with A_"

Astra has been developed and tested at Alfa to improve the velocity at which large scale refactors may be performed.

## How do I use Astra?
* First, please see [the Wiki!](https://github.com/alfasoftware/astra/wiki)
* Astra can be run as part of a Java application, using `astra-core` as a dependency and using the refactors it provides. For an illustration of how to do this, please see the [README in astra-core](./astra-core/README.md). The code can be found in [astra-example](./astra-example).
* For cases needing a more bespoke approach, [astra-core](./astra-core/README.md) also provides an SPI for writing your own custom `ASTOperation`s. See the `astra-core` README for further details.
* For very simple cases, there is also a command line interface which exposes a small subset of Astra's refactoring operations. Please see [astra-cli](./astra-cli/README.md) for more information.

## Why would I use Astra?
A simple and common use case is renaming a method, and updating all the callers of that method so that they use the new name. 
Your IDE is often the best tool for the job, but sometimes this isn't possible. There may be so many modules that manually selecting and opening them is a real pain, or the overall size of the modules may mean that your IDE struggles to open them all at once. 
This means that sometimes it's easier to just add a new method, deprecate the old one, and leave all the existing callers. 
The same issues apply to many other refactors, such as renaming a type. 

Astra can be used to make changes like these easily, and on a massive scale.

## How does Astra work?
Please see [How does Astra work?](https://github.com/alfasoftware/astra/wiki/How-does-Astra-work%3F) in the Wiki.

## Technologies
* Java 11
* Eclipse JDT
* JUnit
* log4j

## License
Astra is released under the [Apache 2.0 License](https://github.com/alfasoftware/astra/blob/main/LICENSE). Contributions are also made under this license, as per the GitHub [terms of service](https://docs.github.com/en/github/site-policy/github-terms-of-service#6-contributions-under-repository-license).
