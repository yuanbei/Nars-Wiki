####Natural Language and Structure Learning

Besides the fact that the input window gives information about syntax error in your Narsese, input is not restricted to Narsese. You can put in any data you can think of, in which case it will be up to NARS to make sense of it in the current situation (for example in the examples).

![structurelearning](https://cloud.githubusercontent.com/assets/11791925/6994232/ca3ba5ae-db43-11e4-86c0-c5cfedee3be6.png)

Such a input will be transformed to

```
<(*,word-tom,word-is,word-the,word-brother,word-of,word-me) --> linepart>. :|: %1.00;0.90%
```

where the words are changed automatically so that the words won't conflict with the concepts the words represent. See [Natural Language Processing](https://github.com/opennars/opennars/wiki/Natural-Language-Processing) wiki page for more information of how such a input will be interpreted according to the current situation. Also "Natural Language Processing by Reasoning and Learning" is relevant here: http://www.cis.temple.edu/~pwang/Publication/NLP.pdf