## Valx
a Python tool to extract and structure numeric lab test comparison statements from text

Objectives: To develop an automated method for extracting and structuring numeric lab test comparison statements from text and evaluate the method using clinical trial eligibility criteria text. Methods: Leveraging semantic knowledge from the Unified Medical Language System (UMLS) and domain knowledge acquired from the Internet, Valx takes 7 steps to extract and normalize numeric lab test expressions: 1) text preprocessing, 2) numeric, unit, and comparison operator extraction, 3) variable identification using hybrid knowledge, 4) variable - numeric association, 5) context-based association filtering, 6) measurement unit normalization, and 7) heuristic rule-based comparison statements verification. Our reference standard was the consensus-based annotation among three raters for all comparison statements for two variables, i.e., HbA1c and glucose, identified from all of Type 1 and Type 2 diabetes trials in ClinicalTrials.gov. Results: The precision, recall, and F-measure for structuring HbA1c comparison statements were 99.6%, 98.1%, 98.8% for Type 1 diabetes trials, and 98.8%, 96.9%, 97.8% for Type 2 Diabetes trials, respectively. The precision, recall, and F-measure for structuring glucose comparison statements were 97.3%, 94.8%, 96.1% for Type 1 diabetes trials, and 92.3%, 92.3%, 92.3% for Type 2 diabetes trials, respectively. Conclusions: Valx is effective at extracting and structuring free-text lab test comparison statements in clinical trial summaries. Future studies are warranted to test its generalizability beyond eligibility criteria text. The open-source Valx enables its further evaluation and continued improvement among the collaborative scientific community.

## Usage

<code>
import Valx_core
</code>

### Clean text by preprocessing

<code>
Valx_core.preprocessing (text)
</code>

### Split eligibility criteria text into inclusion and exclusion sections 

Please ignore this step if the text is not clincial trial eligibility criteria text

<code>
Valx_core.split_text_inclusion_exclusion (text)
</code>

### Extract candidates containing numeric features

<code>
Valx_core.extract_candidates_numeric(text) 
</code>

### Identify numerical expressions
Identify expressions and formalize them into labels, e.g., "&lt;VML(tag) L(logic, e.g., greater_equal)=X U(unit)=X&gt;value&lt;/VML&gt;"

<code>
Valx_core.formalize_expressions (candidates[])
</code>

### Identify variable mentions and map them to names

<code>
Valx_core.identify_variable(expression_text, feature_dict_dk, fea_dict_umls)
</code>

### Associate variable and its related numerical values

<code>
Valx_core.associate_variable_values(expression_text)
</code>

### Context-based validation

<code>
Valx_core.context_validation(expressions)
</code>

### Unit conversion and value normalization

Normalize the unit and their corresponding values

<code>
Valx_core.normalization(feature_list, expressions)
</code>

### Heuristic rule-based validation

<code>
Valx_core.context_validation(expressions)
</code>


## Usage examples

<code>Valx_CTgov.py</code>
demostrating how to use the Valx for extracting and structuring certain types of numeric lab test comparison statements from clincial trial eligibility criteria texts using single CPU core.

<code>Valx_CTgov_multiCPUcores.py</code>
demostrating how to use the Valx for extracting and structuring certain types of numeric lab test comparison statements from clincial trial eligibility criteria texts using multiple CPU cores

## Online Demo

http://columbiaelixr.appspot.com/valx

## Versions

V0.9	The stable version with full functionality

V1.0	Add multi-CPU core support, enable set core number easily

V1.1	Separate rules from code to a csv file named as "rules.csv"

V1.2	Separate numeric feature list from code to a csv file named as "numeric_features.csv"

## Citation

Tianyong Hao, Hongfang Liu, Chunhua Weng. Valx: A system for extracting and structuring numeric lab test comparison statements from text. Methods of Information in Medicine. Vol. 55: Issue 3, pp. 266-275, 2016 <a href=http://www.ncbi.nlm.nih.gov/pubmed/26940748 target=_blank>on Pubmed</a>

## Contributors

Tianyong Hao

Chengtao Li (new Web user interface with online pattern editing function)
