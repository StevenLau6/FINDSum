# FINDSum

![](https://img.shields.io/badge/version-v1.0-blue.svg)
![](https://img.shields.io/badge/language-ENG-lightgrey.svg)
[![](https://img.shields.io/badge/license-ODCBy-green.svg)](https://opendatacommons.org/licenses/by/1-0/)
[![](https://img.shields.io/badge/author-@sq-red.svg)](https://stevenlau6.github.io/)

A Large-Scale Dataset for Long Text and Multi-Table Summarization

Paper [link](https://aclanthology.org/2022.findings-emnlp.145/)

## License
FINDSum is licensed under [ODC-BY](https://opendatacommons.org/licenses/by/1-0/).

## Download

Download from Google Drive [link](https://drive.google.com/drive/folders/1O8HwUOp0Uxepc-SF9Oq2alxWHz03FEUE?usp=sharing)


When using the FINDSum dataset in a product or service, or including data in a redistribution, please cite the following paper:

```
@inproceedings{liu-etal-2022-long,
    title = "Long Text and Multi-Table Summarization: Dataset and Method",
    author = "Liu, Shuaiqi  and
      Cao, Jiannong  and
      Yang, Ruosong  and
      Wen, Zhiyuan",
    booktitle = "Findings of the Association for Computational Linguistics: EMNLP 2022",
    month = dec,
    year = "2022",
    address = "Abu Dhabi, United Arab Emirates",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2022.findings-emnlp.145",
    pages = "1995--2010",
}
```

## FAQ

Q1: How to load these data files?

A1: You can use pd.read_csv in pandas to load the text files and use json.loads to load the tuple files.

```
# load the text files
import pandas as pd
input_csv_file_path="TEXT_CSV_PATH"
input_pd = pd.read_csv(input_csv_file_path, sep=',')


# load the tuple files
import json
input_file_name="TUPLE_FILE_PATH"
with open(input_file_name, 'r', encoding='UTF-8') as input_src_file:
    input_src_lines = input_src_file.readlines()
for input_src_line in input_src_lines:
    input_json = json.loads(input_src_line)
```

Q2: What is the "story_separator_special_tag" and "replace_table_token_i_th"?

A2: "story_separator_special_tag" separates input text segments. "replace_table_token_i_th" is the placeholder indicating the tables' location in text.

Q3: Does each row in the text file correspond to one row (JSON) in the tuple file?

A3: Yes

Q4: What are the attributes of each tuple in the tuple file?

A4: Each tuple in these file is [rowname_str, colname_str, cell_value_str, date_str, cell_row_index, cell_col_index]







