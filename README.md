# VetClaims-JSON
This repository contains JSON decision models for analyzed disability-claim decisions issued by the Board of Veterans' Appeals of the U.S. Department of Veterans Affairs.

Those models contain five properties or elements:

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
