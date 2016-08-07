## Valx_core.py
a Python tool to extract and structure numeric lab test comparison statements from text

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

