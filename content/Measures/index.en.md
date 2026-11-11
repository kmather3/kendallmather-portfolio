---
title: "Personality Assessment Materials"
description: "Personality assessment materials."
showDate: false
showTableOfContents: true
showHero: true
heroStyle: liquid-ether-thumb
showAuthor: false
showPagination: false
---


All items and information regarding the personality assessment materials I've developed can be found on this page!


### Compound Remote Associates (CRA) Items

Download all CRA items (including newly developed items and items from the Remote Associates Test developed by [Mednick & Halpern (1962)](https://psycnet.apa.org/doiLanding?doi=10.1037%2Ft11859-000)) as a csv file [here](/img/CRA/CRA_Items.csv) or as an xlsx file [here](/img/CRA/CRA_Items.xlsx).

**Administration Guidelines:**

CRA items assess the ability to find a connection among seeminly unrelated words. They offer a strong method for measuring creative thinking, and can be administered using either an open-ended or multiple-choice response format (shown below). 

<img src="/img/CRA/CRAResponseModes.png" alt="CRAItem" width="500"/>
(answer: "pin", or "p").

Together, the complete set of 96 items included in the file cover a wide range of difficulty, making them suitable for administration in samples across levels of creativity. To help those interested in administering CRA items, information on the difficulty of each item is included in the following files (the "difficulty" column refers to the IRT item difficulty parameter and the "mean" column refers to the proportion of participants in the SAPA project sample who responded correctly).

**Scoring:**

I recommend selecting a subset of CRA items that cover the full range of item difficulty (i.e., some easier items, some more difficult items, but mostly items somewhere in the middle range). Item difficulty is reflected in both the difficulty IRT parameter and the proportion of correct responses. While sum scoring the CRA items is an option, IRT scoring will provide more accurate scores based on known item difficulty levels. 


**Column included in the file:**

- **SAPA Item label:** The label given to the item in the SAPA project dataset. This could be useful for those looking for more information on a particular item  in the supplemental file, dataset, or results (e.g., factor loading).
- **Stimuli 1:** First stimuli word in the CRA item (e.g., "safety")
- **Stimuli 2:** Second stimuli word in the CRA item (e.g., "cushion")
- **Stimuli 3:** Third stimuli word in the CRA item (e.g., "point")
- **Solution:** The word that connects the three words (e.g., "pin")
- **discrimination:** IRT discrimination parameter (i.e., how well does this item distinguish those at one ability level from another?)
- **difficulty:** IRT difficulty parameter (i.e., at what ability level do participants have a 50% chance of answering correctly? Higher values indicate that the item is harder to solve)
- **mean:** The proportion of participants who responded correctly from the SAPA project sample used to validate the items
- **se:** Standard error
- **n:** Number of responses for this item in the SAPA dataset


**Reference:**

Mather, K. A., Weston, S. J., & Condon, D. M. (2024). Scaling a common assessment of associative ability: Development and validation of a multiple-choice compound remote associates task. *Behavior Research Methods*, 56(7), 1-29. https://doi.org/10.3758/s13428-024-02422-3


### Two-dimensional Rotation Items

Download a zip file with all 2D rotation items [here](/img/2D/R2Dfigures.zip), the answer key here:[(as csv)](/img/2D/R2D_AnswerKey.csv)/[(as xlsx)](/img/2D/R2D_AnswerKey.xlsx), and information on the psychometric properties for the validated set of items here: [(as csv)](/img/2D/R2D_Items_Final.csv)/[(as xlsx)](/img/2D/R2D_Items_Final.xlsx).

**Administration Guidelines:**

Each of these spatial ability items presents a large square containing 16 small shapes in a 4 × 4 array. To the right of this square, the same square is shown rotated 0–3 times by 90 degrees, with one of the corner pieces missing from the frame. Participants should select the answer that completes the figure from a set of multiple-choice options. Six of the eight multiple-choice options show a puzzle piece with 1 of the 16 small shapes, and the remaining two allow participants to indicate that they do not know the answer or that the correct answer is not included among the answer options. 

Each item requires either rotation of the large square, rotation of the answer option, rotation of both the large square and answer option, or rotation of neither (i.e., simple pattern matching). The example item below requires rotation of both the larger square and the answer option to arrive at the correct answer ("C").

<img src="/img/2D/R2D_Example_Item.png" alt="R2DItem" width="500"/>

**Scoring:**

I recommend selecting a subset of these 2D rotation items that cover the full range of item difficulty (i.e., some easier items, some more difficult items, but mostly items somewhere in the middle range). Item difficulty is reflected in both the difficulty IRT parameter and the proportion of correct responses. While sum scoring the 2D rotation scale is an option, IRT scoring will provide more accurate scores based on known item difficulty levels. 

**Columns included in file with information on validated set of items:**

- **item:** The label given to the item in the SAPA project dataset (which correspond to the item numbers for the items included in the zip file)
- **mean:** The proportion of participants who responded correctly from the SAPA project sample used to validate the items
- **sd:** Standard deviation
- **N:** Number of responses for this item in the SAPA dataset
- **discrimination:** IRT discrimination parameter (i.e., how well does this item distinguish those at one ability level from another?)
- **difficulty:** IRT difficulty parameter (i.e., at what ability level do participants have a 50% chance of answering correctly? Higher values indicate that the item is harder to solve)


**Reference:**

Mather, K. A., & Condon, D. M. (2023). Development of a Public-Domain Measure of Two-Dimensional Rotation Ability and Preliminary Evidence for Discriminant Validity among Occupations. Journal of Intelligence, 11(10), 191. https://doi.org/10.3390/jintelligence11100191



### Cross-cultural Big Two Inventory (CCBTI)

The CCBTI measures the "Big Two" traits of Communion/Social Self-regulation (the internalization versus resistance to the normative code's of one's society--with components of warmth, morality, respect, and industriousness), and Dynamism (which reflects approach versus avoidant tendencies, with components of competence, confidence, fearlessness, positive mood, and sociability).

Download all CCBTI items as a csv file [here](/img/BigTwo/CCBTI_Items.csv) or as an xlsx file [here](/img/BigTwo/CCBTI_Items.xlsx). 

**Administration Guidelines:**

This file includes all CCBTI items, the Big Two subscale they measure, and information regarding their factor loadings when using raw and ipsatized data. Note that the file contains the complete pool of 55 items for transparency purposes, but only 45 items were retained in the final validated scale. You can filter spreadsheet to see only these 45 items using the "Final_Scale" column and removing rows with the value "No". 

All items begin with the stem "I tend to be..." (e.g., *I tend to be shy*, *I tend to be energetic*). The response format used for the validated measure was a 6-point scale with options: 

(1) strongly inaccurate
(2) somewhat inaccurate
(3) slightly inaccurate
(4) slightly accurate
(5) somewhat accurate
(6) strongly accurate

**Columns included in the file:**

This file is a factor loading table for the CCBTI items arranged by ipsatized data factor loadings (i.e., you'll see all items with primary loadings onto the "Agency" factor first, arranged in descending order of factor loading, and then all items with primary loadings on to the "Communion" factor, arranged in descending order of factor loading). Here is the information included in the file:

- **item:** Item label in the SAPA dataset
- **content:** Item phrasing
- **Reverse_Score:** Whether to reverse score the item (if so, the value will be "Yes")
- **subscale:** Big Two subscale (Agency or Communion)
- **Final_Scale:** Whether or not the item was included in the final scale
- **Primary Ips:** Primary construct loading when using ipsatized data (Agency or Communion)
- **Agency Ips:** Loading onto the Agency factor for ipsatized data
- **Communion Ips:** Loading onto the Communion factor for ipsatized data
- **Loading ratio Ips:** Primary:Secondary factor loading ratio for ipsatized data
- **Primary raw:** Primary construct loading when using raw data (Agency or Communion)
- **Agency raw:** Loading onto the Agency factor for raw data
- **Communion raw:** Loading onto the Communion factor for raw data
- **Loading ratio:** Primary:Secondary factor loading ratio for raw data

**Scoring:**

There are a few options for generating CCBTI scale scores for Agency and Communion. We used mean scoring (taking the mean response of items answered), but sum scoring can also be used is missing data is not an issue. Remember to filter out items that were not included in the final scale (i.e., those with a value of "No" under the "Final_Scale" column) and to reverse score items with the value "Yes" in the "Reverse_Score" column.

**Reference:**

Thalmayer, A. G., Mather, K. A., Saucier, G., Naudé, L., Florence, M., Adonis, T. A., ... & Condon, D. M. (2025). The cross-cultural big two: A culturally decentered theoretical and measurement model for personality traits. *Journal of Personality and Social Psychology*, 128(5), 1181. https://doi.org/10.1037/pspp0000528 


