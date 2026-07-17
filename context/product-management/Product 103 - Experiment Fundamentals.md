# Product 103: Experiment Fundamentals

**Purpose:**

The [Growth
Ideas](https://microsoft.sharepoint.com/teams/AIMomentWorkingGroup/Shared%20Documents/General/AI%20Product%20Readiness_Excellence/Playbooks/Product%20102%20-%20Growth%20Ideas.docx)
helped define a set of prioritized investments with estimated impact.
This playbook will turn those ideas into a set of well formed
experiments. Any software change that impacts a customer journey should
be A/B tested by tracking metrics that product teams can impact directly
such as events triggered by user actions in the product.

**Audience:** GPMs and Product Leads

**Add'l resources:**

The following resources do a great job outlining the basics of
experimentation like observations, hypotheses, success criteria, etc.

- [EXP Partner
  site](https://microsoft.sharepoint.com/teams/expshared?xsdata=MDV8MDF8fDUzOWRhYzg4YWM1YjQ2NmVmYThmMDhkYjI5ODQ0YzJhfDcyZjk4OGJmODZmMTQxYWY5MWFiMmQ3Y2QwMTFkYjQ3fDB8MHw2MzgxNDk0MjAzOTMzNjQxMTF8VW5rbm93bnxWR1ZoYlhOVFpXTjFjbWwwZVZObGNuWnBZMlY4ZXlKV0lqb2lNQzR3TGpBd01EQWlMQ0pRSWpvaVYybHVNeklpTENKQlRpSTZJazkwYUdWeUlpd2lWMVFpT2pFeGZRPT18MXxNVFkzT1RNME5USXpPVEF4T1RzeE5qYzVNelExTWpNNU1ERTVPekU1T20xbFpYUnBibWRmVDFSUmVWcHFRVFJPVkVsMFRWUnNiVmxwTURCT1YwcG9URmRKTVZscVVYUk5iVWw2V2xkV2FGbHFZekpPYlVreVFIUm9jbVZoWkM1Mk1nPT18ZjViYTNlZGQ1OTQzNGQyYmZhOGYwOGRiMjk4NDRjMmF8Y2Y3NTM3N2I4MGJmNDk1YmIxMjM1ZWU2YzY4ZWRlZTU%3D&sdata=endwNnJFS0F5aElIYVZtUm02cm9aWHNoMkttcU9wNDVURXI4N2xnVVpqcz0%3D&ovuser=72f988bf-86f1-41af-91ab-2d7cd011db47%2Cmalicata%40microsoft.com&OR=Teams-HL&CT=1679345243918&clickparams=eyJBcHBOYW1lIjoiVGVhbXMtRGVza3RvcCIsIkFwcFZlcnNpb24iOiI0OS8yMzAzMTIwMTcwMCIsIkhhc0ZlZGVyYXRlZFVzZXIiOmZhbHNlfQ%3D%3D)
  for learning all about EXP and Experimentation.

- [Intro to
  Experimentation](https://microsoft.sharepoint.com/:p:/r/teams/expshared/Shared%20Documents/Intro%20To%20Exp%20Class/Section%201%20-%20Introduction%20and%20Motivation/1%20-%20Online%20-%20Julie%20-%20Feb2023.pptx?d=wcaf1c9b8db4e43f4b74b9619f39f5181&csf=1&web=1&e=mxddI2)
  class and greater [documents
  folder](https://microsoft.sharepoint.com/teams/expshared/Shared%20Documents/Forms/AllItems.aspx?id=%2Fteams%2Fexpshared%2FShared%20Documents%2FIntro%20To%20Exp%20Class)

- [EXP \| what is A/B
  experimentation](https://microsoft.sharepoint.com/:p:/t/expshared/ESDV47_HvbVAvoY5DHrPLVkBuezVe-6GF53k9OC2w9TRHg?e=V2luBs)
  (slides 3-15)

- [Twyman\'s Law](http://www.exp-platform.com/Documents/TwymansLaw.pdf)
  for running efficient experiments and getting to results

- [LinkedIn Learning Path on A/B
  Testing](https://www.linkedin.com/learning/paths/microsoft-introduction-to-online-a-b-testing-with-azure-experimentation?shareId=4ce1c06d-615d-40ea-8bab-60f9eb3c9e4d&accountId=3322&u=3322&success=true&authUUID=SAARN4lMQFC7iFGsUqVAFA%3D%3D)

# Contents {#contents .TOC-Heading}

[Product 103: Experiment Fundamentals
[1](#product-103-experiment-fundamentals)](#product-103-experiment-fundamentals)

[Part 1: The Scientific Method
[1](#part-1-the-scientific-method)](#part-1-the-scientific-method)

[Data-driven observations
[2](#data-driven-observations)](#data-driven-observations)

[Falsifiable hypothesis
[2](#falsifiable-hypothesis)](#falsifiable-hypothesis)

[Success metrics [2](#success-metrics)](#success-metrics)

[Guardrail metrics [2](#guardrail-metrics)](#guardrail-metrics)

[Estimated impact [2](#estimated-impact)](#estimated-impact)

[Part 2: Experiment design
[3](#part-2-experiment-design)](#part-2-experiment-design)

[Speed of signal [3](#speed-of-signal)](#speed-of-signal)

[Experiment type [4](#experiment-type)](#experiment-type)

[Exposure percentages [4](#exposure-percentages)](#exposure-percentages)

[Timing [4](#timing)](#timing)

[Statistical analysis [4](#statistical-analysis)](#statistical-analysis)

[Next steps [4](#next-steps)](#next-steps)

[Part 3: Best practices
[5](#part-3-best-practices)](#part-3-best-practices)

[Appendix A: experiment placemat
[6](#appendix-a-experiment-placemat)](#appendix-a-experiment-placemat)

# Part 1: The Scientific Method

Well-formed experiments follow the [Scientific
Method](https://medium.com/pathtoproduct/applying-the-scientific-method-to-product-management-953ca4a51758).
**Below are essential elements of a well-formed experiment.** Having
each of these components for each experiment will ensure they provide
the right signals and contribute to important product decisions.

## Data-driven observations

Observations are data points about user behavior, marketing trends, or
product data that suggest an experiment should be run. **These are
data-based, objective statements that someone else would observe**.
*"MAU is low"* is not an observation because it's subjective. *"MAU is
5M"* is an observation because it is objective.

## Falsifiable hypothesis

Using your quant and qual data-driven observations from above, define a
falsifiable[^1] hypothesis for the critical user journey, funnel, and/or
user experience you're looking to impact. The hypothesis is written
simply as the following

*For a specific audience,*

> *If I make a specific, targeted change,*
>
> *Then I will observe a specific, measurable result.*

The best hypotheses aim to drive a specific and measurable change in
user behavior and include the expected impact from the experiment.

## Success metrics

Experiments should measure the specific user behavior (input metrics)
you're trying to influence because they can be measured at a
moment-in-time. User clicks or sessions are good examples and should be
reflected in your hypothesis (above).

It's also essential to understand how these input metrics ladder up to
your product outputs (like MAU, retention, or revenue) and eventually
your north star. If needed, you can estimate upside in output metrics
based on the causal/correlation relationship between input and output
metrics. The
[Metrics](https://microsoft.sharepoint.com/teams/AIMomentWorkingGroup/Shared%20Documents/General/AI%20Product%20Readiness_Excellence/Playbooks/Product%20104%20-%20Metrics.docx?web=1)
playbook is a useful tool in defining what metrics matter for an
experiment.

## Guardrail metrics

Well run experiences have a set of metrics, which ensure the experiment
is not inadvertently damaging other parts of the user experience. I.e.
if these metrics start to drop then you will stop the experiment. These
metrics are considered "guardrails", "backstops", or sometimes
"secondary". The
[Metrics](https://microsoft.sharepoint.com/teams/AIMomentWorkingGroup/Shared%20Documents/General/AI%20Product%20Readiness_Excellence/Playbooks/Product%20104%20-%20Metrics.docx)
playbook is a useful tool in defining what guardrail metrics to consider
for an experiment.

> ***Exploratory question:** what specific user signals will validate or
> invalidate your hypothesis? What user signals will be your guardrails
> that can tell you if something is going wrong with the experiment in
> the first 24 hours?*

## Estimated impact

Refer to Part 3 of the [Growth
Ideas](https://microsoft.sharepoint.com/teams/AIMomentWorkingGroup/Shared%20Documents/General/AI%20Product%20Readiness_Excellence/Playbooks/Product%20102%20-%20Growth%20Ideas.docx)
playbook. Estimate the movement you're expecting in the success metrics
for your experiment.

# Part 2: Experiment design

Product investments should drive the product north star and busienss. It
can be difficult to not ship a feature that we've spent time, effort,
and energy to build, but we shouldn't be committed to a feature. We
should be committed to the product providing user value and driving
business growth that we can measure through experiments.

Below are essential elements of a well-run experiment. Defining each of
these components for each experiment will ensure they are run
efficiently and lead to statistically significant (statsig) results.
StatSig positive or negative experiments are **GOOD**; they teach us
something. Neutral experiments are **BAD**; they teach us nothing. **So
swing big!**

## Speed of signal

Find the fastest, cheapest way to prove or disprove your hypothesis.
Consider testing via mockups, prototypes, or "painted doors". Evaluate
the approach of a partial implementation with where certain
functionality is hard coded. Mitigate risk by limiting audience size.

## Experiment type

Depending on the hypothesis you're testing, determine whether you need a
controlled rollout or feature experiment.

- [Feature experiment]{.underline} is used for new features,
  experiences, or concepts. These tests are meant to improve success
  metrics, and rollout is dependent on a statsig positive result.

- [Controlled rollout]{.underline} is used for privacy, security,
  branding, or technology investments. Similar to Feature Experiments we
  would like a positive result to roll out but a neutral result is also
  acceptable.

## Exposure percentages

You will have already defined the users who will see your experiment as
part of the hypothesis. Now decide what percentage of what user group
you want to be exposed to the experiment. Traditionally experiments are
run at 50/50, but you can balance minimizing risk and reducing COGS with
getting signal by running a smaller treatment group: 80/20, 90/10, or
even 95/5.

> ***Exploratory question:** what percentages will balance minimizing
> risk with getting signal. Is 50/50 best?*

## Timing

Calculate how long you expect the experiment to run before getting to
statistical significance. Be sure to include external factors like
seasonality or weekly trends. Consider [hold-out
groups](https://medium.com/pinterest-engineering/how-holdout-groups-drive-sustainable-growth-35a4786c3801)
to assess long-term impact to key metrics.

## Statistical analysis

At this stage metrics become essential to understanding the effects of
any experiment. Using data from the control and treatment groups and
statistical analysis tools, calculate whether there was a "significant"
change in user behavior for the test group. Significant meaning we have
a certain percentage of confidence that the change in user behavior is
due to the experiment and not an external factor. Make sure to look at
guardrail metrics as well. Online tools or data scientists can easily
run a statistical analysis for you. They are typically framed in the
following way.

![A picture containing text, font, handwriting, line Description
automatically generated](media/image2.png){width="5.805854111986002in"
height="1.5556353893263342in"}

Since statistical analyses generate normalized curves, the way to read
this image is we are 98% confident that the change in user behavior is
somewhere between +2.8% and +11.6%, but likely right around 7.2%.

> **Exploratory question:** if the experiment is not getting to StatSig,
> we need to ask why. Are we looking at the right metric? Are there bugs
> that could be affecting the test? Is the test aggressive enough?

## Next steps

Based on results, you'll have to decide what to do next.

- If the results are **positive**, evaluate the next phase of the
  experiment to test with a broader audience or rollout the feature to
  everyone.

- If the results are **negative**, consider what caused this outcome,
  make changes to the initial experiment, and retest. Or move on to your
  next hypothesis.

- If the results are **inconclusive**, consider a different
  implementation to test your core hypothesis.

> ***Exploratory question:** what specifically will you do if the
> experiment wins, loses, or is neutral? What are the next steps to
> experiment further, rollout, or pivot.*

# Part 3: Best practices

- **Lean into feature experiments** -- using experimentation to decide
  whether or not to build something and/or which version to implement.
  Every feature that impacts a **user journey** is A/B-tested.

- **Test a product hypothesis** as cheaply and quickly as possible,
  assessing impact on key product metrics.

- Always **track metrics you can impact directly** i.e., input metrics
  that measure user action in the product.

- Create **well-rounded scorecards** that include input, output, and
  guardrail metrics.

- StatSig positive or negative experiments are **GOOD**; they teach us
  something. Neutral experiments are **BAD**; they teach us nothing.

- Make sure that you have **enough variants and a holdout group** so you
  can attribute causality to whatever you test.

- Hold **regular product reviews** (usually monthly) to review
  experiment results (including number of positive, negative, and
  neutral results); along with running and upcoming experiments.

The following resources do a great job of outlining how to functionally
run an experiment.

- [EXP \| creating and running
  experiments](https://microsoft.sharepoint.com/:p:/t/expshared/ESDV47_HvbVAvoY5DHrPLVkBuezVe-6GF53k9OC2w9TRHg?e=V2luBs)
  (slides 16-37)

- Example [experiment entrance
  review](https://eng.ms/docs/products/experimentation-platform/docs/daytoday/experimententrancereview)

- Example [experiment exit
  review](https://eng.ms/docs/products/experimentation-platform/docs/daytoday/experimentexitreview)

- Example [VS experiment
  Template](https://nam06.safelinks.protection.outlook.com/ap/w-59584e83/?url=https%3A%2F%2Fmicrosoft-my.sharepoint.com%2F%3Aw%3A%2Fp%2Fselmai%2FET1_tc-hhyFFq3feZg694voBxf7txF-XsA9zjhUpCNKYuQ%3Fe%3D4%253aOik2as%26at%3D9&data=05%7C01%7CMark.Licata%40microsoft.com%7C2e823c129cc046efdb2008db27493420%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C638146967579546746%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=xUhIz0gfpb5lryq8eDt17LqjN5gFXt%2FFCwCHO7O0P5U%3D&reserved=0)

Additionally, the following resources cover how to analyze data and
results.

- [EXP \| analyzing experiment
  results](https://microsoft.sharepoint.com/:p:/t/expshared/ESDV47_HvbVAvoY5DHrPLVkBuezVe-6GF53k9OC2w9TRHg?e=V2luBs)
  (slides 38-65)

- [Metrics maturity
  model](https://microsoft.sharepoint.com/:w:/r/teams/expshared/_layouts/15/WopiFrame2.aspx?action=edit&sourcedoc=%7B354A308A-4DE6-48B9-A516-3F48BC647FB1%7D&wdOrigin=TEAMS-ELECTRON.null.bim&wdExp=TEAMS-CONTROL&wdhostclicktime=1669151099599&web=1&cid=a68c653c-e416-4855-aa72-9e41d43887bf)
  covering basics like data culture, organizational goals, and authoring
  metrics.

This playbook turned a set of investment ideas into well-formed
experiments. The [Positioning and
GTM](https://microsoft.sharepoint.com/teams/AIMomentWorkingGroup/Shared%20Documents/General/AI%20Product%20Readiness_Excellence/Playbooks/Product%20105%20-%20Positioning%20and%20GTM.docx)
playbook will provide criteria for bringing these investments to market.
Additionally the [AI Product
Building](https://microsoft.sharepoint.com/teams/AIMomentWorkingGroup/Shared%20Documents/General/AI%20Product%20Readiness_Excellence/Playbooks/Product%20202%20-%20Building%20your%20Copilot.docx)
playbook gives some specific areas to think about when experimenting
with AI features.

# Appendix A: experiment placemat

+----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Data-driven  | *What user behavior, marketing, or product data are you seeing that suggests an experiment should be run? These must be **data-based, objective statements** that someone else   |
| observations** | would observe as well. "MAU is low" is not an observation because it's subjective. "MAU is 5M" is an observation.*                                                               |
+================+==================================================================================================================================================================================+
| **Test type**  | *Is the experiment a product evolution or qualification?*                                                                                                                        |
|                |                                                                                                                                                                                  |
|                | - ***Feature experiment** is used for new features, experiences or concepts. They are meant to improve success metrics, and rollout is dependent on a statsig positive result.*  |
|                |                                                                                                                                                                                  |
|                | - ***Controlled rollout** is used for privacy, security, branding, or technology investments. They are meant to prove no harm, and rollout is dependent on a neutral or better   |
|                |   result.*                                                                                                                                                                       |
+----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Hypothesis** | *Written simply as the following:*                                                                                                                                               |
|                |                                                                                                                                                                                  |
|                | *For a **specific audience**,*                                                                                                                                                   |
|                |                                                                                                                                                                                  |
|                | > *If I make a **specific, targeted change**,*                                                                                                                                   |
|                | >                                                                                                                                                                                |
|                | > *Then I will observe a **specific, measurable result**.*                                                                                                                       |
|                |                                                                                                                                                                                  |
|                | *Bonus points for making a [falsifiable                                                                                                                                          |
|                | hypothesis](https://blogs.stjude.org/progress/hypothesis-must-be-falsifiable.html#:~:text=A%20hypothesis%20or%20model%20is,obtained%2C%20would%20disprove%20the%20hypothesis.);  |
|                | i.e. it can be proven wrong or incorrect.*                                                                                                                                       |
+----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Success      | *What product INPUT metrics will you use to determine success? These should tie directly to your falsifiable hypotheses. Feel free to leverage the                               |
| metric(s) and  | [Metrics](https://microsoft.sharepoint.com/teams/AIMomentWorkingGroup/Shared%20Documents/General/AI%20Product%20Readiness_Excellence/Playbooks/Product%20104%20-%20Metrics.docx) |
| expected       | playbook for help with metrics.*                                                                                                                                                 |
| impact**       |                                                                                                                                                                                  |
+----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Guardrail    | *What product INPUT metrics will serve as your backstop that you set before you start the experiment? I.e. if they start to drop then you will stop the experiment.*             |
| metrics**      |                                                                                                                                                                                  |
+----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Timing /     | *What are the expected start and end dates of the experiment? How long do you expect the experiment to run for before getting to statistical significance?*                      |
| dates**        |                                                                                                                                                                                  |
+----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Exposure     | *What percentages will you run your experiment at, which will balance COGS and minimize risk with getting signal. Is 50/50 best or perhaps 80/20, 90/10, etc.?*                  |
| percentages**  |                                                                                                                                                                                  |
+----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

[^1]: [*falsifiable
    hypothesis*](https://blogs.stjude.org/progress/hypothesis-must-be-falsifiable.html#:~:text=A%20hypothesis%20or%20model%20is,obtained%2C%20would%20disprove%20the%20hypothesis.)
