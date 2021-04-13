# Classical-Chinese-NER-RE-Dataset
A dataset used for NLP tasks.

## Named Entity Extraction

There are 6 types of entities named "PER"(person), LOC"(location), "ORG"(orgnization)", "JOB"(job), "BOO"(book), "WAR"(war). 

### Statistics

| # PER | # LOC | # ORG | # JOB | # BOO | # WAR | # Total |
| ----- | ----- | ----- | ----- | ----- | ----- | ------- |
| 13472 | 4149  | 2100  | 3178  | 157   | 6     | 23362   |

## Relation Extraction

### Data Format

* `.jsonl`

* ```
  {"h": {"name": "衡山王", "pos": [44, 47], "type": "PER"}, "t": {"name": "芮", "pos": [42, 43], "type": "PER"}, "relation": "同名于", "text": "当阳君黥布为楚将，常冠军，故立布为九江王，都六。鄱君吴芮率百越佐诸侯，又从入关，故立芮为衡山王，都邾"}
  ```

### Data Cleaning and Augmentation

We delete the relations the number of which is less than 20.  Also, if the relation is bidirectional, for example, A's father is B, inversely, B's son is A,  we do complementations.

### Statistics

* **Known relations:** the real relations.

* **Unknown relations:** to increase the robustness and generalization ability of our relation extraction model, we generate some unknown relations accoring to known relations randomly.

| # Known relations | Unknown |
| ----------------- | ------- |
| 4825              | 218365  |

