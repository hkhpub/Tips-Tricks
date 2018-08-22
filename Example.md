```python
def create_training_data(corpus_raw, WINDOW_SIZE=2):
    sentences_list = corpus_raw.split('.')

    sentences = []
    words_list = []
    for sent in sentences_list:
        sent_words = sent.split()
        sentences.append(sent_words)

        for word in sent_words:
            words_list.append(word)

    print("total words: %d" % len(words_list))

    words_list = set(words_list)
    vocab_size = len(words_list)
    print("vocabulary size: %d" % vocab_size)

    word2idx = dict()
    idx2word = dict()
    for i, w in enumerate(words_list):
        word2idx[w] = i
        idx2word[i] = w
```
