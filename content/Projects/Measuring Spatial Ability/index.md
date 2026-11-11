---
title: "Measuring Spatial Ability"
summary: "A project designed to develop and validate a measure of spatial ability"
tags:
- Measurement
- Statistical Learning
- Factor analysis
- Item response theory
- R
external_link: ''
---

{{< github repo="kmather3/2D-Rotation-Task" showThumbnail=false >}}

## Project overview

Spatial reasoning-—the ability to mentally manipulate and rotate visual information—-is needed for daily tasks such as map-reading and navigation and is particularly important in some occupations across STEM fields. However, researchers have relatively few freely available tools for measuring specific spatial abilities––especially for assessing two-dimensional (2D) rotation ability, as most available instruments assess 3D rotation. I developed and evaluated an algorithmically generated, public domain measure of 2D rotation ability using data from the Synthetic Aperture Personality Assessment (SAPA) Project. 

**Some of our specific research questions were...**

- Does responding across 2D rotation ability items appear to be influenced by a single ability (i.e., spatial reasoning), or do different item types require different mental processes?

- How does 2D rotation ability relate to other cognitive abilities and personality traits?

- How do 2D rotation ability and 3D rotation ability compare across college majors and occupations?


**This is an example item** from the complete pool of 70. Each item presents participants with a large square containing 16 small shapes in a 4 × 4 array. To the right of this square, the same square was shown rotated 0–3 times by 90 degrees, with one of the corner pieces missing from the frame. To solve the problem, participants must select the answer that completes the figure from a set of multiple-choice options. Six of the eight multiple-choice options show a puzzle piece with 1 of the 16 small shapes, and the remaining two allowed participants to indicate that they did not know the answer or that the correct answer was not included among the answer options. Each item requirea either rotation of the large square, rotation of the answer option, rotation of both the large square and answer option, or rotation of neither (i.e., simple pattern matching).


<img src="/img/2D/R2Dfig16001.png" alt="2Dexample" width="500"/>

This item requires rotation of both the large square and the answer option to arrive at the correct answer ("G").


### Method

Using SAPA project data (*N* = 1,558,035), I evaluated the assessment's psychometric properties, including its factor structure and internal consistency, and used item response theory to estimate participants' spatial ability. 

To examine the items' construct validity, I explored relationships with other cognitive abilities and personality traits, and compared performance across college majors and occupations. In addition, I identified the job characteristics from the O*NET content model that were most strongly associated with spatial reasoning by applying the BISCUIT (Best Items Scales that are Cross Validated, Unit Weighted, Informative, and Transpatent) Technique. This is a statistical learning approach designed to identify informative predictors while accounting for the complexity of large, incomplete datasets (See [Elleman et al. (2021)](https://doi.org/10.1027/1015-5759/a000590) for more information).


### Results

Overall, findings indicated that the items demonstrate strong psychometric properties and hypothesized relationships with other constructs.

#### Psychometric Properties

Evaluation of the factor structure of the 70-item scale suggested the presence of four lower-order factors, which reflected differences in the items' mental rotation demands (i.e., whether they demanded rotation of the larger square and/or the answer option). Thus, unidimensionality was poor (ωh = 0.47), but improved when accounting for the specific variance associated with these lower-order factors (ωh = 0.66).

Because this task was developed primarily as a measure of 2D rotation ability, the 12 items that do not require any rotation were removed to improve the unidimensionality of the scale (although these items could still be useful for assessing other spatial skills, such as pattern detection). The removal of these items resulted in sufficient unidimensionality of the scale with the remaining 58 items (ωh = 0.77).

One additional item was removed from the scale before generating IRT scores due to its interference with generating accurate overall test scores. This item had unusually high difficulty and discrimination parameters, and appeared to have a challenging distractor response option, which deviates from other items included in the scale. 

Findings from the IRT analyses indicated that the items demonstrated a broad range of difficulty (from −0.79 to 1.96; M = 0.34; SD = 0.68)--indicating that the items are suitable for administration in samples across levels of expected spatial ability. In addition, item discrimination ranged from 0.91 to 3.21 (M = 1.76; SD = 0.53).

**Item Characteristic Curves from IRT analyses**
<img src="/img/2D/R2D_ItemProbability.png" alt="2DProb" width="500"/>

This figure shows the Item Characteristic Curves for the final set of 57 items (with latent ability level on the x axis and the probability of a correct response on the y axis). The difficulty level of an item is the latent ability level at which the probability of a correct response is .5. 


#### Construct Validity

The 2D rotation items also demonstrated the hypothesized relationships to various other cognitive abilities and personality traits. 

Among the cognitive abilities assessed, 2D rotation ability showed slightly larger relationships to other spatial and visual tasks (e.g., 3D rotation, matrix reasoning) than tasks that draw more on verbal skills (e.g., Verbal reasoning, Compound Remote Associates), though relationships were very similar across all ability measures.

<img src="/img/2D/R2D_AbilityCors.png" alt="2Dcorplot" width="500"/>

In line with past findings, relationships with personality traits (i.e., the Big Five traits and the 27 SAPA Personality Inventory traits) were very modest. 2D rotation ability showed the strongest relationships with emotional stability (+), intellect (+), anxiety (-), and irritability (-) from the SAPA Personality Inventory.

<img src="/img/2D/R2D_SPICors.png" alt="2Dcorplot" width="500"/>


<img src="/img/2D/R2D_BigFiveCors.png" alt="2Dcorplot" width="500"/>


As anticipated, job characteristics from the [O*NET content model](https://www.onetcenter.org/content.html) showing the strongest positive associations with 2D rotation ability were related to STEM knowledge and skills. Most job characteristics showing the strongest negative associations with 2D rotation ability were related to interpersonal skills and frequent interaction with others. Other characteristics that showed negative associations with 2D rotation ability were related to physical labor.


<img src="/img/2D/R2D_JobChars.png" alt="2DBigFive" width="600"/>

The relationship between 2D rotation ability and STEM-related tasks and activities was also supported by the associations between occupations and performance with the 2D rotation items. The occupations with the highest correlations were almost exclusively STEM-related. There was also strong overlap between the occupations that scored highest on 2D rotation ability and the occupations that scored the highest on 3D rotation ability. However, there were enough differences among the lists of majors and occupations scoring higherst on 2D and 3D rotation ability to support the discriminant validity of these measures.

**Highest scoring majors** (arranged in order of 2D rotation ability percentile)

<img src="/img/2D/R2D_HighestMajors.png" alt="2DBigFive" width="600"/>

**Highest scoring occupations** (arranged in order of 2D rotation ability percentile)

<img src="/img/2D/R2D_HighestOccupations.png" alt="2DBigFive" width="600"/>


### Conclusions and impact

This project established an openly available assessment with strong psychometric properties and support for validity that researchers can use to investigate spatial reasoning without relying on proprietary testing tools. You can find the items and information regarding psychometric properties and scoring under the Measures tab, and all code and data for this project on the github repository linked at the top of this page. 
