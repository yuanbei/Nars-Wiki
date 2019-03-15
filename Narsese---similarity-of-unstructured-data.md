NARS is able to compute the similarity between arbitrary unstructured information.

```
<(*,this, _d0) --> wordin>.
<(*,duck, _d0) --> wordin>.
<(*,is, _d0) --> wordin>.
<(*,green, _d0) --> wordin>.

<(*,green, _d1) --> wordin>.
<(*,ants, _d1) --> wordin>.
<(*,may, _d1) --> wordin>.
<(*,be, _d1) --> wordin>.
<(*,ducks, _d1) --> wordin>.

<duck <-> ducks>.

<_d0<->_d1>?"
```

A script to generate the narsese from text may look like this:
```python
# print the narsese for the tokens in a article or section
def printTokensN(text, datasetNumber):
	text = text.lower()

	# replace special letters with spaces
	for i in[".",",",";","(",")","[","]"]:
	    text=text.replace(i, " ")

	tokens = text.split(" ")
	for iToken in tokens:
	    if not iToken in ["", ".", ";"]:
	        print("<(*," + iToken + ", _d" + str(datasetNumber) + ") --> wordin>.")




text = "A neural network is a network or circuit of neurons, or in a modern sense, an artificial neural network, composed of artificial neurons or nodes.[1] Thus a neural network is either a biological neural network, made up of real biological neurons, or an artificial neural network, for solving artificial intelligence (AI) problems."
datasetNumber = 0
printTokensN(text, datasetNumber)



text = "Machine learning (ML) is the scientific study of algorithms and statistical models that computer systems use to effectively perform a specific task without using explicit instructions, relying on patterns and inference instead. It is seen as a subset of artificial intelligence. Machine learning algorithms build a mathematical model of sample data, known as \"training data\", "
datasetNumber = 1
printTokensN(text, datasetNumber)


text = "Machine learning has gone from the the realm of a relatively small number of data scientists to the mainstream of analysis and business. And while this has resulted in a plethora of innovations and improvements for organizations worldwide, its also provoked reactions ranging from curiosity to anxiety among people everywhere."
datasetNumber = 2
printTokensN(text, datasetNumber)


# ask questions to know how similar the text pieces are

print("<_d0<->_d1>?")
print("<_d1<->_d2>?")
```

Additionally n-grams may get used to increase the accuracy.