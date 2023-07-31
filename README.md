**Valx: Extracting and Structuring Numeric Lab Test Comparison Statements from Text**

Valx is an automated tool designed to extract and structure numeric lab test comparison statements from text, with a focus on clinical trial eligibility criteria. It leverages semantic knowledge from the Unified Medical Language System (UMLS) and domain-specific information to achieve its goal. This updated version of Valx is Python 3 compatible.

**Please Note**: The multi-CPU core support (V1.0) has not been thoroughly tested, and it may not run successfully in its current state.

### Usage

1. **Preprocessing Text**:

```python
import Valx_core

# Clean text by preprocessing
Valx_core.preprocessing(text)
```

2. **Splitting Eligibility Criteria Text**:

*Note: Skip this step if the text is not clinical trial eligibility criteria.*

```python
# Split eligibility criteria text into inclusion and exclusion sections
Valx_core.split_text_inclusion_exclusion(text)
```

3. **Extracting Candidates Containing Numeric Features**:

```python
# Extract candidates containing numeric features
Valx_core.extract_candidates_numeric(text)
```

4. **Identifying Numerical Expressions**:

```python
# Identify expressions and formalize them into labels
Valx_core.formalize_expressions(candidates)
```

5. **Identifying Variable Mentions and Mapping**:

```python
# Identify variable mentions and map them to names
Valx_core.identify_variable(expression_text, feature_dict_dk, fea_dict_umls)
```

6. **Associating Variable and Its Related Numerical Values**:

```python
# Associate variable and its related numerical values
Valx_core.associate_variable_values(expression_text)
```

7. **Context-Based Validation**:

```python
# Context-based validation
Valx_core.context_validation(expressions)
```

8. **Unit Conversion and Value Normalization**:

```python
# Normalize the unit and their corresponding values
Valx_core.normalization(feature_list, expressions)
```

9. **Heuristic Rule-Based Validation**:

```python
# Heuristic rule-based validation
Valx_core.context_validation(expressions)
```

### Usage Examples

- `Valx_CTgov.py`: Demonstrates how to use Valx for extracting and structuring certain types of numeric lab test comparison statements from clinical trial eligibility criteria texts using a single CPU core.

- `Valx_CTgov_multiCPUcores.py`: Demonstrates how to use Valx for extracting and structuring certain types of numeric lab test comparison statements from clinical trial eligibility criteria texts using multiple CPU cores.

### Online Demo

Visit the [Online Demo](http://columbiaelixr.appspot.com/valx) to try Valx and explore its capabilities.

### Versions

- V0.9: The stable version with full functionality.

- V1.0: Added multi-CPU core support, enabling easy configuration of core number. (*Note: Not tested with python3*)

- V1.1: Separated rules from code into a CSV file named "rules.csv."

- V1.2: Separated numeric feature list from code into a CSV file named "numeric_features.csv."

### Citation

Tianyong Hao, Hongfang Liu, Chunhua Weng. Valx: A system for extracting and structuring numeric lab test comparison statements from text. Methods of Information in Medicine. Vol. 55: Issue 3, pp. 266-275, 2016 [on Pubmed](http://www.ncbi.nlm.nih.gov/pubmed/26940748).

### Contributors

- Tianyong Hao

- Chengtao Li (new Web user interface with online pattern editing function)
