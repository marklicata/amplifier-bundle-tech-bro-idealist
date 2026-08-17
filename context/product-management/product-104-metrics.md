[]{#_Toc939704676 .anchor}Product 104: Product Metrics

**Purpose:**

Defining product metrics is a critical part of product development.
Whether that's defining outcomes for your product; monitoring product
health; or validating impact of experiments. Without the right
measurement in place we can't know if we're building the right product.
And just like the product itself, product metrics need to be continually
iterated upon. This measurement becomes even more important for products
where the cost is high but value and impact are unproven.

**Audience:** GPMs and Product Leads

**Add'l resources**

- [Data Practice
  Assessment](https://microsoft.sharepoint.com/:w:/t/TeamCTO/EUaPQA7GNmJMn2TkbVy8X8YBRBwvXKUGrfYN-LFQxSGwDg?e=ZLtV1Y)

- [Product metrics
  primer](https://microsoft.sharepoint.com/:w:/t/TeamLeonardo/ET5RrDpdBvhLk0NcLfhcomYByaQvqnvHbJZWxO92fR7_Iw?e=x7d22a)

- [Metrics
  Ladder](https://microsoft.sharepoint.com/:w:/t/TeamLeonardo/EYQAvot3ROdNgGFFbK5DPRcBwU7CnYj8AyPZC787f9XaDQ?e=8uD5Vj)

# Contents {#contents .TOC-Heading}

[Product 104: Product Metrics [1](#_Toc939704676)](#_Toc939704676)

[Part 1: Metrics ladders
[1](#part-1-metrics-ladders)](#part-1-metrics-ladders)

[North star metrics
[2](#examples-north-star-metricnorth-star-metrics)](#examples-north-star-metricnorth-star-metrics)

[Lifecycle metrics [2](#lifecycle-metrics)](#lifecycle-metrics)

[Guardrail metrics [3](#guardrail-metrics)](#guardrail-metrics)

[Input metrics [3](#input-metrics)](#input-metrics)

[Part 2: Critical user journeys / funnels
[4](#part-2-critical-user-journeys-funnels)](#part-2-critical-user-journeys-funnels)

[Part 3: Re-engagement loops
[5](#part-3-re-engagement-loops)](#part-3-re-engagement-loops)

[Flywheels [5](#flywheels)](#flywheels)

[Part 4: Best practices
[6](#part-4-best-practices)](#part-4-best-practices)

[Appendix A: example metrics
[7](#appendix-a-example-metrics)](#appendix-a-example-metrics)

[Appendix B: metrics ladder examples
[9](#appendix-b-metrics-ladder-examples)](#appendix-b-metrics-ladder-examples)

# Part 1: Metrics ladders

A metrics ladder---aka metrics hierarchy---is a map of metrics that
connects top-line business metrics with metrics individual teams try to
influence on a day-by-day basis. The ladder has leading indicators/input
metrics at the bottom and lagging indicators/output metrics at the top.
When done right, this enables leaders and teams to understand current
product & business performance, identify growth opportunities/friction,
and quickly evaluate whether we\'re making the right investments.

Below is a simple frame for how metrics ladder on top of one another.

- First **Product** **Input metrics**: measuring user behavior or
  actions in the product at a moment in time. They indicate how
  successfully users are using the product. They are leading indicators
  and good proxies for output metrics. For e.g., messages sent, docs
  shared, communities created.

- Second **Product** **Output metrics**: product outcomes that are
  driven by input metrics. These are typically lifecycle metrics that
  look at how users use and find value in the product over a period of
  time. They are lagging indicators of product performance. For e.g.,
  active users (MAU, DAU), engaged users (WEU), sessions, retention.

- Finally **Financial metrics**: the topline business metrics are driven
  by product input and output metrics. Product teams typically focus on
  the first three with finance teams calculating financial impact based
  on them. For e.g., ARPU, total revenue, CAC, LTV.

Your metrics ladder will be unique to your product and business. Below
is an example of how LinkedIn set up their metrics ladder, but yours may
have more layers, different metrics, fewer north stars, or something
else. The key is establishing a causal/correlation relationship between
metrics.

## ![Examples North Star Metric](media/image2.jpg){width="2.1145833333333335in" height="2.1145833333333335in"}North star metrics

The North Star is the output metric that best captures the core value
that your product delivers to customers. A well designed [north
star](https://blog.growthhackers.com/what-is-a-north-star-metric-b31a8512923f)
reflects the moment a customer receives the intended value from the
product and is something within the teams' control to impact.

**While a single north star metric can create tremendous clarity +
focus, it can also be potentially [limiting or drive the wrong
outcomes](https://www.reforge.com/blog/north-star-metric-growth).** So
consider whether your product has one or a few north stars. LinkedIn
(above) has 4.

> ***Exploratory question**: what are you product's north star
> metric(s)? i.e. the number that if improved will drive long-term
> performance improvement?*

## Lifecycle metrics

Starting first with Acquisition, Every product should track lifecycle
metrics across acquisition, activation, engagement, retention, and
conversion. Funnels are the most popular way to track these and enable a
time-series view (longitudinally). Additional dimensions like
device-type, geo, cohort, segment, etc. are also helpful in identifying
trends and diagnosing issues. Pay particular attention to lifecycle
metrics that directly influence your north star metric(s). Note that
these may change over time.

> ***Exploratory question**: What subset of lifecycle metrics directly
> contribute to your north star metric(s)?*

## Guardrail metrics

Since no metric is perfect, we need counterbalance metrics to ensure we
don't over-optimize locally. Also, no metric lives in isolation, and
often there is natural tension between metrics (e.g., one approach to
growing ad revenue may be to increase ad spots which may negatively
impact long-term engagement). Defining guardrail or check metrics can
help monitor for unintended changes and surface implicit tradeoffs to
allow for a more deliberate decision.

In the Teams Consumer example from above, the team monitors taskbar
unpins for the Teams app on Win11 very closely.

> ***Exploratory question**: what are the guardrail metric(s) for your
> product? What user actions in the product would indicate users are
> undoing or taking an unintended, negative action? Where is that
> tension in your product?*

## Input metrics

These are the user actions that are correlated with your product output
or lifecycle metrics and are much easier to influence with product
changes. Input metrics are typically tied to core value props and are
sometimes called value metrics.

In the Teams Consumer example from above, the team observed much higher
4-week retention for users who perform at least one collab action. So
they broke down collab into individual actions (send invite, join
meeting, send IM, etc.) to see which had the most influence on
retention, and then experiment with getting more users to complete those
actions.

> ***Exploratory question**: what actions in the product indicate users
> are finding value? The Aha and Magic moments discussed in the Growth
> Ideas playbook. How do those actions correlate with the lifecycle and
> north star metrics of your product?*

Eventually, you'll build a map of key product output and input metrics
and the relationships between them, but this correlation may shift over
time. Or the initial correlation was wrong or for new relationships will
emerge. So it's essential to closely monitor and periodically revisit
these causal or correlation mappings.

Note: in addition to metrics that evaluate success of the product,
metrics that signals that tell us the product isn\'t' performing as it
should are equally valuable. Repeated actions, for example, could
indicate the user doesn't believe the model, is attempting to jailbreak,
etc.

# Part 2: Critical user journeys / funnels

A critical user journey (CUJ) is a series of steps or interactions that
is both high traffic (ex. an onboarding or purchase flow) and creates
high user value (ex. the collab journeys from the Teams example above).
These journeys represent the \"happy paths\" allowing users to derive
value in the product. Many of the integrated AI experiences---like Word
copilot or Designer tools---can be measured as a funnel. Even though the
technology is different, the goal remains to enable the user to find
value via a specific outcome that is closely correlated with retention.

> ***Exploratory question**: what are the critical user journeys for
> your product? Do you have the telemetry to create funnel analysis and
> derive insights? What input metrics do these journeys drive that
> ladder up to output and north star metrics?*

# Part 3: Re-engagement loops

Critical user journeys and funnels have a clearly defined endpoint.
Assuming the journeys work well, the user will achieve the goal or take
the action at the end of the funnel, and that's by design. Constantly
growth hacking to streamline these flows creates a narrow focus and
assumes users need a simple action to meet their need.

For experiences where the user doesn't have a clearly defined endpoint,
it's important to understand user engagement and re-engagement patterns
and **measure outcomes, not just activity** indicating the user is
finding value. For example, metrics like DAU or sessions won't be very
insightful for support conversations or looking at product detail pages
in a Store flow because those metrics don't really indicate if users are
finding value in the product. For interactive products and features, a
"loop" or "flywheel" works much better.

## Flywheels

The flywheel and funnel are both frameworks for understanding customer
interactions, but the flywheel focuses on whether users are finding
value in the product and returning over time. Flywheels nurture user
value and delight by focusing on...

- ...product features meant to drive **engagement** and **retention**
  through **user value** and personalized relationships.

- ...**ongoing and cyclical** engagements rather than linear sessions.
  Users may come back to an experience multiple times, finding value
  each time.

Flywheels contain one to many steps, but they typically have 4 specific
stages that users are meant to travel through.

![](media/image4.png){width="6.113888888888889in"
height="3.1666666666666665in"}

1.  **Trigger** -- user has an initial "need" that the product could
    potentially meet.

2.  **Action** -- users starts a new session with the product. This step
    measures the **size & health** of the user base

    - \# of users per month, per week, and per day

    - \# of sessions per month, week, day

    - \# sessions per user OR \# sessions where AI is used

3.  **Investment** -- user then continues to engage with the product
    because they found value

    - \# of specific actions showing positive interactions. Focusing on
      user-value.

    - \# of high-value actions completed, from the totality of actions
      users can take.

    - \# of visits or sessions

    - \# of positive conversations with an agent

    - Avg length of a session

4.  **Variable reward** -- user experiences a magic moment in the
    product. These moments are typically the greatest indicators of
    retention.

    - \# of users experiencing **magic moments** in the product. i.e.
      specific actions most closely correlated with retention.

    - \# of magic moments experienced by 1-n users in the product.

    - \# of users experiencing a threshold of magic moments that turns
      them into a net promoter.

5.  **Re-trigger** -- user has a new "need" that the product could
    potentially solve. This step measures how well the product retains
    users. High retention indicates the user found value.

    - \# of 2^nd^, 3^rd^, and 4^th^ sessions

    - \# of retained users per month, per week, and per day

# Part 4: Best practices

- Identity **metrics that matter** for your product and understand how
  they **ladder up** to key business and financial metrics.

- Invest in **causal** and/or **correlation analysis** to identify key
  drivers for output metrics.

- **Periodically revisit** key product metrics and refresh causal +
  correlation mappings.

- Track and review metrics **longitudinally** whenever possible. Key
  insights often emerge from trends.

- Make sure you can slice funnels, CUJs, output, and input metrics by
  various dimensions. Your **user bases are rarely (if ever)
  homogeneous**.

# Appendix A: example metrics

Below are some **example** metrics the team can consider. Note product
inputs specifically will be very specific to your product and AI
experiences.

+-------------+------------------+--------------------------------------------+
| **Area**    | **Example        | **Description**                            |
|             | Metrics**        |                                            |
+:===========:+==================+============================================+
| > **Input   | Page views       | Number of users who viewed a specific      |
| > metrics** |                  | page.                                      |
|             +------------------+--------------------------------------------+
|             | Clicks           | Number of users who clicked on a specific  |
|             |                  | element.                                   |
|             +------------------+--------------------------------------------+
|             | Tasks / Actions  | Number of users who completed a specific   |
|             |                  | task or action. Conversely the number of   |
|             |                  | times a specific task or action was        |
|             |                  | completed.                                 |
+-------------+------------------+--------------------------------------------+

+-------------------------------+------------------+--------------------------------------------+
| **Area**                      | **Example        | **Description**                            |
|                               | Metrics**        |                                            |
+:===========:+:===============:+==================+============================================+
| > **Output  | > **Acquisition | New Users        | Number of new users active in the product  |
| > metrics** | > / User        |                  | over a 28 day period.                      |
|             | > Growth**      |                  |                                            |
|             |                 +------------------+--------------------------------------------+
|             |                 | Monthly Active   | Number of users active in the product      |
|             |                 | Users (MAU)      | during a given month.                      |
|             |                 +------------------+--------------------------------------------+
|             |                 | Weekly Active    | Number of users active in the product      |
|             |                 | Users (WAU)      | during a given week.                       |
|             |                 +------------------+--------------------------------------------+
|             |                 | Daily Active     | Number of users active in the product      |
|             |                 | Users (DAU)      | during a given day.                        |
|             |                 +------------------+--------------------------------------------+
|             |                 | Quick Ratio[^1]  | The ratio of new + returning users divided |
|             |                 |                  | by churned users. A ratio \>1 indicates    |
|             |                 |                  | growth; \<1 indicates decline.             |
|             |                 +------------------+--------------------------------------------+
|             |                 | Viral            | Number of users acquired to the product    |
|             |                 | Acquisition      | via user generated growth like shares or   |
|             |                 |                  | invites. Not traditional Microsoft GTM     |
|             |                 |                  | motions.                                   |
|             |                 +------------------+--------------------------------------------+
|             |                 | Monthly Active   | Number of active devices during a given    |
|             |                 | Devices (MAD)    | month. Can also be a variation like PBMAD. |
|             +-----------------+------------------+--------------------------------------------+
|             | > **User        | Monthly Engaged  | Number of users engaged in the product     |
|             | > Engagement**  | Users (MEU)      | during a given month.                      |
|             |                 | (cohort          |                                            |
|             |                 | analysis)        |                                            |
|             |                 +------------------+--------------------------------------------+
|             |                 | Weekly Engaged   | Number of users engaged in the product     |
|             |                 | Users (WEU)      | during a given week.                       |
|             |                 +------------------+--------------------------------------------+
|             |                 | Daily Engaged    | Number of users engaged in the product     |
|             |                 | Users (DEU)      | during a given day.                        |
|             |                 +------------------+--------------------------------------------+
|             |                 | P95 latency of   | The P95 latency of the top 3 service       |
|             |                 | top 3 workloads  | workloads in the product.                  |
|             |                 +------------------+--------------------------------------------+
|             |                 | Time Spent       | The time spent in a product or doing a     |
|             |                 |                  | specific set of tasks. Usually measured in |
|             |                 |                  | minutes.                                   |
|             |                 +------------------+--------------------------------------------+
|             |                 | Net Sentiment    | The % of positive sentiment minus the % of |
|             |                 | Score (NSS)      | negative sentiment from feedback looks     |
|             |                 |                  | like surveys.                              |
|             |                 +------------------+--------------------------------------------+
|             |                 | Net Promotor     | How likely users are to recommend a        |
|             |                 | Score (NPS)      | product on a scale of 0-10 measured        |
|             |                 |                  | through regular surveys.                   |
|             +-----------------+------------------+--------------------------------------------+
|             | > **User        | DAU / MAU %      | \% of Monthly Active Users who are using   |
|             | > Retention**   |                  | the product Daily.                         |
|             |                 +------------------+--------------------------------------------+
|             |                 | 7d / 14d / 28d / | Number of monthly active users seen in two |
|             |                 | 60d Returning    | consecutive \[x\] day periods.             |
|             |                 | MAU (cohort      |                                            |
|             |                 | analysis)        | A MoM cohort analysis should be provided   |
|             |                 |                  | for this metric.                           |
|             |                 +------------------+--------------------------------------------+
|             |                 | Churned Users    | Number of users who were not seen in the   |
|             |                 |                  | product during two consecutive 28 day      |
|             |                 |                  | periods.                                   |
+-------------+-----------------+------------------+--------------------------------------------+

+---------------------------------+------------------+--------------------------------------------+
| **Area**                        | **Example        | **Description**                            |
|                                 | Metrics**        |                                            |
+:=============:+:===============:+==================+============================================+
| > **Financial | > **Market      | Share Growth     | Not the market share of the product as     |
| > or Business | > Share**       |                  | that is likely to be low. Instead the %    |
| > metrics**   |                 |                  | change in market share over time.          |
|               |                 +------------------+--------------------------------------------+
|               |                 | Share on Windows | On Windows devices, what is the share of   |
|               |                 |                  | users using your product vs. competitors.  |
|               |                 |                  | For example: Browser Share of Minutes in   |
|               |                 |                  | Edge; Bing search share vs. Google; Steam  |
|               |                 |                  | vs. Game Pass                              |
|               +-----------------+------------------+--------------------------------------------+
|               | > **Financial** | Customer         | The cost to acquire a single new user to   |
|               |                 | Acquisition Cost | the product.                               |
|               |                 | (CAC)            |                                            |
|               |                 +------------------+--------------------------------------------+
|               |                 | LifeTime Value   | The revenue made from a single user in the |
|               |                 | (LTV)            | product over the customer's lifespan.      |
|               |                 +------------------+--------------------------------------------+
|               |                 | Average Revenue  | Revenue generated by each user in a        |
|               |                 | per User (ARPU)  | product. Usually measured as total revenue |
|               |                 |                  | or average revenue per user.               |
|               |                 +------------------+--------------------------------------------+
|               |                 | Gross Adds       | The total number of new subscribers added  |
|               |                 |                  | via the product over a period of time;     |
|               |                 |                  | usually monthly.                           |
|               |                 +------------------+--------------------------------------------+
|               |                 | End of Period    | The number of subscribers measured at a    |
|               |                 | Subscribers      | moment in time. Including both new         |
|               |                 | (EOP)            | subscriber adds and subscribers churned.   |
|               |                 +------------------+--------------------------------------------+
|               |                 | Advertising      | Number of Ads that were surfaced to users. |
|               |                 | metrics.         |                                            |
|               |                 |                  | The average cost of a user clicking on an  |
|               |                 | > Impressions    | Ad.                                        |
|               |                 | >                |                                            |
|               |                 | > Cost per Click | The average cost of a user clicking on an  |
|               |                 | > (CPC)          | Ad and purchasing.                         |
|               |                 | >                |                                            |
|               |                 | > Cost per       |                                            |
|               |                 | > Acquisition    |                                            |
|               |                 +------------------+--------------------------------------------+
|               |                 | Ad Cost per      | The average cost of a user clicking on an  |
|               |                 | Acquisition      | Ad and purchasing.                         |
|               |                 | (CPA)            |                                            |
+---------------+-----------------+------------------+--------------------------------------------+

# Appendix B: metrics ladder examples

![Timeline Description automatically
generated](media/image5.png){width="4.90625in"
height="2.703472222222222in"}

![A diagram of a company Description automatically generated with low
confidence](media/image6.png){width="5.177084426946632in"
height="2.410416666666667in"}

![A screenshot of a computer Description automatically generated with
low confidence](media/image7.png){width="6.663888888888889in"
height="3.747916666666667in"}

[^1]: [Quick Ratio as a Shortcut to Understand Product
    Growth](https://medium.com/theventurecity/quick-ratio-as-a-shortcut-to-understand-product-growth-ae60212bd371)
