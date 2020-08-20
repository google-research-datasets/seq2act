# Seq2act

This repository contains the opensource version of the datasets that were used
for the research described in "Mapping Natural Language Instructions to Mobile
UI Action Sequences" by Yang Li, Jiacong He, Xin Zhou, Yuan Zhang, and Jason
Baldridge, which is accepted in 2020 Annual Conference of the Association for
Computational Linguistics (ACL 2020).

The three datasets were used for different parts of training and testing of
models that ground natural language to UI actions as described in the paper.

-   AndroidHowTo: annotated action phrase spans in HowTo instructions
-   Rico-SCA: synthetic grounded descriptions of actions for mobile user
    interfaces
-   PixelHelp: instructions for performing common tasks on Google Pixel phones
    with labeled actions in steps.

See README.md in each subfolder for details about each dataset.

Note: The original datasets can not be released due to the copyright. The
AndroidHowTo and PixelHelp datasets released here are re-created from a public
source for opensource purposes. They are different from the original dataset
that the paper was based on thus result in slightly different performance.

If you use any of the materials, please cite the following paper.

```
@inproceedings{seq2act,
  title = {Mapping Natural Language Instructions to Mobile UI Action Sequences},
  author = {Yang Li and Jiacong He and Xin Zhou and Yuan Zhang and Jason Baldridge},
  booktitle = {Annual Conference of the Association for Computational Linguistics (ACL 2020)},
  year = {2020},
  url = {https://www.aclweb.org/anthology/2020.acl-main.729.pdf},
}
```
