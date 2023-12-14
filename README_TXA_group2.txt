Questa cartella contiene i seguenti elementi: 
	- la cartella dataset_raw
	- la cartella dataset_first_task
	- la cartella dataset_second_task
	- i notebook: 
		- Group2_Preprocess.ipynb
		- Group2_ClassificationTask1.ipynb
		- Group2_ClassificationTask2.ipynb
		- Group2_Explainability.ipynb

Dataset_raw contiene tutti i dataset di SemEval-2015: questi sono i dataset di partenza, in diverse versioni: 
- figurative_clean contiene solo testo e tweet ID
- figurative_clean_onlyframes contiene solo frames + tweet ID
- task-11-training-data contiene tweet ID e score
- ironicFRAMES contiene ID tweet ironico e score e frames
- sarcasticFRAMES contiene ID tweet sarcastico e score e frames
- text_dataset dataset finale processato (i primi tre di questo elenco, uniti e senza duplicati)

Dataset_first_task contiene tutti i dataset che vengono utilizzati per il primo task di classificazione (figurative vs non figurative). Questi sono i dataset output dello step di preprocessing, già splittati in train e test. Ci sono diverse versioni: 
- testo + frame + syno_lower_mean + syn_mean
- testo + frame + syno_lower_mean + syn_mean + features di senticnet 
- testo + frame + syno_lower_mean + syn_mean vettorizzato con countvectorizer 
- testo + frame + syno_lower_mean + syn_mean vettorizzato con countvectorizer + features di senticnet 
- come il precedente, ma con feature selection 

Dataset_second_task  contiene tutti i dataset che vengono utilizzati per il secondo task di classificazione (ironic vs sarcastic). Questi sono i dataset output dello step di preprocessing, già splittati in train e test. Ci sono diverse versioni: 
- testo + frame + syno_lower_mean + syn_mean
- testo + frame + syno_lower_mean + syn_mean vettorizzato con countvectorizer
- testo + frame + syno_lower_mean + syn_mean vettorizzato con countvectorizer + features di senticnet
- come il precedente, ma con feature selection  

I notebook 
1. Group2_Preprocess.ipynb
2. Group2_ClassificationTask1.ipynb
3. Group2_ClassificationTask2.ipynb
4. Group2_Explainability.ipynb 

implementano rispettivamente: data understanding e preprocessing, il task di classificazione 1 (figurative vs non figurative), il task di classificazione 2 (sarcastic vs ironic) e la parte di explainability. Si consegna una versione già compilata dei notebook, quindi tutti gli output sono già visibili senza necessità di eseguire nuovamente. 

