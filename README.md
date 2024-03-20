# RationaleMappingsDataset

We publish IRT and CRT for three tasks of interest, i.e. Sentiment Analysis (SA), Text Summarization (TS) and Question Answering (QA).
Each file contains a json array of annotated instances. In the case of IRT, each instance is associated with an array "trees" containing all the RT provided for that instance. In the case of CRT, each instance is the CRT for the texts stored in the root.

The attributes of the documents stored in each file are listed below. 

## IRT_SA

- _id: unique id;
- trees: a vector containing all the RT provided for the instance;
- text: the data point's input text;
- sentiment: the data point's output, i.e., the sentiment of the input text.

### SA RT documents attributes - attributes of the documents stored in the trees vector

- mappings: RMs in the IRT;
- text: the data point's input text;
- sentiment: the data point's output, i.e., the sentiment of the input text.

## CRT_SA

- mappings: all the RM provided for the instance;
- total: total number of IRTs merged for creating the CRT;
- text: the data point's input text;
- sentiment: the data point's output, i.e., the sentiment of the input text.

## SA Mappings attributes

### External Mappings

- text_1: the mapping's text. This is a snippet of the input's text;
- label: the label of the mapping. It coincides with the data point's sentiment;
- mapping_type: External Mapping;
- indices_text_1: a vector containing the position of the first and last character of text_1 within the input's text sentence it comes from;
- offset: a vector containing the position of the first and last character of the text_1 within the input's text (ONLY FOR SENTENCE-LEVEL MAPPINGS);
- mappings: a vector containing the node's children in the tree. If the node has no children, the vector is empty;
- counter: the number of IRT the node is found in (ONLY FOR  MAPPINGS IN CRTS);
- perc: the number of IRT the node is found in over the total number of IRTs used for creating the CRT (ONLY FOR  MAPPINGS IN CRTS)


### Resolution Mappings

- text_1: the mapping's first text. This is a snippet of the input's text;
- indices_text_1: a vector containing the position of the first and last character of text_1 within the input text;
- text_2: the mapping's second text. This is a snippet of the input's text;
- indices_text_2: a vector containing the position of the first and last character of text_2 within the input text;
- mapping_type: Resolution Mapping;
- label: Coreference.
- counter: the number of IRT the node is found in (ONLY FOR  MAPPINGS IN CRTS);
- perc: the number of IRT the node is found in over the total number of IRTs used for creating the CRT (ONLY FOR  MAPPINGS IN CRTS)

## IRT_TS

- _id: unique id;
- trees: a vector containing all the RT provided for the instance;
- text: the data point's input text;
- summary: the data point's output text, i.e., the summary of the input text.

### TS RT documents attributes - attributes of the documents stored in the trees vector

- mappings: RMs in the IRT;
- text: the data point's input text;
- summary: the data point's output text, i.e., the summary of the input text.

## CRT_TS

- mappings: all the RM provided for the instance;
- total: total number of IRTs merged for creating the CRT;
- text: the data point's input text;
- summary: the data point's output text, i.e., the summary of the input text.

## TS Mappings attributes

### External Mappings

- text_1: the mapping's first text. This is a snippet of the input's text;
- text_2: the mapping's second text. This is a snippet of the summary. #If the label is Extractive, this text is equal to text_1 and therefore the attribute is not present
- label: the label of the mapping, i.e., Extractive or Abstractive. 
- mapping_type: External Mapping;
- indices_text_1: a vector containing the position of the first and last character of text_1 within the input's text sentence it comes from;
- indices_text_2: a vector containing the position of the first and last character of text_2 within the summary sentence it comes from;
- offset_text: a vector containing the position of the first and last character of the text_1 within the input's text (ONLY FOR SENTENCE-LEVEL MAPPINGS);
- offset_summary: a vector containing the position of the first and last character of the text_2 within the summary (ONLY FOR SENTENCE-LEVEL MAPPINGS);
- mappings: a vector containing the node's children in the tree. If the node has no children, the vector is empty;
- counter: the number of IRT the node is found in (ONLY FOR  MAPPINGS IN CRTS);
- perc: the number of IRT the node is found in over the total number of IRTs used for creating the CRT (ONLY FOR  MAPPINGS IN CRTS)


### Resolution Mappings

- text_1: the mapping's first text. This is a snippet of the input's text;
- indices_text_1: a vector containing the position of the first and last character of text_1 within the input text;
- text_2: the mapping's second text. This is a snippet of the input's text;
- indices_text_2: a vector containing the position of the first and last character of text_2 within the input text;
- mapping_type: Resolution Mapping;
- label: Coreference.
- origin: the text it comes from, i.e., summary or text.
- counter: the number of IRT the node is found in (ONLY FOR  MAPPINGS IN CRTS);
- perc: the number of IRT the node is found in over the total number of IRTs used for creating the CRT (ONLY FOR  MAPPINGS IN CRTS)

# IRT_QA

- _id: unique id;
- paragraph: the data poin's paragraph;
- question: the data point's question;
- answer: the data point's output text, i.e., the answer;
- trees: a vector containing all the RT provided for the instance;

### QA RT documents attributes - attributes of the documents stored in the trees vector

- question: the data point's question;
- paragraph: the data poin's paragraph;
- answer: the data point's output text, i.e., the answer;
- mappings: RMs in the IRT;

## CRT_QA

- mappings: all the RM provided for the instance;
- total: total number of IRTs merged for creating the CRT;
- text: the data point's input text;
- summary: the data point's output text, i.e., the summary of the input text.

## TS Mappings attributes

### External Mappings

- text_1: the mapping's first text. This is either a snippet of the question or of the answer;
- text_2: the mapping's second text. This is a snippet of either the paragraph or of the answer. If the label is Syntactic, this text is equal to text_1 and therefore the attribute is not present;
- label: the label of the mapping, i.e., Syntactic or Semantic.
- mapping_type: External Mapping;
- indices_text_1: a vector containing the position of the first and last character of text_1 within the text sentence it comes from (question or answer);
- indices_text_2: a vector containing the position of the first and last character of text_2 within the text sentence it comes from (paragraph or answer);
- offset_text: a vector containing the position of the first and last character of the text_2 within the input's text (ONLY FOR SENTENCE-LEVEL MAPPINGS - RELEVANT ONLY WHEN TEXT_2 COMES FROM THE PARAGRAPH).
- mappings: a vector containing the node's children in the tree. If the node has no children, the vector is empty;
- counter: the number of IRT the node is found in (ONLY FOR  MAPPINGS IN CRTS);
- perc: the number of IRT the node is found in over the total number of IRTs used for creating the CRT (ONLY FOR  MAPPINGS IN CRTS)


### Resolution Mappings

- text_1: the mapping's first text. This is a snippet of the input's text;
- indices_text_1: a vector containing the position of the first and last character of text_1 within the input text;
- text_2: the mapping's second text. This is a snippet of the input's text;
- indices_text_2: a vector containing the position of the first and last character of text_2 within the input text;
- mapping_type: Resolution Mapping;
- label: Coreference.
- origin: the text it comes from, i.e., question, paragraph, or answer.
- counter: the number of IRT the node is found in (ONLY FOR  MAPPINGS IN CRTS);
- perc: the number of IRT the node is found in over the total number of IRTs used for creating the CRT (ONLY FOR  MAPPINGS IN CRTS)

### Abstractive Mappings

- text_1: the mapping's text. This is a snippet of the question's text;
- indices_text_1: a vector containing the position of the first and last character of text_1 within the question's text;
- label: the label of the mapping, i.e., the question type, concatenated with the specialization if it is a WH-Question;
- mapping_type: Abstractive Mapping;
- mappings: a vector containing the node's children in the tree;
- counter: the number of IRT the node is found in (ONLY FOR  MAPPINGS IN CRTS);
- perc: the number of IRT the node is found in over the total number of IRTs used for creating the CRT (ONLY FOR  MAPPINGS IN CRTS)


# NOTES

- Mappings from IRTs are applied POS Tagging before being merged into CRT. In particular, entites beloning to the following categories are removed from the beginning and the end of each text in each mapping:  'ADP', 'CONJ', 'CCONJ', 'DET', 'PUNCT', 'SYMBOL', 'PRON'.

- Labels Extractive, Abstractive in Text Summarization and Syntactic, Semantic are applied by checking exact equality between the two texts. The number of mappings belonging to each level can be balanced by assigning an Extractive or Syntactic label also to the texts that are similar above a desired threshold, possibly after having applied stemming/lemmatization on them.

- Resolution Mappings are stored in the tree's root for simplicity. 
