![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)
![Pandas](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white)
![Numpy](https://img.shields.io/badge/Numpy-777BB4?style=for-the-badge&logo=numpy&logoColor=white)
![PyCharm](https://img.shields.io/badge/PyCharm-000000.svg?&style=for-the-badge&logo=PyCharm&logoColor=white)

![Python](https://img.shields.io/badge/Python-3-brightgreen)

# SRPOL - A lexicon based framework for sentiment strength of Serbian texts

Identifying the semantic orientation or polarity of words is one of the most important topics in sentiment analysis tasks.

In this work, we propose a new lexicon based approach for text polarity detection using sentiment triggers which are adding contextual semantic during the analysis. The existing word polarity dictionary in Serbian has been extended containing approximately 15000 words annotated with polarity strength. Serbian sentiment framework (SRPOL), relying on the new lexicon and the following sentiment triggers:
- Adverb Modifiers
  
```math 
\textit{"\textbf{Veoma}\ ($\rightarrow$ MOD=1.2)\ \textbf{dobar}\ (p=+0.43)\ film..." $\xrightarrow[]{1.2 \times (+0.43) }$ +0.52}
```

### Negations
  
```math
\textit{"Film\ \textbf{nije}\ ($\rightarrow$ NEG)\ \textbf{zanimljiv}" (p=+0.53) $\xrightarrow[\times (-1)]{+0.53 }$ -0.53}
```

### Exclamation Marks
  
```math 
\textit{"Odličan film\textbf{!}"($\leftarrow\times$ 1.06)} $\xrightarrow[\times 1.06]{p=+0.57}$+0.60
```

### Elongated Words
  
```math 
\textit{"Tako\ \textbf{dooooosadan} (p=-0.24)..." $\xrightarrow[1.27]{\times 1.05^{chr(o)} }$ "Tako\ \textbf{dosadan}..."(p=-0.30)}
```

### Emoticons and Emojis
  
```math

\textit{"Divan (p=+0.4)\ film (p=+0.14) 😍 (p=+0.678)" $\xrightarrow[]{}$ +0.41}
```

### Segmentation

```math 
P_{text} = \frac{\sum_{i}{S}w_{i} * P_{s}^{i}}{\sum_{i}^{S}w_{i}}, w_{i}=\sum_{m}^{S}|sign(P_{s}^{i}) = sign(P_{s}^{m})|
```
```math 
P_{s} = \frac{\sum_{i}^{k}P_{w}^{i}}{k}
```

