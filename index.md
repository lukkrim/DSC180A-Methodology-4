---
title: DSC 180A Methodology Assignment 4
---

# DSC 180A Methodology Assignment 4

**Name:** Samson Wan  
**UCSD Email:** r1wan@ucsd.edu  
**Section:** DSC 180A, Section 001  
**Mentor:** Professor Alex Warstadt  
**Capstone Topic:** BabyLM

**1. What is the most interesting topic covered in your domain this quarter?**

The most interesting topic to me has been knowledge distillation, especially self-distillation and reverse distillation in language model pretraining. I initially thought distillation mainly involved transferring knowledge from a larger model to a smaller one. Learning that a model can benefit from a teacher of the same size, or even a smaller teacher, made me more interested in how the training signal affects learning. This is particularly relevant to our BabyLM project because we are exploring how models can learn more effectively from limited language data. I find it interesting that improving performance might depend on how we use the available data, rather than simply increasing the model size or dataset.

**2. Describe a potential investigation you would like to pursue for your Quarter 2 Project.**

For Quarter 2, I would like to investigate whether combining self-distillation with dynamic sample reweighting during pretraining can improve learning under BabyLM’s limited-data setting. My initial approach would use a previously trained model as a teacher for a new model of the same architecture. The student would learn both from the actual next tokens and from the teacher’s predicted probability distributions. Instead of giving every training example equal weight, I would adjust each example’s contribution as training progresses, using signals such as the student’s loss or the teacher’s confidence.

My main question is whether dynamic reweighting helps the student learn more effectively from the teacher, or whether it causes the model to emphasize noisy examples or reinforce the teacher’s mistakes. I would compare four conditions: standard pretraining, self-distillation alone, dynamic reweighting alone, and their combination. Keeping the training data and student training budget comparable would help isolate the effect of each method. I would evaluate both overall performance and specific language abilities to understand where the combined approach helps.

**3. What is a potential change you’d make to the approach taken in your current Quarter 1 Project?**

One change I would make is to include more targeted error analysis alongside aggregate benchmark scores. During our evaluation discussions, I became interested in cases where a model appears to recognize the words in a sentence but still confuses who performed an action or who received something. An overall score may hide these differences in understanding. I would create controlled sentence pairs that change a specific relationship, such as reversing the subject and object, and examine whether the model consistently distinguishes them. This would help us identify weaknesses in the current approach and choose future experiments based on specific errors.

**4. What other techniques would you be interested in using in your project?**

I would also be interested in exploring curriculum learning, teacher ensembles, and confidence-based weighting. Curriculum learning could let us investigate whether the order of training examples affects how efficiently the model learns from limited data. Teacher ensembles could provide a way to examine whether students benefit from combining models with different strengths. Confidence-based weighting could help us test when the student should rely more heavily on a teacher’s predictions, although we would need to check whether that confidence actually reflects accuracy. These techniques would let us explore how example selection and teacher guidance interact during pretraining.
