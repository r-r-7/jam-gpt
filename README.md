# Jam-gpt

An Experimental Reimplementation of [large language model (LLM)](https://en.wikipedia.org/wiki/Large_language_model#:~:text=References-,Large%20language%20model,-19%20languages) for research and development of it architectures and design process and create a simple and fast framework for training and fine-tuning medium-sized [Generative Pretrained Transformers (GPT)](https://en.wikipedia.org/wiki/Generative_pre-trained_transformer#:~:text=Generative%20pre%2Dtrained,20%20languages)

<p align="center">
<img src="https://user-images.githubusercontent.com/80915494/263127835-0509942a-0528-4471-96fa-8eda3d4f159c.jpeg" width="50%" height="50%" >
</p>

## Installation :

use pip and install it in your local site-packages directory

```bash
pip install git+https://github.com/Lokeshwaran-M/jam-gpt.git
```
## Example :

```python

from jam_gpt import Data, Tokenizer, Config, LM, Model

tok = Tokenizer()


def gen_model(model_name,path):

    # data collection
    data = Data.get(path)

    # tokanization
    tok.set_encoding(model_name, data)
    tok.get_encoding(model_name)

    # setting parameters
    args = Config.pass_args()
    args[0] = tok.n_vocab
    print(tok.n_vocab)

    # model genration
    test_model = Model()
    lm = LM()

    test_model.set_parameters(args)
    lm.set_parameters(args)

    m = test_model.set_model(lm.BigramLanguageModel())

    test_model.set_data(Data.train_test_split(tok.encode(data)))

    test_model.optimize()

    test_model.train()

    print(tok.decode(test_model.generate()))


gen_model("test-m","data.txt")

```

## DOCS :

[Jam-gpt docs](./docs/jam-gpt.md) will give you the useage and explanation of the jam-gpt library

1 [ setup](./docs/jam-gpt.md#1-setup)  
2 [ Collecting data](./docs/jam-gpt.md#2-collecting-data)  
3 [ Tokenization](./docs/jam-gpt.md#3-tokenization)  
4 [ configurator]()  
5 [ Language Model (LM)]()  
6 [ Model generator]()


## credits :

kudos to [Andrej karpathy](https://github.com/karpathy) for his lectures on deep learning 