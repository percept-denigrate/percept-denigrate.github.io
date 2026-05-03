Education has been shown to raise cognitive ability.[^1][^2] But are those gains on [[General intelligence]], or does education only increase specific cognitive abilities?

# Initial study

Ritchie et al. (2015)[^3] is the study aiming to answer this question.

> Here, we report an analysis of a longitudinal cohort (the Lothian Birth Cohort 1936) of over 1,000 individuals across a follow-up period of almost 60 years with intelligence measurements from both early and late in life. We investigated whether education is associated with relative improvements in the _g_ factor extracted from a battery of 10 diverse cognitive tests (domain-general effects of education on cognitive development), or with improvements on only some of those tests (domain-specific effects of education).

The study tests three models:

- A: Education acts only on *g*
- B: Education acts both on *g* and on specific skills
- C: Education acts only on specific skills

The models also use a measure of [[IQ]] taken at age 11 to add a confounder.

![[ritchie_models.gif]]

Parameters for each models were dtermined to maximize model fit. Model C ends up fitting better than model A ($\Delta AIC=19.08$) and model B ($\Delta AIC=9.90$).

![[ritchie_model_c.gif]]

The study concludes that education doesn't raise general intelligence.

# Critique

Sasha Gusev outlined in a [post](https://theinfinitesimal.substack.com/p/does-education-increase-intelligence) multiple interesting points.

- Model B only allows for education to act on some specific skills. If it acted on all of them, the model would be unidentifiable. Thus the hypothesis that education acts on all subtests can't be tested.
- The study doesn't test models where early IQ have a direct effect on specific skills.
- Many decisions were made without a provided explanation: the number of specific skills, the use of a single-factor model where a multiple-factor model had better model fit, the paths from education and specific skilles removed in model C. This opens up the possibility of overfitting and *p*-hacking.

[Ritchie agrees with the criticisms.](https://www.sciencefictions.org/p/science-fictions-links-for-july-2024)

# Reanalysis

Gusev allowed for paths from early IQ to specific skills, and found a model that fits way better ($\Delta AIC \geq 50$ than any other model) in which education only acted on $g$.

![[ritchie_best.png]]

This is essentially the exact opposite of Ritchie et al. (2015)'s conclusion.

[^1]: [Ritchie et al. (2013), *Education is associated with higher later life IQ scores, but not with faster cognitive processing speed*](https://pubmed.ncbi.nlm.nih.gov/23276218/)

[^2]: [Ritchie et al. (2018), *How Much Does Education Improve Intelligence? A Meta-Analysis*](https://journals.sagepub.com/doi/10.1177/0956797618774253)

[^3]: [Ritchie et al. (2015), *Is Education Associated With Improvements in General Cognitive Ability, or in Specific Skills?*](https://psycnet.apa.org/fulltext/2015-11424-001.html)
