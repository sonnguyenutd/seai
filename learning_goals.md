# 17-445/645 Software Engineering for AI-Enabled Systems -- Learning Goals



## Lecture: Introduction and Motivation

Content:

* Lecture illustrates traditional view of machine learning and contrasts it with the challenges of building systems. Characterizes stakeholders involved and their goals. Overview of qualities. Outlines challenges to be discussed
* Inductive vs deductive reasoning; key distinction specifications vs learning from data, but also success in engineering systems from imprecise specifications and unreliable components
* Technical debt
* Brief distinction AI vs ML and typical classes of AI components
* Syllabus and class structure; introductions, and survey

Learning goals:

* Explain the typical machine-learning process
* Illustrate the challenges in engineering an AI-enabled system beyond accuracy
* Summarize the respective goals and challenges of software engineers vs data scientists

Assignment:

* Case study analysis of an ML product



## Lecture: From Models to AI-Enabled Systems (Systems Thinking) ![Requirements](https://img.shields.io/badge/-Requirements-Green.svg) ![Architecture](https://img.shields.io/badge/-Architecture/Design-Blue.svg) ![QA](https://img.shields.io/badge/-Quality%20Assurance-Orange.svg) ![Process](https://img.shields.io/badge/-Process-Grey.svg)

Overview:

* Machine learning is typically a component of a larger system in production
* Thinking in pipelines not models
* Challenges of production-machine learning
* Components of intelligent experiences and corresponding challenges (experience, intelligence, orchestration) within a larger system architecture
* Overview of design options and automation degrees, e.g., forcefulness of the experience
* Qualities of interest (beyond model accuracy)
* Illustration how machine-learned components interact with other mechanisms of the system, e.g., guardrails and other safety mechanisms
* View of machine-learning pipelines over models

Learning goals:

* Explain how machine learning fits into the larger picture of building and maintaining production systems
* Describe the typical components relating to AI in an AI-enabled system and typical design decisions to be made

Readings:

* 🕮 Hulten, Geoff. "Building Intelligent Systems: A Guide to Machine Learning Engineering." (2018), Chapters 5 (Components of Intelligent Systems).
* 🗎 Sculley, David, Gary Holt, Daniel Golovin, Eugene Davydov, Todd Phillips, Dietmar Ebner, Vinay Chaudhary, Michael Young, Jean-Francois Crespo, and Dan Dennison. "[Hidden technical debt in machine learning systems](http://papers.nips.cc/paper/5656-hidden-technical-debt-in-machine-learning-systems.pdf)." In Advances in neural information processing systems, pp. 2503-2511. 2015.



## Lecture: Model Quality and Software Testing ![Quality Assurance](https://img.shields.io/badge/-Quality%20Assurance-Orange.svg)

Overview:

* Goals and measurement
* Metrics and experimental designs to assess model quality, including measures beyond accuracy and RUC
* Challenge of getting test data
* Automated assessment, dashboards, continuous integration, continuous experimentation
* Notions of test suits and coverage for models (e.g., test by population segment), black box test case design
* Comparison against heuristics approaches
* Fuzzing, adversarial learning, and test case generation; overview of current research
* Metamorphic testing

Learning goals:

* Select a suitable metric to evaluate prediction accuracy of a model and to compare multiple models
* Select a suitable baseline when evaluating model accuracy
* Explain how software testing differs from measuring prediction accuracy of a model
* Curate validation datasets for assessing model quality, covering subpopulations as needed
* Use invariants to check partial model properties with automated testing
* Develop automated infrastructure to evaluate and monitor model quality


Readings:

* 🕮 Hulten, Geoff. "Building Intelligent Systems: A Guide to Machine Learning Engineering." (2018), 19-20 (Evaluating Intelligence, Machine Learning Intelligence).
* 🗎 Ribeiro, Marco Tulio, Sameer Singh, and Carlos Guestrin. "[Semantically equivalent adversarial rules for debugging NLP models](https://www.aclweb.org/anthology/P18-1079.pdf)." In Proceedings of the 56th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers), pp. 856-865. 2018.
  



## Lecture: Quality Assessment in Production ![Implementation/Operations](https://img.shields.io/badge/-Implementation/Operations-Yellow.svg) ![Quality Assurance](https://img.shields.io/badge/-Quality%20Assurance-Orange.svg)

Overview:

* Introduction to the scientific method (experimental design, statistical tests, causality)
* Design of telemetry 
* Online experimentation
  * Testing in production, chaos engineering
  * *A/B testing*
  * Necessary statistics foundation
  * Concurrent A/B tests
* Infrastructure for experimentation, planning and tracking experiments
* Interacting with and supporting data scientists

Learning goals:

* Plan and execute experiments (chaos, A/B, ...) in production
* Conduct and evaluate multiple concurrent A/B tests in a system
* Examine experimental results with statistical rigor
* Perform sensitivity analysis in large configuration/design spaces

Assignment:

* Design an experimentation platform that (a) performs automated tests offline, (b) tracks experiments and their results, (c) compares model quality using suitable measures

Readings:

* Alec Warner and Štěpán Davidovič. “[Canary Releases](https://landing.google.com/sre/workbook/chapters/canarying-releases/).” in [The Site Reliability Workbook](https://landing.google.com/sre/books/), O'Reilly 2018
* Georgi Georgiev. “[Statistical Significance in A/B Testing – a Complete Guide](http://blog.analytics-toolkit.com/2017/statistical-significance-ab-testing-complete-guide/#noninf).” Blog 2018



## Lecture: Goals and Success Measures for AI-Enabled Systems ![Requirements](https://img.shields.io/badge/-Requirements-Green.svg) ![Architecture](https://img.shields.io/badge/-Architecture/Design-Blue.svg)

Overview:

* Business consideration for using machine learning
* When to use AI and when not to use AI
* Overall cost of operating an ML-component (e.g., data, learning, updating, inference cost)
* Brief intro into measurement
* Defining and measuring a systems goals
* Designing telemetry to assess system success

Learning goals:

* Judge when to apply AI for a problem in a system
* Define system goals and map them to goals for the AI component
* Design and implement suitable measures and corresponding telemetry

Readings:

* 🕮 Hulten, Geoff. "Building Intelligent Systems: A Guide to Machine Learning Engineering." (2018), Chapters 2 (Knowing when to use IS), 4 (Defining the IS’s Goals) and 15 (Intelligent Telemetry)

Optional readings:

* 🕮 Ajay Agrawal, Joshua Gans, Avi Goldfarb. “[Prediction Machines: The Simple Economics of Artificial Intelligence](https://cmu.primo.exlibrisgroup.com/permalink/01CMU_INST/6lpsnm/alma991019698987304436)” 2018 



## Lecture: Risk and Planning for Mistakes (Requirements) ![Requirements](https://img.shields.io/badge/-Requirements-Green.svg) ![Architecture](https://img.shields.io/badge/-Architecture/Design-Blue.svg)

Overview:

* Specifications or lack thereof for ML-components, deductive reasoning, probabilistic specifications in certain AI components; inevitability 
* Introduction to risk analysis and fault trees; writing of requirements
* The world and the machine in the context of AI: concept drift, feedback loops, adversaries
* Overview of fault handling strategies (guardrails, redundancies, voting, fallback, undo, forcefulness, where and when to ask for human judgment...)
* Viewpoint: Machine learning as requirements engineering/specification mining

Learning goals:

* Analyze how mistake in an AI component can influence the behavior of a system
* Evaluate risk of a mistake from the AI component using fault trees
* Design and justify a mitigation strategy for a concrete system

Assignment:

* Write requirements and plan mechanisms for dealing with mistakes; set system goals and define success measures; perform risk analysis

Readings:

* 🕮 Hulten, Geoff. "Building Intelligent Systems: A Guide to Machine Learning Engineering." (2018), Chapters 6--8, and 24.

Recommended supplementary reading:

* Kocielnik, Rafal, Saleema Amershi, and Paul N. Bennett. "Will you accept an imperfect AI? Exploring designs for adjusting end-user expectations of AI systems." In *Proceedings of the 2019 CHI Conference on Human Factors in Computing Systems*, pp. 1-14. 2019.



## Lecture: Tradeoffs among Modeling Techniques ![Architecture](https://img.shields.io/badge/-Architecture/Design-Blue.svg)

Overview:

* Survey quality attributes of interest (e.g., accuracy, model size, inference time, learning time, robustness)
* Survey of ML and symbolic AI techniques and their tradeoffs
* Brief intro to fairness, explainability, and robustness

Learning goals:

* Describe the most common models and learning strategies used for AI components and summarize how they work
* Organize and prioritize the relevant qualities of concern for a given project
* Plan and execute an evaluation of the qualities of alternative AI components for a given purpose

Assignment:

* Present tradeoff analysis among two techniques (prepare blog post + short presentation); for a given dataset evaluate which technique is more suitable after measuring various qualities; find an alternative task for which the other technique is more suitable

Readings:

* 🗎 Vogelsang, Andreas, and Markus Borg. "[Requirements Engineering for Machine Learning: Perspectives from Data Scientists](https://arxiv.org/pdf/1908.04674.pdf)." In Proc. of the 6th International Workshop on Artificial Intelligence for Requirements Engineering (AIRE), 2019.



## Lecture: Software Architecture of AI-enabled Systems ![Architecture](https://img.shields.io/badge/-Architecture/Design-Blue.svg)

Overview:

* Introduction to software architecture and domain-specific modeling
* Modularity, encapsulation, model composition, design for robustness
* Abstraction techniques for hardware, software and data change
* Architecture case study: Model updates
  * Importance of model updates; threats from stale data and data drift
  * Architectural discussions: when to learn, incremental vs from scratch, where the model lives, costs for updates vs costs from stale models, client-side vs server-side models vs hybrid approaches
* Architectural patterns and design patterns for ML
* AI as a service
* Cost of data and feature extraction (deciding what data/features and how much)
* TODO: Architectural decision: when and *where* to learn (e.g., privacy, testing)

Learning goals:

* Create an architectural model describing the relevant characteristics to reason about update frequency and costs
* Critique the decision of where an AI model lives (e.g., cloud vs edge vs hybrid), considering the relevant tradeoffs 

Assignment:

* Design and justify a system architecture for a given scenario, considering computing and network resources

Readings:

* 🕮 Hulten, Geoff. "Building Intelligent Systems: A Guide to Machine Learning Engineering." (2018), Chapter 13 (Where Intelligence Lives)

* 📰 Daniel Smith. "[Exploring Development Patterns in Data Science](https://www.theorylane.com/2017/10/20/some-development-patterns-in-data-science/)." TheoryLane Blog Post. 2017.
* 🗎 Washizaki, Hironori, Hiromu Uchida, Foutse Khomh, and Yann-Gaël Guéhéneuc. "[Machine Learning Architecture and Design Patterns](http://www.washi.cs.waseda.ac.jp/wp-content/uploads/2019/12/IEEE_Software_19__ML_Patterns.pdf)." Draft, 2019



## Lecture: Data Quality and Data Programming ![Quality Assurance](https://img.shields.io/badge/-Quality%20Assurance-Orange.svg)

Overview:

* Introduction to *data cleaning*
* Introduction to *data schema* (databases, xml, Avro, ...) and unit testing for data
* Comparing data distributions and detecting data drift
* Quality assurance for the data processing pipelines
* Measures of noise, accuracy, and precision, and consequences for AI components (robustness)
* Integrating data from many sources, with different qualities
* Automated data cleaning with HoloClean
* Weakly-supervised learning with Snorkel

Learning goals:

* Design and implement automated quality assurance steps that check data schema conformance and distributions 
* Devise thresholds for detecting data drift and schema violations
* Describe common data cleaning steps and their purpose and risks
* Evaluate the robustness of AI components with regard to noisy or incorrect data
* Understanding the better models vs more data tradeoffs
* Programatically collect, manage, and enhance training data


Readings:

* 🗎 Schelter, S., Lange, D., Schmidt, P., Celikel, M., Biessmann, F. and Grafberger, A., 2018. Automating large-scale data quality verification. Proceedings of the VLDB Endowment, 11(12), pp.1781-1794.
* 🗎 The Data Linter: Lightweight Automated Sanity Checking for ML Data Sets. Nick Hynes, D. Sculley, Michael Terry  NIPS Workshop on ML Systems (2017)
* 🗎 Rahimi, Mona, Jin LC Guo, Sahar Kokaly, and Marsha Chechik. "[Toward Requirements Specification for Machine-Learned Components](https://ieeexplore.ieee.org/document/8933771)." In 2019 IEEE 27th International Requirements Engineering Conference Workshops (REW), pp. 241-244. IEEE, 2019.
* Snorkel and HoloClean papers

Assignments: Snorkel assignment?

## Lecture: Managing and Processing Large Datasets ![Architecture](https://img.shields.io/badge/-Architecture-Blue.svg) ![Implementation/Operations](https://img.shields.io/badge/-Implementation/Operations-Yellow.svg)

Overview:

* Infrastructure for large amounts of training data and large amounts of telemetry
* Introduction to data storage strategies and their tradeoffs
* Schema vs noschema storage (data lakes)
* Overview of common technologies (relational databases, NoSQL storage, OLAP/OLTP, streaming systems, replication and partitioning)
* Design considerations: mutable vs immutable data
* Common design patterns (e.g., batch processing, stream processing, lambda architecture)
* Distributed logging systems, distributed data cleaning and feature extraction, distributed learning – including open-source frameworks

Learning goals:

* 🗎 Organize different data management solutions and their tradeoffs
* 🗎 Recommend and justify a design and corresponding technologies for a given system

Readings:

* 🕮 Martin Kleppmann. [Designing Data-Intensive Applications](https://cmu.primo.exlibrisgroup.com/discovery/fulldisplay?docid=alma991019578119704436&context=L&vid=01CMU_INST:01CMU&search_scope=MyInst_and_CI&tab=Everything&lang=en). O’Reilly, 2017, Ch. 1

* tbd (on data lakes, lambda architecture, stream processing)

  

## Lecture: Deployment and Infrastructure Quality ![Implementation/Operations](https://img.shields.io/badge/-Implementation/Operations-Yellow.svg) ![QA](https://img.shields.io/badge/-Quality%20Assurance-Orange.svg)

Overview:

* Unit testing vs integration testing vs system testing
* Testing all parts of the ML-pipleline
* Test automation with *Continuous Integration* tools
* Performance testing and performance regression testing
* Introduction to DevOps and Continuous Deployment
* *Canary releases* and rolling releases
* *Feature flags* and corresponding infrastructure
* Code reviews
* Unit vs system testing: local improvements may degrade overall system performance


Learning goals:

* Deploy a service for models using container infrastructure
* Design and implement an infrastructure canary/rolling releases using feature flags
* Implement and automate tests for all parts of the ML pipeline

Assignment:

* Design a pipeline to build, evaluate, and serve models that (a) performs automated tests offline, (b) rolls out models incrementally and rolls back a model automatically if it performs poorly, (c) enables experimentation, (d) detects and reports data quality issues and data drift, and (e) provides a monitoring dashboard and sends alerts


Reading:

* 🗎 Zinkevich, Martin. [Rules of Machine Learning: Best Practices for ML Engineering](https://developers.google.com/machine-learning/guides/rules-of-ml/). Google Blog Post, 2017
* 🗎 Eric Breck, Shanqing Cai, Eric Nielsen, Michael Salib, D. Sculley. The ML Test Score: A Rubric for ML Production Readiness and Technical Debt Reduction. Proceedings of IEEE Big Data (2017)



## Lecture: Ethics + Fairness (2 Lectures) ![Requirements](https://img.shields.io/badge/-Requirements-Green.svg) ![Quality Assurance](https://img.shields.io/badge/-Quality%20Assurance-Orange.svg) ![Process](https://img.shields.io/badge/-Process-Grey.svg) ![Machine Learning](https://img.shields.io/badge/-Machine%20Learning-Purple.svg)

Overview:

* Introductions to ethics
* Overview of notions of *bias and fairness* and corresponding philosophies and measures
* Identifying key concerns to drive requirements analysis and tradeoff decisions
* Techniques for measuring bias; fairness testing
* Overview of possible interventions to reduce or mitigate bias

Learning goals:

* Review the importance of ethical considerations in designing AI-enabled systems
* Recall basic strategies to reason about ethical challenges
* Diagnose potential ethical issues in a given system
* Design and execute tests to check for bias/fairness issues
* Evaluate and apply mitigation strategies

Assignment:

* Analyze a given component for potential bias, design a mitigation, and deploy automated tests 

Readings:

* 📰 Max Tegmark. [Benefits and Risks of Artificial Intelligence](https://futureoflife.org/background/benefits-risks-of-artificial-intelligence/?cn-reloaded=1). Future of Life Institute
* 📰 Julia Angwin, Jeff Larson, Surya Mattu and Lauren Kirchner. [Machine Bias](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing). Propublica 2016
* 🗎 Corbett-Davies, Sam, and Sharad Goel. "[The measure and mismeasure of fairness: A critical review of fair machine learning](https://arxiv.org/abs/1808.00023)." arXiv preprint arXiv:1808.00023 (2018).
* 🗎 Holstein, Kenneth, Jennifer Wortman Vaughan, Hal Daumé III, Miro Dudik, and Hanna Wallach. "[Improving fairness in machine learning systems: What do industry practitioners need?](http://users.umiacs.umd.edu/~hal/docs/daume19fairness.pdf)" In *Proceedings of the 2019 CHI Conference on Human Factors in Computing Systems*, pp. 1-16. 2019.
* 🗎 Madaio, Michael A., Luke Stark, Jennifer Wortman Vaughan, and Hanna Wallach. "[Co-Designing Checklists to Understand Organizational Challenges and Opportunities around Fairness in AI](http://www.jennwv.com/papers/checklists.pdf)." In Proceedings of the 2020 CHI Conference on Human Factors in Computing Systems, pp. 1-14. 2020.
* 🗎 Robyn Caplan, Joan Donovan, Lauren Hanson, Jeanna Matthews. [Algorithmic Accountability: A Primer. (Links to an external site.)](https://datasociety.net/wp-content/uploads/2018/04/Data_Society_Algorithmic_Accountability_Primer_FINAL-4.pdf) Data & Society (2018)



## Lecture: Safety and Robustness ![Requirements](https://img.shields.io/badge/-Requirements-Green.svg) ![Architecture/Design](https://img.shields.io/badge/-Architecture/Design-Blue.svg) ![Quality Assurance](https://img.shields.io/badge/-Quality%20Assurance-Orange.svg) ![Machine Learning](https://img.shields.io/badge/-Machine%20Learning-Purple.svg)

Overview:

* Introduction to safety and ethics; safety vs reliability
* Introduction to *hazard analysis* (requirements)
* State of the art of robustness research in machine learning – approaches and guarantees
* Safety concerns in everyday applications
* Architectural safety tactics -- how to build safe systems from unreliable components
* Introduction to assurance cases and software certification; evidence collection for safety claims

Learning goals:

* Summarize the state of the art robustness analysis strategies for machine-learned models
* Perform a hazard analysis for a system to derive safety requirements
* Diagnose potential safety issues in a given system
* Collect evidence and sketch an argument for a safety case
* Design architectural safeguards against safety-relevant mistakes from AI components
* Describe the typical processes for safety evaluations and their limitations

Assignment: (?)

* Perform a hazard analysis of a given system, identify suitable mitigations, and sketch an argument for a safety case

Readings:

* 🗎 Borg, Markus, Cristofer Englund, Krzysztof Wnuk, Boris Duran, Christoffer Levandowski, Shenjian Gao, Yanwen Tan, Henrik Kaijser, Henrik Lönn, and Jonas Törnqvist. "[Safely entering the deep: A review of verification and validation for machine learning and a challenge elicitation in the automotive industry](https://www.atlantis-press.com/journals/jase/125905766)." Journal of Automotive Software Engineering. Volume 1, Issue 1, Pages 1 - 19. 2019
* 🗎 Cohen, Jeremy M., Elan Rosenfeld, and J. Zico Kolter. "[Certified adversarial robustness via randomized smoothing](https://arxiv.org/abs/1902.02918)." In Proc. International Conference on Machine Learning, p. 1310--1320, 2019.
* 🗎 Salay, Rick, Rodrigo Queiroz, and Krzysztof Czarnecki. "[An analysis of ISO 26262: Using machine learning safely in automotive software (Links to an external site.)](https://arxiv.org/pdf/1709.02435)." *arXiv preprint arXiv:1709.02435* (2017).



## Lecture: Security, Adversarial Learning, and Feedback Loops ![Requirements](https://img.shields.io/badge/-Requirements-Green.svg) ![Quality Assurance](https://img.shields.io/badge/-Quality%20Assurance-Orange.svg) ![Process](https://img.shields.io/badge/-Process-Grey.svg)

Overview:

* Attack scenarios against AI components and possible defenses
* Basics of adversarial learning techniques
* Feedback loops and how to detect them
* Dangers of leaking sensitive data, deanonymization, and *differential privacy*
* *Threat modeling*
* Overview of common security patterns/tactics
* Anomaly detection, intrusion detection

Learning goals:

* Describe common attacks against AI component 
* Conduct threat modeling for a given system and derive security requirements
* Suggest counter measures against attacks for specific systems
* Discuss challenges in anonymizing data 

Reading:

* 🕮 Hulten, Geoff. "Building Intelligent Systems: A Guide to Machine Learning Engineering." (2018), Chapter 25 (Adversaries and Abuse)
* 🗎 Shawn Hernan and Scott Lambert and Tomasz Ostwald and Adam Shostack. [Uncover Security Design Flaws Using The STRIDE Approach](https://github.com/ckaestne/seai/raw/F2019/other_material/readings/security/msnd_threatmodeling.pdf). MSDN 2007
* 🕮 Agrawal, A., Gans, J., & Goldfarb, A. (2018). [*Prediction machines: the simple economics of artificial intelligence* (Links to an external site.)](https://cmu.primo.exlibrisgroup.com/permalink/01CMU_INST/6lpsnm/alma991019698987304436). Harvard Business Press. Chapter 19 (Managing AI Risk)
* 🗎 Goodfellow, I., McDaniel, P., & Papernot, N. (2018). [Making machine learning robust against adversarial inputs](https://par.nsf.gov/servlets/purl/10111674). *Communications of the ACM*, *61*(7), 56-66. 
* 🗎 Huang, L., Joseph, A. D., Nelson, B., Rubinstein, B. I., & Tygar, J. D. (2011, October). [Adversarial machine learning](http://www.blaine-nelson.com/research/pubs/Huang-Joseph-AISec-2011.pdf). In *Proceedings of the 4th ACM workshop on Security and artificial intelligence* (pp. 43-58). 

## Lecture: Explainability & Interpretability ![Requirements](https://img.shields.io/badge/-Requirements-Green.svg) ![Machine Learning](https://img.shields.io/badge/-Machine%20Learning-Purple.svg)

Overview:

* Introduction to use cases, concepts, and measures for interpretability
* Explanatory power of different AI techniques, retrofitting explanations
* Strategies for model interpretability, including local explanations, invariants, counterfactuals, and model constraints
* Introduction to sensitivity analysis

Readings:

* 🗎 Rudin, Cynthia. "[Stop explaining black box machine learning models for high stakes decisions and use interpretable models instead](https://arxiv.org/abs/1811.10154)." Nature Machine Intelligence 1, no. 5 (2019): 206-215.
* 🗎 Ribeiro, Marco Tulio, Sameer Singh, and Carlos Guestrin. "[Anchors: High-precision model-agnostic explanations](https://sameersingh.org/files/papers/anchors-aaai18.pdf)." In Thirty-Second AAAI Conference on Artificial Intelligence. 2018.
* 🎧 Data Skeptic Podcast Episode “[Black Boxes are not Required](https://dataskeptic.com/blog/episodes/2020/black-boxes-are-not-required)” with Cynthia Rudin (32min)



## Lecture: Debugging, Data Provenance, and Reproducability (2 Lectures) ![Requirements](https://img.shields.io/badge/-Requirements-Green.svg) ![Implementation/Operations](https://img.shields.io/badge/-Implementation/Operations-Yellow.svg) ![Quality Assurance](https://img.shields.io/badge/-Quality%20Assurance-Orange.svg)

Overview:

* Goal: Explaining why decisions have been made
* Stacking and composing AI components
* Documenting and tracking data provenance (modeling), "visibility debt", techniques for automated tracking
* Versioning of code, data, and models
* Logging and audit traces
* Strategies for debugging and improving models
* (Explainable machine learning and robustness techniques for debugging)
* (“Origin tracking” during learning – identifying influential training data)

Learning goals:

* Judge the importance of data provenance, reproducibility and explainability for a given system
* Create documentation for data dependencies and provenance in a given system
* Propose versioning strategies for data and models
* Test systems for reproducibility

Readings:

* 🗎 Halevy, Alon, Flip Korn, Natalya F. Noy, Christopher Olston, Neoklis Polyzotis, Sudip Roy, and Steven Euijong Whang. "Goods: Organizing google's datasets." In Proceedings of the 2016 International Conference on Management of Data, pp. 795-806. ACM, 2016.
* 🗎 Gulzar, Muhammad Ali, Matteo Interlandi, Tyson Condie, and Miryung Kim. "Debugging big data analytics in spark with bigdebug." In Proceedings of the 2017 ACM International Conference on Management of Data, pp. 1627-1630. ACM, 2017.
* 🕮 Hulten, Geoff. "Building Intelligent Systems: A Guide to Machine Learning Engineering." (2018), Chapter 21 (Organizing Intelligence) – 23 (Orchestration)
* 🗎 Sugimura, Peter, and Florian Hartl. "Building a Reproducible Machine Learning Pipeline." *arXiv preprint arXiv:1810.04570* (2018).



## Lecture: Fostering Interdisciplinary Teams: MLOps, AI Engineering, DevOps ![Process](https://img.shields.io/badge/-Process-Grey.svg)

Overview:

* Different roles in developing AI-enabled systems and their respective goals and concerns
* Communication strategies for cross-disciplinary teams
  - Understand basic management, engineering, science, and operations mindsets
  - Experimentation (notebooks) vs production
  - Going beyond accuracy, pipelines not models
  - Communicating the importance of process
* Agile techniques in AI-enabled systems
* Infrastructure and tools to foster collaboration, learning from DevOps

Learning goals:

* Plan development activities in an inclusive fashion for participants in different roles
* Describe agile techniques and tools to address common process and communication issues

Readings:

* 🗎 Kim, M., Zimmermann, T., DeLine, R., & Begel, A. (2017). [Data scientists in software teams: State of the art and challenges (Links to an external site.)](https://andrewbegel.com/papers/data-scientists.pdf ). *IEEE Transactions on Software Engineering*, *44*(11), 1024-1038.



## Lecture: Deployment and Operations at Scale ![Implementation/Operations](https://img.shields.io/badge/-Implementation/Operations-Yellow.svg)

Overview:

* Build vs buy, cloud infrastructure for learning and deployment
* Automated configuration management challenges and tools (Kubernetis, puppet, ansible)
* Overview of cloud infrastructure services (containers, serverless, app engines, ...) and relevant tradeoffs
* Logging and analysis at scale
* Debugging and monitoring tools for distributed systems and for AI components, including latency and resource consumption; deciding when to send alerts and how
* AIOps, runtime adaptation, anomaly detection

Learning goals:

* Describe common deployment options and their tradeoffs
* Design and justify a scalable deployment strategy for a given system
* Automate common configuration management tasks
* Devise a monitoring strategy and suggest suitable components for implementing it
* Diagnose common operations problems

Readings:

* tbd



