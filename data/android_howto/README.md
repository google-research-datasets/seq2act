# AndroidHowTo

## Data Description

`common_crawl_annotation.csv` contains common crawl data sources for extracting
instruction text data, and their corresponding human labels for constructing the
AndroidHowTo dataset, which can be used for training and evaluating models for
parsing action phrases from instruction text (see the following paper). For code
and instructions, please follow
[https://github.com/google-research/google-research/blob/master/seq2act/data_generation/README.md](https://github.com/google-research/google-research/blob/master/seq2act/data_generation/README.md)

If you use the dataset, please cite the following paper.

```
@inproceedings{seq2act,
  title = {Mapping Natural Language Instructions to Mobile UI Action Sequences},
  author = {Yang Li and Jiacong He and Xin Zhou and Yuan Zhang and Jason Baldridge},
  booktitle = {Annual Conference of the Association for Computational Linguistics (ACL 2020)},
  year = {2020},
  url = {https://arxiv.org/pdf/tbd.pdf},
}
```

## Data Format

Each line of `common_crawl_annotation.csv` contains annotation of one task from
one annotatior. See table below for all the features:

| Feature Name    | Type   | Content                                           |
| --------------- | ------ | ------------------------------------------------- |
| Url             | string | url of the web page which contains instructions to fulfill a task on a mobile system. |
| Index           | int    | the index of instruction in the webpage. Some webpages may contain several instructions. Index+Url can be used to identify an instruction in this dataset. |
| Warc_file       | string | the warc file name where this instruction is coming from. |
| Annotation      | string | human annotations for phrases (spans) describe each action in steps, in which each step has: 1) verb_refs: int, the positions of verb in the instruction_str; 2) obj_refs\: int, the position of the substring of the UI element in the Instruction_str; 3) input_refs\: int, the position of the string user input in |
| Agreement_count | int    | mostly 1~3, how many annotators for the this annotation  |
