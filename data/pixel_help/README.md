# PixelHelp

## Data Description

PixelHelp includes 187 multi-step instructions of 4 task categories deined in
[https://support.google.com/pixelphone](https://support.google.com/pixelphone)
and annotated by human. This dataset includes 88 general tasks, such as
configuring accounts, 38 Gmail tasks, 31 Chrome tasks, and 30 Photos related
tasks. This dataset is an updated opensource version of the original PixelHelp
dataset, which was used for testing the end-to-end grounding quality of the
model in paper "Mapping Natural Language Instructions to Mobile UI Action
Sequences". The similar accuracy is acquired on this version of the dataset.

If you use the dataset, please cite the following paper.

```
@inproceedings{seq2act,
  title = {Mapping Natural Language Instructions to Mobile UI Action Sequences},
  author = {Yang Li and Jiacong He and Xin Zhou and Yuan Zhang and Jason Baldridge},
  booktitle = {Annual Conference of the Association for Computational Linguistics (ACL 2020)},
  year = {2020},
  url = {https://www.aclweb.org/anthology/2020.acl-main.729.pdf},
}
```

## Data Format

Each example in dataset contains a task which can be performed on Android
platform, like "switch Wi-Fi settings", and a list of annotated features. We
label objects phrase in the instructions, perform the steps in an emulator
environment and record the screen information. See table below for all the
features:

| Feature Name            | Type   | Content                                  |
| ----------------------- | ------ | ---------------------------------------- |
| Task_id                 | int    | an unique id for each example            |
| Instruction_str         | string | English sentence describes a list of actions users can do sequentially on Android |
| Instruction_word_id_seq | int    | split Instruction_str to words and give each word an unique id |
| Instruction_rule_id     | int    | if the sentence is real or synthetic     |
| Ui_obj_str_seq          | string | English phrases/text of UI elements in all screens | 
| Ui_obj_word_id_seq      | int    | split Ui_obj_str_seq to words and give each word an unique id |
| Ui_obj_type_id_seq      | int    | UI element type                          |
| Ui_obj_clickable_seq    | int    | if UI element is clickable               |
| Ui_obj_cord_x_seq       | int    | X coordinates of UI elements             |
| Ui_obj_cord_y_seq       | int    | Y coordinates of UI elements             |
| Ui_obj_v_distance       | int    | vertical distance of any two UI elements |
| Ui_obj_h_distance       | int    | horizontal distance of any two UI elements |
| Ui_obj_dom_distance     | int    | distance of any two UI elements in dom tree |
| Ui_obj_dom_location_seq | int    | traversal order of a UI element in the dom tree |
| Verb_id_seq             | int    | verb for the action |
| Ui_target_id_seq        | int    | which UI elements is user actioned on    |
| Input_str_position_seq  | int    | the position of the string user input in the Instruction_str |
| Obj_desc_position_seq   | int    | the position of the substring of the UI element in the Instruction_str. |

This dataset contains 187 examples splitted in 10 shards in `tfrecord` format.
