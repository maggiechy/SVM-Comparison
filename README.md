# SVM-Comparison

A [workflowr][] project.

An algorithmn for comparing the performance of different SVMs---Leave-one out experiment 

There are n positive samples and x samples as background. We picks 1 of the n positive samples and mix it randomly into half of the x samples. We build a model from the n-1 sample set and use this model to predict which samples in the x+1 sample set contain the positive signal---exhibit the same features showed in the n-1 sample set. The accuracy is evaluated via AUC (area under the ROC curve).

We compare SVDD (a one-class model) and general SVM. Here we use the entire unlabeled background set as negative examples.

Conclusion: We note the general upward trend in the performance of one-class models as alpha increases. Because a larger mixing proportion of the positive sample makes the mixtures look more like the positive class. The trend is not shared by v-SVM models, which are unable to identify samples with mixed stemness signal from others in the background. A potential explanation for the poor performance comes from sample locality in high-dimensional feature spaces. "An SVM can be viewed as a mechanical system, where the decision plane is a "stiff sheet" in mechanical equilibrium, upon which the training samples exert forces and torques. This effectively makes the model highly sensitive to noise and reduces its generalization to the unsampled portions of the feature space."

