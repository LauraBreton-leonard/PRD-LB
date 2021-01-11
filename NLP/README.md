# NLP: Natural Language Processing  

## Introduction  

Le NLP ou Traitement Automatique du Language Naturel est un domaine de l'inelligence artificielle qui englobe tous les outils destinés au traitement du language. Nous nous sommes intéressés particulièrement à un de ses domaines d'application: la classification de texte.
Notre objectif est d'identifier la nature d'une ligne d'un recu de magasin (nom du magasin, adresse, total...).

<img src="https://github.com/LauraBreton-leonard/PRD-LB/blob/main/NLP/ReadmeContent/SchemaObjectif.png" width="1000" height="500"/>  

L'état de l'art actuel sur le NLP fait ressortir de nombreux types d'algorithmes de deep learning ( réseaux de neurones profonds) adaptés à notre tâche. Les principales méthodes utilisées et performantes sont l'utilisation d'un réseau convolutionnel comme pour le traitement d'image ou l'utilisation de couches LSTM (Long-Short Term Memory) bidirectionnelles. Ces deux méthodes nécéssitent une compréhension assez poussée des réseaux de neuronnes car ils doivent être adaptés au type et au nombre de données disponnibles pour l'entrainement(ajustement des paramètres: nombre de couches, taille, et hyperparametres: nombre d'epoch, taille de "batch").  

shema 1 et 2 

Une autre piste récente est développée dans le papier:"CUTIE: Learning to Understand Documents with Convolutional Universal Text Information Extractor, par
Xiaohui Zhao, Zhuo Wu, and Xiaoguang Wang":https://www.groundai.com/project/cutie-learning-to-understand-documents-with-convolutional-universal-text-information-extractor/  

Le manque de données et d'informations concernant cette méthode nous a poussé à abandonner l'idée de la reproduire, cependant, nous nous en sommes inspirés pour créer des modèles "multi input", (entrée multiples) dont la première entrée serait du texte, traité par l'une des deux méthodes précédente ( LSTM ou convolutionnel) et la deuxième entrée, une entrée numérique de position, traitée comme un problème de regression logistique simple ou réseau de neurones dense.

<img src="https://github.com/LauraBreton-leonard/PRD-LB/blob/main/NLP/ReadmeContent/SchemaMultiInput.png" width="250 height="500"/>
  
  
La troisième piste explorée et retenue pour ce projet est la piste du "fine tuning" et "transfert learning" d'un modèle existant de type transformers*, pré-entrainé comme le modèle BERT (et toutes ses déclinaisons) de Google.  

*transformers:(nouveau type de réseau utilisant le mechanisme d'attention et surpassant les anciennes méthodes telles que LSTM ou CNN)


Cette section contient deux parties:  
1) Fine-Tunned Bert Model pour la classification  
2) Modèles de classification divers: CNN, LSTM, Multi-input  

## Fine-Tunned Bert Model pour la classification  

Modèle BERT (Bidirectional Encoder Representations from Transformers ) de Google  
Ce modèle est un modèle de type transformers, pré-entrainé.  
Nous utilisons ici uplusieurs modèles de la librairie transformers de HuggingFace tel que BERT, Camembert, XLM, adaptés à la classification (et non au NER-Named Entity recognition)  
Avantages de ce modèle:  
-Optimisé par des professionnels  
-Pré-entrainé sur de nombreuses données  
-Transformers: dernière avancée en terme de NLP, et souvent la plus performante 

##  Modèles de classification divers  

Cette section comporte plusieurs modèles ( BiLSTM, CNN, Multi-Input...), écrits à la main et qui nécéssitent encore d'être optimisés au niveau des hyperparamètres et de leur conception même.  
Modèle 1: Regression Linéaire Naive Bayes  
Modèle 2: Embedding+Bi-LSTM avec et sans Attention layer  
Modèle 3: Embedding+CNN  
Modèle 4 et 5: Multi-Input models 
 

