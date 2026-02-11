# quantumstd1

## Setup

```bash
python3.13 -m venv .venv
.venv/bin/pip install tensorflow tf-keras scikit-learn scipy numpy
```

## Run

```bash
.venv/bin/python pred_lstm.py -p ./data/stocknet-dataset/price/ourpped -o train
```

### Actions

| Flag | Action |
|------|--------|
| `-o train` | Train the model |
| `-o test` | Evaluate on val/test sets |
| `-o pred` | Save predictions to file |
| `-o adv` | Evaluate adversarial robustness |
| `-o latent` | Extract latent representations |

### Options

| Flag | Description | Default |
|------|-------------|---------|
| `-p` | Path to price data | `./data/stocknet-dataset/price/ourpped` |
| `-e` | Number of epochs | `150` |
| `-b` | Batch size | `1024` |
| `-l` | Sequence length | `5` |
| `-u` | LSTM hidden units | `32` |
| `-r` | Learning rate | `0.01` |
| `-a` | Use attention (0/1) | `1` |
| `-v` | Adversarial training (0/1) | `0` |
| `-hi` | Use hinge loss (0/1) | `1` |
| `-f` | Fixed random seed (0/1) | `0` |
| `-g` | Use GPU (0/1) | `0` |
| `-rl` | Reload saved model (0/1) | `0` |
| `-q` | Path to load model from | `./saved_model/acl18_alstm/exp` |
| `-qs` | Path to save model to | `./tmp/model` |

### Example

Train for 10 epochs with adversarial training:

```bash
.venv/bin/python pred_lstm.py -p ./data/stocknet-dataset/price/ourpped -o train -e 10 -v 1
```
