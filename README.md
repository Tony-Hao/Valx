## Valx_core.py
a Python tool to extract and structure numeric lab test comparison statements from text

Objectives: To develop an automated method for extracting and structuring numeric lab test comparison statements from text and evaluate the method using clinical trial eligibility criteria text. 
Methods: Leveraging semantic knowledge from the Unified Medical Language System (UMLS) and domain knowledge acquired from the Internet, Valx takes 7 steps to extract and normalize numeric lab test expressions: 1) text preprocessing, 2) numeric, unit, and comparison operator extraction, 3) variable identification using hybrid knowledge, 4) variable - numeric association, 5) context-based association filtering, 6) measurement unit normalization, and 7) heuristic rule-based comparison statements verification. Our reference standard was the consensus-based annotation among three raters for all comparison statements for two variables, i.e., HbA1c and glucose, identified from all of Type 1 and Type 2 diabetes trials in ClinicalTrials.gov. 
Results: The precision, recall, and F-measure for structuring HbA1c comparison statements were 99.6%, 98.1%, 98.8% for Type 1 diabetes trials, and 98.8%, 96.9%, 97.8% for Type 2 Diabetes trials, respectively. The precision, recall, and F-measure for structuring glucose comparison statements were 97.3%, 94.8%, 96.1% for Type 1 diabetes trials, and 92.3%, 92.3%, 92.3% for Type 2 diabetes trials, respectively.
Conclusions: Valx is effective at extracting and structuring free-text lab test comparison statements in clinical trial summaries. Future studies are warranted to test its generalizability beyond eligibility criteria text. The open-source Valx enables its further evaluation and continued improvement among the collaborative scientific community.


##  Usage

import the file

`import Valx_core`

### identify numerical expressions

identify expressions and formalize them into labels

<code>
\>\>print(Valx_core.formalize_expressions("age 40 or older"))

\>\>age < VML Logic=greater_equal Unit=\>40</VML \>
</code>

### associate variable and its related numerical values

you can use

<code>
Valx_core.associate_variable_values(text)
</code>

### split eligibility criteria text into inclusion and exclusion sections

<code>
Valx_core.split_text_inclusion_exclusion(text)
</code>

### context validation

<code>
Valx_core.context_validation(text)
</code>

### normalization

normalize the unit and their corresponding values

<code>
Valx_core.normalization(nor_unit, exps)
</code>

## Citation
Please kindly cite the paper: Tianyong Hao, Hongfang Liu, Chunhua Weng. Valx: A system for extracting and structuring numeric lab test comparison statements from text. Methods of Information in Medicine. Vol. 55: Issue 3, pp. 266-275, 2016
