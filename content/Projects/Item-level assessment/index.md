---
title: "The case for using individual personality items"
summary: "Conventional scale development wisdom might not always be the best approach"
tags:
- Measurement
- Personality
- Culture
- R
external_link: ''
---


{{< github repo="kmather3/Item-level" showThumbnail=false >}}

This page discusses the work I completed for my dissertation. You can read it online <a href="https://www.proquest.com/openview/6d9553f03b9db3ef32f2c4bd8789f7ae/1?pq-origsite=gscholar&cbl=18750&diss=y" target="_blank" rel="noopener noreferrer">here</a> if you're interested in learning more!


# Background

The Big Five is one of the most widely used frameworks for measuring personality. It organizes personality into five broad traits: Extraversion, Agreeableness, Conscientiousness, Neuroticism, and Openness to Experience. One reason for its popularity is that it reaches a useful balance between comprehensiveness and parsimony: it captures many important components of personality without requiring researchers to measure an overwhelming number of variables.

However, the Big Five isn't necessarily the best framework for every research question. Some studies require more specific measures of personality, while others benefit from broader descriptions of individual differences. These different approaches occupy different levels of the personality trait hierarchy, which organizes traits according to how broadly or narrowly they are defined.

For example, the item "I start conversations" captures a specific behavior associated with Gregariousness, a facet of Extraversion, which falls under the broader meta trait of Plasticity. Each level offers a different perspective on personality, and the most useful level of analysis depends on the research question.

<img src="/img/ItemLevel/Trait_Hierarchy.png" alt="TraitHierarchy" width="700"/>

Despite the value of these different approaches, researchers often default to the Big Five, even when other models may be more appropriate. Cross-cultural research, for example, increasingly suggests that broader frameworks like the Big Two (Social Self-Regulation and Dynamism) generalize more consistently across cultural contexts. Yet the Big Five remains widely used, partly because of longstanding assumptions that its five traits represent universal, biologically grounded dimensions of personality.

Another reason for the dominance of the Big Five is the influence of Classical Test Theory, which shaped traditional approaches to psychological measurement. These approaches emphasize using multiple items to measure broad, underlying traits and treating the unique variance associated with individual items largely as measurement error. This perspective helped establish many of the measurement practices that are used today, and often leads researchers to measure personality traits using a latent variable modeling approach––which is very useful for differentiating trait-relevant variance from measurement error. 

<img src="/img/ItemLevel/LVM_Assumptions.png" alt="LCM" width="700"/>

However, advances in statistical methods and computing have made it possible to reconsider some of these assumptions. Research increasingly shows that individual personality items possess many of the characteristics we associate with personality traits, including stability over time, agreement across observers, and heritability (Mõttus et al., 2014, 2017, 2019). More importantly, specific personality characteristics can sometimes predict real-world outcomes even after accounting for the broader traits they are typically used to measure (Mõttus et al., 2022; Seeboth & Mõttus, 2018).

This raises an important question: **Are we overlooking meaningful personality information by treating the unique variance in individual items as measurement error?**

Rather than automatically assuming that personality items are interchangeable indicators of broader traits, we might consider whether their individual contributions are meaningful in their own right. For example, Extraversion could be understood not simply as an underlying trait reflected in a collection of interchangeable behaviors, but as a system of distinct, interconnected characteristics.

<img src="/img/ItemLevel/Modeling_Options.png" alt="MO" width="700"/>

One strategy for navigating model selection could be to focus on individual personality items as units of analysis first rather than aggregating them into broader scales from the beginning. This has already been proposed by some researchers focusing on test-validity, who recommend examining causal relationships between items, and item response processes before exploring evidence for the construct validity of a multi-item scale (e.g., test-retest reliability, internal consistency, relationships with other scales; Rhemtulla et al., 2021).

# The Case for Item-Level Assessment in Cross-Cultural Research

Cross-cultural personality research is one area where item-level assessment may be particularly valuable. Identifying personality frameworks that generalize across different cultural contexts has long been a challenge. Existing evidence suggests that broader models, such as the Big Two and Big Three, often demonstrate stronger cross-cultural generalizability than more specific frameworks like the Big Five.

**But what if we're interested in more specific personality differences?**

Consider emotional expressivity. A broad trait like Dynamism captures several characteristics, including assertiveness, sociability, adaptability, and emotional expressivity. Even if Dynamism can be measured consistently across cultures, it may not tell us much about the specific ways people express their emotions.

At the same time, using an existing emotional expressivity scale presents its own challenges. Cultural norms influence which emotions people feel comfortable expressing, how openly they communicate their feelings, and how they interact with others. As a result, a scale developed in one cultural context may not capture the same experiences in another.

An item-level approach offers another possibility: rather than relying on a single broad scale, researchers can examine individual questions that capture different aspects of emotional expressivity. These might include how freely people express emotions like sadness or anger, how much they reveal about themselves to others, and how naturally or comfortably they express their feelings.

By examining these specific characteristics individually, we may be able to identify meaningful cross-cultural similarities and differences that broader personality models would otherwise overlook.


# Comparing groups at the item-level: Beyond *t*-tests and *F*-tests

Another expanation for the lack of item-focused research could be the limited statistical options for addressing research questions at the item-level. Some options––such as Differential Item Functioning (DIF) analysis from the Item Response Theory framework––sound like they would be item-centered, but still mostly tell us about how items relate to their broader scales. Alternative options include comparing group means and variances throught the use of *t*-tests and *F*-tests, respectively. A key limitation of these tests is that they only detect differences in one aspect of the distribution, and it's possible that two groups show differences in their distributions that maybe one or both of these tests together wouldn't be able to detect. 

<img src="/img/ItemLevel/TF_tests.png" alt="TF" width="700"/>


## The Dowd Test Statistic

Instead it would be preferable to detect whether the entire distributions for two groups differ using a single test, which can be done by comparing their empirical cumulative distribution functions or "ECDF"s.

There are several existing tests for comparing group ECDFs. For this work, I used the Dowd Test Statistic (DTS), which combines the strengths of several of these previously developed tests: The Wasserstein Statistic and the Anderson-Darling Statistic. The DTS test takes the variance weighted integral of the area between the ECDFs––which improves upon the statistical power of previous tests by assigning more weight to stable areas of the distribution with lower variance than those with higher variance that are more likely to be affected by sampling variability. 

The formula for the statistic is:

<img src="/img/ItemLevel/DTS.png" alt="DTS" width="700"/>

To give a quick example, let's say we compare the Philippines and the United States on the item *"I am quiet around strangers"* with response options from 1 (*strongly disagree*) to 6 (*strongly agree*)...

- If D(3) = .9, this means the model is fairly confident that the response of 3, or “slightly disagree” came from the Philippines
- If D(3) is .1, the model is confident that the response of 3 came from the United States
- If D(3) is around .5, the model is unsure which sample the response came from

When the classifier is more confident about which sample each response option likely came from, the denominator is smaller, which leads to a larger DTS effect size. When the classifier is more uncertain (near 0.5 across response options), the denominator is larger, which leads to a smaller DTS effect size.


# Applying DTS

## Comparisons across SAPA Personality Inventory (SPI) Items

In this work, I used a dataset from the SAPA project (*N* = 25,598) to compare responding in a set of culturally diverse nations on each of the 135 SAPA Personality Inventory items using the DTS test. Nations included in analyses were selected based on global representation and whether they met a minimum threshold of 100 pairwise administrations per item pair (as the SAPA project uses a planned missingness design). This left 12 nations: the United States, Canada, the United Kingdom, Australia, Sweden, India, Germany, the Netherlands, China, Singapore, the Philippines, and Norway. 

This results in a total of 10,530 DTS tests across combinations of the 135 items and 78 nation pairs (of the 12 nations). Here are two example DTS test results for an item with a fairly large significant effect size ("I am full of ideas") and an item with a non-significant effect ("I do not like art"). Response options from 1-6 are shown on the x-axis of each figure, and the percentile of responses at or below a given response option is shown on the y-axis of each figure.

<img src="/img/ItemLevel/DTS_SPI_Examples.png" alt="SPI" width="1000"/>


Across all DTS tests, 36% were statistically significant. 

**Items with the fewest differences in responding** across nations (with broader SPI construct/Big Five construct in parentheses) were: 

- “Believe that others have good intentions” (SPI Trust/Big Five Agreeableness)
- “Am not bothered by disorder” (SPI Order/Big Five Conscientiousness)
- “Adjust easily” (SPI Adaptability/Big Five Openness)
- “Am open about my feelings” (SPI Emotional expressiveness/Big Five Neuroticism)
- “Let things proceed at their own pace” (SPI Easygoingness/Big Five Conscientiousness)
- “Tell the truth” (SPI Honesty/Big Five Agreeableness)
- “Jump into things without thinking” (SPI Impulsivity/Big Five Conscientiousness)

**Items with the most differences in responding** across nations (with broader SPI construct/Big Five construct in parentheses) were: 

- “Like to stand during the national anthem” (SPI Conservatism/Big Five Openness)
- “Learn things slowly” (SPI Intellect/Big Five Openness)
- “See myself as an average person” (SPI Conformity/Big Five Agreeableness)
- “Believe in one true religion” (SPI Conservatism/Big Five Openness)
- “Lack the talent for influencing people” (SPI Charisma/Big Five Extraversion)
- “Fear for the worst” (SPI Anxiety/Big Five Neuroticism)
- “Don’t consider myself religious” (SPI Conservatism/Big Five Openness)

While there are a few trends here (such as the higher number of conservatism items with many cross-national differences), it is notable that there were items from a variety of SPI and Big Five scales represented on both of these lists. It suggests that even more precise, fine grained constructs such as the SPI traits might sometimes obscure cultural differences that exist at the item level. 

**Effect Sizes for all significant DTS tests across item x nation pair combinations**

To better understand patterns in repsonding across the SPI items and nation pairs, it can be useful to look at them visually. Effect sizes for all statistically significant (*p* < .05) DTS tests are shown in the figure below. Nation pairs are represented by their ISO 3 codes and on the x axis (e.g., The "AUS_CAN" label indicates tests between Australia and Canada), and SPI items are shown on the y axis (grouped and color-coded by SPI trait). In order on the y axis, these SPI constructs include: irritability, industry, humor, authoritarianism, impulsivity, art appreciation, perfectionism, attention seeking, well being, adaptability, charisma, compassion, honesty, trust, emotional stability, easygoingness, anxiety, sensation seeking, conservatism, intellect, emotional expressiveness, sociability, self-control, conformity, order, introspection, and creativity.

<img src="/img/ItemLevel/SPI_Items.png" alt="SPI" width="3000"/>

There are a few items (and broader constructs) where the larger effect sizes appear to cluster, such as those included among items with the highest number of differences ("I tend to vote for conservative political candidates", "I like to stand for the national anthem", "I believe in one true religion", and "I don't consider myself religious"). Some of these findings are likely driven by the varied relevance of the item across nations (e.g., regarding standing for the national anthem), and others reflect known differences in religiosity across cultures. 

A few other items that stand out in this figure include:

- "I am full of ideas"
- "I think of others first"
- "I think quickly"



## Comparisons across 2,623 International Personality Item Project Items

Using nearly 1.03 million participants from the Synthetic Aperture Personality Assessment (SAPA) Project, we compared the ECDFs for 2,623 personality items from the International Personality Item Project (IPIP; https://ipip.ori.org/) across 13 countries. This resulted in a total of 204,594 DTS tests across all item x nation pair combinations.

**Overall, 56% of DTS tests were statistically significant**
 
 The following image shows the distribution of the proportion of significant tests per item across the 204,594 DTS comparisons. This distribution appears fairly normally distributed, though some items showed a notably high proportion of significant DTS tests. 

 <img src="/img/ItemLevel/Proportion_Significant.png" alt="ProportionSignificant" width="1000"/>

**For the following 37 of the 2,623 IPIP items, 100% of cross-national comparisons were statistically significant:**

- Am able to come up with new and different ideas
- Am full of ideas.
- Am not bothered by disorder.
- Am skilled in handling social situations.
- Believe in one true religion.
- Believe that people are basically moral.
- Dislike myself.
- Don't consider myself religious.
- Feel comfortable with myself.
- Get angry easily.
- Have a natural talent for influencing people.
- Have a slow pace to my life.
- Jump into things without thinking.
- Let things proceed at their own pace.
- Like order.
- Like to be thought of as a normal kind of person.
- Like to stand during the national anthem.
- Like to take it easy.
- Love dangerous situations.
- Never spend more than I can afford.
- Never splurge.
- Often forget to put things back in their proper place.
- Often make decisions on the spur of the moment.
- Panic easily.
- Prefer variety to routine.
- Put on a show to impress people.
- Rarely get irritated.
- Rarely overindulge.
- Seek danger.
- Start tasks right away.
- Take risks.
- Tend to vote for conservative political candidates.
- Think quickly.
- Think that my moods don't change more than most people's do.
- Trust people to mainly tell the truth.
- Trust what people say.
- Use others for my own ends.

Many items were related to impulsivity or sensation-seeking (items like “I seek danger” or “I take risks”). A few were related to influencing others in various ways or attention-seeking, like “I have a natural talent for influencing people”, or “I put on a show to impress people”. Some items were conscientiousness related, like “I am not bothered by disorder” or “I start tasks right away”. Others, as expected, were openness-related items (so items like “I prefer variety to routine”, “I believe in one true religion”, “Like to be thought of as a normal kind of person”)

**When looking at items that had more than 90% significant comparisons across nation pairs, there were many additional openness items:**

- Spend time reflecting on things
- Love to reflect on things
- Tend to vote for liberal political candidates
- Seek adventure
- Learn things slowly
- Enjoy examining myself and my life
- Don’t like the idea of change
- Do not like poetry
- Believe in the importance of art
- Am quick to understand things
- Can handle a lot of information
- Try to understand myself
- Am quick to understand things
- Can handle a lot of information
- Try to understand myself
- Love to think up new ways of doing things
- Have read the great literary classics
- Have a vivid imagination
- Catch on to things quickly
- Am an original thinker
- Do not enjoy going to art museums
- Would hate to be considered odd or strange

These findings align with the field's understanding of Openness to Experience as a diffcult trait to measure across cultures, as it appears to lack relevance in some non-Western contexts (cite). Previous work has suggested that Openness lacks the universality of other broad constructs, like Agreeableness and Extraversion. 

**However, most work exploring the generalizability of personality models has focused solely on broad constructs, and findings at the item-level tell a different story**. Openness-related items were not only overrepresented among those with the *most* cross-national differences in responding, but also in the set of items with the *fewest* cross-national differences in responding. 

**For example, these are the IPIP items that showed the fewest differences in responding across nations (less than 20%), with Openness items shown in bold:**

- **Believe that there are many sides to most issues**
- **Want to understand things**
- **Enjoy the beauty of nature**
- Know how to fly a helicopter
- Have little patience for slackers
- **Am committed to principles of justice and equality**
- Am able to see how other peoples’ emotions can affect their behaviors
- Don’t have a soft side
- Have lived in all 50 states in the U.S.A.
- Love to chat
- Look at the facts
- Think a lot before complaining in a restaurant if my meal is not well-prepared
- **Want to know the reasons why**


**Additional Openness items for which fewer than 30% of cross-national comparisons were significant included...**

- Enjoy games of strategy
- Try to identify the reasons for my actions
- Go my own way
- Love to learn new things
- Don’t like to travel
- Get excited when I learn new things
- Like to visit new places
- Love to read challenging material
- Love to travel to places that I have never been before
- Understand things quickly
- Want to increase my knowledge
- Come up with alternatives
- Am good at thinking of solutions that no one else thinks of
- Prefer to analyze problems rather than just describe them
- See beauty in things others might not notice
- Have new ideas for improving things
- Look at myself through others’ eyes
- Love to hear about other countries and cultures
- Tend to think about something for hours
- Am a true life-long learner
- Can see different points of view
- Can sense how things will turn out
- Care about justice
- Notice contradictions
- Try to do difficult things


### Does Openness to Experience have a "universal core"?

Findings regarding these Openness items highlight the value of evaluating differences at more granular levels––particularly the item level. On one hand, they’re consistent with the many findings suggesting that Openness to Experience lacks generalizability across cultures. However, they also build on more recent work suggesting that Openness might have a more “universal core” that generalizes well across cultures and focuses more on how reflective and knowledgeable people are rather than how much they stand out from others and stray from norms and traditions. Thalmayer and Schwaba [(2025)](https://doi.org/10.1177/10888683251377227) propose the following differences in the structure of Openness for Western cultures and Majority-world cultures:


 <img src="/img/ItemLevel/Openness_Structure.png" alt="OpennessStructure" width="500"/>


When looking for themes among the openness items showing the most and fewest differences in responding across cultural contexts, the present work supports this claim:

**Openness items with the most differences** in responding across nations included those related to...

- **Idea generation without a specific purpose:**
    *"I am able to come up with new and different ideas"*, *"I have a vivid imagination"*, *"I am full of ideas"*, *"I love to think up new ways of doing things"*
- **"Quickness":**
    *"I think quickly"*, *"I learn things slowly"*, *"I am quick to understand things"*, *"I catch on to things quickly"*
- **Standing out from others:**
    *"I like to be thought of as a normal kind of person"*, *"I would hate to be considered odd or strange"*, *"I am an original thinker"*
- **Art, politics, and religion:** 
   *"I believe in the importance of art"*, *"I do not enjoy going to art museums"*, *"I believe in one true religion"*, *"I tend to vote for liberal political candidates"*


**Openness items with the fewest differences** in responding across nations included those related to...

- **Coming up with solutions or strategies:**
    *"I have new ideas for improving things"*, *"I come up with alternatives"*, *"I am good at thinking of solutions that no one else thinks of"*, *"I enjoy games of strategy"*
- **Enjoyment of learning, challenging oneself:**
    *"I am a true life-long learner"*, *"I love to learn new things"*, *"I love to read challenging material"*, *"I try to do difficult things"*, *"I want to increase my knowledge"*, *"I want to understand things"*
- **Perspective-taking:**
    *"I can see different points of view"*, *"I look at myself through others’ eyes"*, *"I believe there are many sides to most issues"*
- **Cultural exploration:**
    *"I love to hear about other countries and cultures"*, *"I like to visit new places"*, *"I don't like to travel"*


While these items are grouped into broader themes for ease of interpretation, these results likely wouldn't have been found at the facet level as an alternative to the item level. There are items on each of these lists that are highly similar, and that researchers (myself included) might include in the same scale based on the assumption that they are assessing the same individual difference. For example, it would be very reasonable to inlcude the items "I love to think up new ways of doing things" and "I have new ideas for improving things" in the same scale, and maybe even view them as redundant and ultimately remove one of them. However, these items differ greatly in whether they reveal cultural differences. 

This could be due to the phrasing of the items. But another possibility is that it reveals something about the value that different cultures place on novelty and idea generation as an end itself (not only in the service of some kind of personal or societal improvement). In some places, this might be seen as a generally positive thing--something associated with creative greatness and innovation. In others, it might be seen more as wasting time. 


# Conclusions and impact

The work demonstrates that item-level constructs offer several advantages across areas of personality research. Focusing on the item-level is useful for both broader scale development purposes and for detecting differences in more narrowly defined individual differences, which would otherwise be missed when aggreating item responses into broader scale scores. This is especially important to consider when comparing personality across cultures. 

This work also demonstrated the use of a more item-centric statistical approach for approaching research questions at the item level: the DTS test. One explanation for the relative lack of item-focused research could be the strong norms in the field regarding personality measurement and the statistical approaches that are considered more rigorous––which center multi-item scales that measure broadly defined personality traits. Findings from the present work suggest that it would be beneficial to identify or develop additional statistical approaches for exploring research questions at the item-level.

While broad trait models like the Big Five will remain highly useful in personality research, many research questions would benefit from a stronger focus on the item-level or on other levels of the trait hierarchy. Personality research would likely benefit the most from viewing these levels of the trait hierarchy as complementary approaches, and from reporting findings at multiple levels. 


**Posters and talks on item-level analysis:**
* [Poster presented at the Association for Research in Personality Conference--2023](/img/ItemLevel/Mather_Poster_ARP2023_July17.pdf)

* [Presentation slides from my dissertation defense--2026](/img/ItemLevel/Mather_Dissertation_Defense.pdf)
