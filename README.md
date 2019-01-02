# proof-dictionary

This dictionary is for [proofdict](https://github.com/proofdict/proofdict).

- Dictionary: <https://proofdict.github.io/proof-dictionary/redirect/?type=dictionary>
- Editor: <https://proofdict.github.io/proof-dictionary/redirect/?type=editor>
- JSON API: <https://proofdict.github.io/proof-dictionary/redirect/?type=api>

## Usage

### Add dictionary

If you want to add new rule to your dictionary, you can add new rule by following steps: 

Visit your [editor page](https://proofdict.github.io/proof-dictionary/redirect/?type=editor):

- <https://proofdict.github.io/proof-dictionary/redirect/?type=editor>

### Update dictionary

If you want to update the rule from your dictionary, you can edit it by following steps: 

1. Visit [_data/proofdict][]
2. Select the file for updating
3. Edit the file by click ![Edit this file](docs/assets/pencil.png) icon

### Remove dictionary

If you want to remove unnecessary rule from your dictionary, you can remove it by following steps: 

1. Visit [_data/proofdict][]
2. Select the file for removing
3. Remove the file by click ![Delete this file](docs/assets/trashcan.png) icon

### Test dictionary

You can check your proof-dictionary is valid format.

Run following command in your local:

    npm install
    npm test

[_data/proofdict]: _data/proofdict "dictionary data directory"
