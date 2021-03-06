## Abstract
Separating the sounds of different instruments that compose a mixture has received great attention in the signal processing society. Yet, the task of separating sounds generated by the same type of instruments, e.g., the sounds of two guitars considered here, is much less explored. Such guitar mixtures are common in pop/rock songs, so being able to separate them has useful downstream applications. As the first attempt towards this task, we consider in this work sound mixtures of various synthetic acoustic and electric guitar timbres. Moreover, we approach this task with a score-informed setting, aiming to build a model that isolates out the sound source whose underlying musical score is given, regardless of the timbre of this target sound source. In other words, the model is built in a hope to be applicable to arbitrary guitar timbres, so as to deal with the rich diversity in timbre seen in guitar music. Specifically, we develop a score-informed version of Open-Unmix, and test its sensitivity to guitar timbre with five separation scenarios. This involves the case of unseen guitar timbres, and the case when the two guitars in the mixture have exactly the same timbre. Our experiments demonstrate the effectiveness of our design.

## Demo audio
The demo contains 15-second clips of the outputs from our proposed score-informed Open-Unmix with soft score encoding (**SI-Open-unmix-Soft**) and binary score encoding (**SI-Open-unmix-Binary**) and the original blind version of Open-Unmix (**SI-Open-unmix-Blind**) when confronted with **unseen** timbres. As mentioned in the abstract, we hope to train our model to be insensitive to timbre.

The first column indicates the guitar combinations of the songs, where ag+ag and eg+eg are abbreviations for two acoustic guitars and two electric guitars. The second column is the input audio mixture, while the third column is the target guitar that the model is asked to isolate out from the mixture. The last three columns are the output audio from the three models.

Scenario (a) Target guitar seen, non-target guitar unseen.

| Combination | Mixture | Target Guitar | SI-Open-unmix-Soft | SI-Open-unmix-Binary | SI-Open-unmix-Blind |
| ----------- | ------- | ------------- | ------------------ | -------------------- | ------------------- |
| ag+ag |<audio src="result/demo/a/ag_ag_Ice_Dance_-_Edward_Scissorhands_mix_1+D.wav" controls="" preload=""></audio>|<audio src="result/demo/a/ag_ag_Ice_Dance_-_Edward_Scissorhands_gt_1.wav" controls="" preload=""></audio>|<audio src="result/demo/a/ag_ag_Ice_Dance_-_Edward_Scissorhands_soft.wav" controls="" preload=""></audio>|<audio src="result/demo/a/ag_ag_Ice_Dance_-_Edward_Scissorhands_binary.wav" controls="" preload=""></audio>|<audio src="result/demo/a/ag_ag_Ice_Dance_-_Edward_Scissorhands_blind.wav" controls="" preload=""></audio>|
| eg+eg |<audio src="result/demo/a/eg_eg_Quelques_Sourires_mix_1+D.wav" controls="" preload=""></audio>|<audio src="result/demo/a/eg_eg_Quelques_Sourires_gt_1.wav" controls="" preload=""></audio>|<audio src="result/demo/a/eg_eg_Quelques_Sourires_soft.wav" controls="" preload=""></audio>|<audio src="result/demo/a/eg_eg_Quelques_Sourires_binary.wav" controls="" preload=""></audio>|<audio src="result/demo/a/eg_eg_Quelques_Sourires_blind.wav" controls="" preload=""></audio>|


Scenario (b) Target guitar unseen, non-target guitar seen

| Combination | Mixture | Target Guitar | SI-Open-unmix-Soft | SI-Open-unmix-Binary | SI-Open-unmix-Blind |
| ----------- | ------- | ------------- | ------------------ | -------------------- | ------------------- |
| ag+ag |<audio src="result/demo/b/ag_ag_Every_little_thing_mix_1+D.wav" controls="" preload=""></audio>|<audio src="result/demo/b/ag_ag_Every_little_thing_d_gt_0.wav" controls="" preload=""></audio>|<audio src="result/demo/b/ag_ag_Every_little_thing_soft.wav" controls="" preload=""></audio>|<audio src="result/demo/b/ag_ag_Every_little_thing_binary.wav" controls="" preload=""></audio>|<audio src="result/demo/b/ag_ag_Every_little_thing_blind.wav" controls="" preload=""></audio>|
| eg+eg |<audio src="result/demo/b/eg_eg_Death_after_Live_mix_1+D.wav" controls="" preload=""></audio>|<audio src="result/demo/b/eg_eg_Death_after_Live_d_gt_0.wav" controls="" preload=""></audio>|<audio src="result/demo/b/eg_eg_Death_after_Live_soft.wav" controls="" preload=""></audio>|<audio src="result/demo/b/eg_eg_Death_after_Live_binary.wav" controls="" preload=""></audio>|<audio src="result/demo/b/eg_eg_Death_after_Live_blind.wav" controls="" preload=""></audio>|

Scenario (c) Different unseen timbres for the target and non-target guitars

| Combination | Mixture | Target Guitar | SI-Open-unmix-Soft | SI-Open-unmix-Binary | SI-Open-unmix-Blind |
| ----------- | ------- | ------------- | ------------------ | -------------------- | ------------------- |
| ag+ag |<audio src="result/demo/c/ag_ag_Bush_mix_D+E.wav" controls="" preload=""></audio>|<audio src="result/demo/c/ag_ag_Bush_d_gt_0.wav" controls="" preload=""></audio>|<audio src="result/demo/c/ag_ag_Bush_soft.wav" controls="" preload=""></audio>|<audio src="result/demo/c/ag_ag_Bush_binary.wav" controls="" preload=""></audio>|<audio src="result/demo/c/ag_ag_Bush_blind.wav" controls="" preload=""></audio>|
| eg+eg |<audio src="result/demo/c/eg_eg_Heart_of_a_Dragon_mix_D+E.wav" controls="" preload=""></audio>|<audio src="result/demo/c/eg_eg_Heart_of_a_Dragon_e_gt_1.wav" controls="" preload=""></audio>|<audio src="result/demo/c/eg_eg_Heart_of_a_Dragon_soft.wav" controls="" preload=""></audio>|<audio src="result/demo/c/eg_eg_Heart_of_a_Dragon_binary.wav" controls="" preload=""></audio>|<audio src="result/demo/c/eg_eg_Heart_of_a_Dragon_blind.wav" controls="" preload=""></audio>|

Scenario (d) Same unseen timbre for both the target and non-target guitars

| Combination | Mixture | Target Guitar | SI-Open-unmix-Soft | SI-Open-unmix-Binary | SI-Open-unmix-Blind |
| ----------- | ------- | ------------- | ------------------ | -------------------- | ------------------- |
| ag+ag |<audio src="result/demo/d/ag_ag_Undecided_mix_D+D.wav" controls="" preload=""></audio>|<audio src="result/demo/d/ag_ag_Undecided_d_gt_1.wav" controls="" preload=""></audio>|<audio src="result/demo/d/ag_ag_Undecided_soft.wav" controls="" preload=""></audio>|<audio src="result/demo/d/ag_ag_Undecided_binary.wav" controls="" preload=""></audio>|<audio src="result/demo/d/ag_ag_Undecided_blind.wav" controls="" preload=""></audio>|
| eg+eg |<audio src="result/demo/d/eg_eg_The_Encounter_mix_D+D.wav" controls="" preload=""></audio>|<audio src="result/demo/d/eg_eg_The_Encounter_d_gt_0.wav" controls="" preload=""></audio>|<audio src="result/demo/d/eg_eg_The_Encounter_soft.wav" controls="" preload=""></audio>|<audio src="result/demo/d/eg_eg_The_Encounter_binary.wav" controls="" preload=""></audio>|<audio src="result/demo/d/eg_eg_The_Encounter_blind.wav" controls="" preload=""></audio>|


### Contact 
Chia-Ho Hsiung chiahohsiung@gmail.com or ch3472@columbia.edu
