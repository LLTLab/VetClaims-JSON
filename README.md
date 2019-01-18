# VetClaims-JSON
This repository contains JSON decision models for analyzed disability-claim decisions issued by the Board of Veterans' Appeals of the U.S. Department of Veterans Affairs.

Those models contain five properties or elements:

<b>docID</b>: The value is the citation number of the decision.

<b>sentences</b>: This array contains the subset of classified or annotated sentences from the decision that pertain to PTSD.

NOTE: THIS ARRAY LISTS THE CLASSIFIED SENTENCES THAT SHOULD BE USED FOR MACHINE LEARNING.

The sentID is composed of the citation number of the decision, plus the paragraph number, plus the number of the sentence within that paragraph. As of now, the sentences are typed using only six rhetorical roles (rhetRole): Sentence (default value), FindingSentence, ReasoningSentence, EvidenceSentence, LegalRuleSentence, or CitationSentence. As of now, the sentences are not mapped to rule conditions (ruleCondition).

<b>ruleTree</b>: This is the representation of the logic of the substantive rules applicable to the case. Many of the annotated sentences will eventually be mapped to the appropriate node-proposition (rule condition) of this rule tree.

<b>text</b>: This contains the text of the original, entire decision (from which the annotated sentences have been extracted).

<b>metadm</b>: //This contains selected metadata about the decision.
