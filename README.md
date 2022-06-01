# MPDD: A Multi-Party Dialogue Dataset for Analysis of Emotions and Interpersonal Relationships
# Introduction
A dialogue dataset is an indispensable resource for building a dialogue system. Additional information like emotions and interpersonal relationships labeled on conversations enables the system to capture the emotion flow of the participants in the dialogue. However, there is no publicly available Chinese dialogue dataset with emotion and relation labels. In this paper, we collect the conversions from TV series scripts, and annotate emotion and interpersonal relationship labels on each utterance. This dataset contains 25,548 utterances from 4,142 dialogues. We also set up some experiments to observe the effects of the responded utterance on the current utterance, and the correlation between emotion and relation types in emotion and relation classification tasks.

# Format
The Multi-Party Dialogue Dataset (MPDD) consists of two files, dialogue.json and metadata.json.
The file dialogue.json contains the dialogues. Each dialogue has a unique case index value in the json file, and is a list composed of the utterances in speaking order. Every utterance in the list contains the speaker, content, and annotated labels shown in data format. The list of the listener in the utterance contains all listeners in this utterance with their relation type. The data format of dialogue.json is shown as follows.

```yaml
    {
        case index:
            [
                {
                    "speaker": speaker's name,
                    "utterance": utterance,
                    "listener":
                        [
                            {
                                "name": listener's name,
                                "relation": relation type between speaker and listener
                            }, ...
                        ],
                    "emotion": speaker's emotion type
                }, ...
            ]
    }
```
The metadata is given in metadata.json. The file defines all the emotion, relation types, and the sub-classes in the two perspectives, position, and field. The data format of metadata.json is shown as follows.

```yaml
    {
        "relation":
            [
                "parent", ...
            ],
        "field":
            {
                "family":
                    [
                        "parent", ...
                    ],
                "school":
                    [
                        "teacher", ...
                    ],
                "company":
                    [
                        "boss", ...
                    ],
                "others":
                    [
                        "couple", ...
                    ]
            },
        "position":
            {
                "superior":
                    [
                        "parent",
...
                    ],
                "peer":
                    [
                        "spouse", ...
                    ],
                "inferior":
                    [
                        "child",
...
                    ]
            },
        "emotion":
            [
                "fear",
...
            ]
    }
```    

# Download
Click [here](http://nlg.csie.ntu.edu.tw/nlpresource/MPDD/mpdd.zip) to download data.


# How to Cite this resource
Please cite the following paper when referring to MPDD in academic publications and papers.

Yi-Ting Chen, Hen-Hsen Huang, and Hsin-Hsi Chen. 2020. MPDD: A Multi-Party Dialogue Dataset for Analysis of Emotions and Interpersonal Relationships. In Proceedings of the 12th International Conference on Language Resources and Evaluation (LREC 2020), Marseille, France.
