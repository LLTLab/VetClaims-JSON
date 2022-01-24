# VetClaims-JSON
This repository contains analyzed disability-claim decisions issued by the Board of Veterans' Appeals ("BVA") of the U.S. Department of Veterans Affairs. These <b>analyzed decisions</b> are referred to as decision models, and they are contained in a JSON format. These decision models were created by the Research Laboratory for Law, Logic and Technology (<b>LLT Lab</b>) at the Maurice A. Deane School of Law at Hofstra University, in New York. The analysis consists of classifying selected sentences in those decisions according to their rhetorical role (see explanation below). These decision models are <b>found in the folder "BVA Decisions JSON Format"</b>.

The original text files for the original 50 BVA decisions are found in the folder "PTSD Dataset 50 Original Text Files." We initially analyzed 50 fact-finding decisions issued by the BVA from 2013 through 2017. We arbitrarily selected those decisions from adjudicated disability claims by veterans for service-related post-traumatic stress disorder (PTSD). PTSD is a mental health problem that some people develop after experiencing or witnessing a traumatic event, such as combat or sexual assault. For each of the 50 BVA decisions in our PTSD dataset, we extracted all sentences addressing the factual issues related to the claim for PTSD, or for a closely-related psychiatric disorder. This set of sentences is the dataset that we manually labeled and curated as the gold standard for our experiments. The “Reasons and Bases” section of the decision is the longest section, containing the Board’s statement of the evidence, its evaluation of that evidence, and its findings of fact on the relevant legal issues. Therefore, the vast majority of labeled sentences are from the portions of that section of these cases, insofar as they address the PTSD claim, or a closely-related psychiatric disorder.

Also in this repo is <b>a folder containing the protocols</b> (guidelines, criteria) for classifying a sentence as being of a particular semantic type (rhetorical role).

If you find an error in either a JSON file or a protocol, please let us know at <LLTLab@Hofstra.edu>.

Finally, there is a folder containing <b>the scripts and ML settings</b> for experiments reported in the paper: Vern R. Walker, Krishnan Pillaipakkamnatt, Alexandra M. Davidson, Marysa Linares and Domenick J. Pesce. 2019. "Automatic Classification of Rhetorical Roles for Sentences: Comparing Rule-Based Scripts with Machine Learning." In <i>Proceedings of the Third Workshop on Automated Semantic Analysis of Information in Legal Text (ASAIL 2019)</i>, Montreal, QC, Canada, 10 pages.

These BVA models contain five properties or elements:

<b>docID</b>: The value is the citation number of the decision.

<b>sentences</b>: This array contains the subset of classified or annotated sentences from the decision that pertain to the claim for disability benefits due to service-connected PTSD.

NOTE: THIS ARRAY LISTS THE CLASSIFIED SENTENCES THAT SHOULD BE USED FOR MACHINE LEARNING.

For each sentence, the <b>sentID</b> is composed of the citation number of the decision, plus the paragraph number, plus the number of the sentence within that paragraph. A sentence is classified using one or more of six <b>rhetorical roles</b> ("rhetRole"): Sentence (default value), FindingSentence, ReasoningSentence, EvidenceSentence, LegalRuleSentence, or CitationSentence. (Brief descriptions of these last five rhetorical roles are provided below.) A sentence might also be mapped to one or more <b>rule conditions</b> ("ruleCondition") in the rule tree (see next property).

<b>ruleTree</b>: This is the representation of the logic of the substantive rules applicable to the case. Some of the annotated sentences may be mapped to the appropriate node-proposition (rule condition) of this rule tree.

<b>text</b>: This contains the plain text of the original, entire decision (from which the annotated sentences have been extracted).

<b>metadm</b>: This contains selected metadata about the decision.

Five sentence rhetorical roles used in these JSON decision models:

1. FindingSentence. A finding sentence is a sentence that primarily states an authoritative finding, conclusion or determination of the trier of fact – a decision made “as a matter of fact” instead of “as a matter of law.”

2. ReasoningSentence. A reasoning sentence is a sentence that primarily reports the trier of fact’s reasoning based on the evidence, or evaluation of the probative value of the evidence, in making the findings of fact.

3. EvidenceSentence. An evidence sentence is a sentence that primarily states the content of the testimony of a witness, states the content of documents introduced into evidence, or describes other evidence.

4. LegalRuleSentence. A legal-rule sentence is a sentence that primarily states one or more legal rules in the abstract, without stating whether the conditions of the rule(s) are satisfied in the case being decided.

5. CitationSentence. A citation sentence is a sentence whose primary function is to reference legal authorities or other materials, and which usually contains standard notation that encodes useful information about the cited source.
