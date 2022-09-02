# customizedLM
----------
Customized LM that outputs attention weights. 

### Usage 
---------
```python
import modeling_gpt2
import tokenization_gpt2

model = GPT2Model.from_pretrained('gpt2')
tokenizer = GPT2Tokenizer.from_pretrained('gpt2')
text = "sample text gpt2"
tokens = tokenizer.tokenize(text) 
token_ids = tokenizer.convert_tokens_to_ids(tokens)
tokens_tensor = torch.tensor(token_ids).unsqueeze(0) 
model.eval()
output = model(tokens_tensor) 
attention_output = output[-1]
```

#### Acknowledgments
-------------
The code was gracefully refered from 
```
@inproceedings{vig-2019-multiscale,
    title = "A Multiscale Visualization of Attention in the Transformer Model",
    author = "Vig, Jesse",
    booktitle = "Proceedings of the 57th Annual Meeting of the Association for Computational Linguistics: System Demonstrations",
    month = jul,
    year = "2019",
    address = "Florence, Italy",
    publisher = "Association for Computational Linguistics",
    url = "https://www.aclweb.org/anthology/P19-3007",
    doi = "10.18653/v1/P19-3007",
    pages = "37--42",
}
```
