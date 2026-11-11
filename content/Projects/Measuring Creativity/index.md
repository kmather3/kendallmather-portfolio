---
title: "Measuring Verbal Creativity"
summary: "A project designed to develop and validate a measure of verbal creativity using new and existing Compound Remote Association (CRA) Task items"
tags:
- Creativity
- Statistical learning
- Factor analysis
- Item response theory
- R
external_link: ''
---

{{< github repo="kmather3/Compound-Remote-Associates-Task" showThumbnail=false >}}

# Project overview

**How can researchers measure creative problem-solving reliably across large populations?**

Creativity research often relies on open-ended tasks that require participants to generate their own answers. Although useful, these tasks can be difficult to score consistently and challenging to administer at scale. I developed and validated a multiple-choice version of the Compound Remote Associates (CRA) task, which measures the ability to connect seemingly unrelated concepts. 

For example, a participant might be asked to find a word that connects three different cue words such as "safety", "cushion", and "point":

<img src="/img/CRA/CRAResponseModes.png" alt="CRAItem" width="500"/>
(answer: "pin", or "p" in the multiple-choice version).

## Method 

Using multiple large datasets, we evaluated the measure's reliability, underlying structure, and relationships with other individual differences. 

**Study 1: Exploring factor structure, internal consistency, and construct validity**

* Dataset: SAPA project data (*N* = 1,323,480 participants)
* Goals: Explore the internal consistency and factor structure of the CRA items (i.e., is the measure unidimensional?), and examine relationships with other constructs. 
* Analyses used: exploratory factor analysis, item response theory (IRT) modeling, pearson correlations, and the BISCUIT statistical learning technique.

**Study 2: Comparing the multiple-choice and short-answer response modes**

* Dataset: Undergraduate sample (*N* = 685 participants)
* Goals: Compare the multiple-choice and short-answer response modes, establish further evidence for construct validity based on GPA and standardized test scores.
* Analyses used: Logistic regression, pearson correlations

**Study 3: Examining test-retest reliability**

* Dataset: Prolific sample (*N* = 357 participants)
* Goals: Examine the test-retest reliability of the items over a two week period, establish further evidence for construct validity using the Cognitive Reflection Task. 
* Analyses used: Pearson correlations



## Results

### Psychometric properties

**Overall, psychometric findings indicated that one underlying ability (creative cognition) explains responding across items, that the items show strong reliability, and that the complete item bank includes CRA items that are suitable for those across levels of creative thinking.**

Findings from the SAPA project sample (*N* = 1,323,480) revealed that the multiple-choice CRA items demonstrated strong psychometric properties including high internal consistency (α = .97, ω total = .97) and unidimensionality based on exploratory factor analysis findings. In addition, Item Response Theory analysis (using a 2 parameter logistic model) suggested that the multiple-choice CRA items are strong in their ability to distinguish participants at one ability level from another (i.e., they demonstrate strong item discrimination), and that the set of items collectively cover a wide range of item difficulty (i.e., there are items in the pool that are suitable for administration to participants from lower levels of ability to those with high levels of associative ability).

**Item difficulty and discrimination curves:**

<img src="/img/CRA/CRA_IRT_Findings.png" alt="CRAIRT" width="800"/>

**Test-retest reliability:**

In addition, findings from the prolific sample (*N* = 357 participants) found good stability for the items over a time period of two weeks (test–retest correlation = .74).

<img src="/img/CRA/CRAretestCors.png" alt="CRAItem" width="400"/>

### Construct validity 

Findings across studies also provided evidence that the multiple-choice CRA items measure the construct they were developed to assess––creative thinking. 

**Comparison of new item set and multiple-choice response mode with existing remote associates task and open ended response mode:**

First, a mixed effects logistic regression model (used in study 2, with *N* = 685 undergraduates) that participants were more likely to give a 
correct response to problems using the multiple-choice response mode (OR = 1.89, 95% CI [1.78, 2.01]), and that the older set of items (from the Remote Associates Test or "RAT") were easier to solve than the newer set of items (OR = 0.41, 95% CI [0.39, 0.44]). 

An interaction term between response mode and problem set was then added to the model, which was also found to be significant (OR = 1.75, 95% CI [1.55, 1.97]). The interaction, depicted in the figure below, shows that the multiple-choice response mode had a stronger effect on the difficulty of the newer "CRA" items (i.e., making them easier to solve) than the difficulty of the older "CRAT" items. When administered using the multiple-choice response mode, the difficulty (on average) of the CRA items appears similar to the difficulty on average of the open CRAT items (i.e., the item set and mode of administration that has been used in previous work).

<img src="/img/CRA/CRAResponseModeEffects.png" alt="CRAResponseModes" width="700"/>

Performance on the CRA items across all item sets (newer, older), and response modes (multiple-choice, open-ended) were also moderately correlated with measures of academic achievement such as ACT scores and GPA.

<img src="/img/CRA/CRA_GPA_ACT.png" alt="CRAItem" width="800"/>


**Correlations for the newly developed items using a multiple-choice format with other constructs:**

When examining relationships with other individual differences, findings from the prolific sample indicated that CRA performance was positively correlated with the [Cognitive Reflection Test](https://sjdm.org/dmidi/Cognitive_Reflection_Test.html) (*r* = .44), which assesses individuals' ability to suppress an intuitive but incorrect answer in favor of a correct answer that requires more reflection to arrive at. 

Relationships with the [Four Factor Imagination Scale](https://pubmed.ncbi.nlm.nih.gov/31302774/) indicated that CRA performance was negatively related to how directed and purposeful one's imagination is (*r* = -.21)––which aligns with previous findings that more creative individuals tend toward uninhibited “mind-wandering” more than intentional brainstorming. However, we did not find the expected positive relationships for CRA performance with other dimensions of imagination, such as how frequently participants engage in imaginative thinking (non-significant correlation), and the complexity of their imagination (how detailed and intricate it is; *r* = -.12).

<img src="/img/CRA/CRA_Imagine_CRT.png" alt="CRAItem" width="800"/>

Findings from the SAPA project sample revealed that the new, multiple-choice CRA items showed the strongest correlations with various cognitive abilities (e.g., propositional reasoning, verbal reasoning). Consistent with past findings, they also showed positive relationships with personality traits such as Openness to Experience and Intellect, and negative relationships with traits like anxiety and neuroticism. 

However, performance on the CRA items showed unexpectly strong positive relationships with prosocial traits such as Agreeableness and Honesty––even after controlling for cognitive ability. These results were surprising given past findings which most often suggest that creativity shows no relationship with these traits, or sometimes even that creative people have a tendency toward interpersonal antagonism and dishonesty (e.g., Feist, 1998). However, some findings deviate from this pattern and are more in line with the present findings. Because few studies have examined how CRA items relate to temperament, it is unclear whether the relationship creativity shows with the traits of honesty and agreeableness varies across measures (e.g., CRA items, measures of divergent thinking). The relationship between creativity and agreeableness could also vary depending on how creativity is conceptually defined. 


<img src="/img/CRA/CRAvalidityCors.png" alt="CRAItem" width="500"/>


Findings from the SAPA project sample also suggested that those who performed the highest on the CRA items chose more creative majors and occupations––particularly those demanding strong verbal skills (relative to math or spatial skills).


<img src="/img/CRA/CRA_Occupations_Majors.png" alt="CRAItem" width="900"/>


Using the BISCUIT statistical learning technique, we also examined the relationships for CRA performance with the 200+ job characteristics described in the [O*NET content model](https://www.onetcenter.org/content.html)––which capture the various abilities, skills, work styles, knowledge bases, and tasks demanded by a given role. 

Job characteristics most strongly associated with CRA performance are shown in descending order in the table below, along with information regarding how many times the job characteristic appeared in the optimal model (*N*), mean correlation (mean *r*), and the standard devation of correlations across bootstrap iterations.


These findings, which revealed job characteristics such as writing and reading comprehension as being most strongly related to CRA performance, further emphasized the importance of verbal skills for solving these problems. Job characteristics relating to creativity—such as originality, thinking creatively, and innovation—were also, to a lesser extent, among the top characteristics.

<img src="/img/CRA/CRA_Job_Chars.png" alt="CRAItem" width="1000"/>


## Conclusions and impact

This work produced a scalable, validated tool for studying creative problem-solving. By making the task easier to administer and analyze in large surveys, the project helps researchers investigate creativity across diverse populations and examine how associative ability relates to cognitive skills, personality, and occupational outcomes.



* [Presentation slides from the European Association of Personality Psychology Conference--2022](/img/CRA/CRA_Presentation.pdf)

