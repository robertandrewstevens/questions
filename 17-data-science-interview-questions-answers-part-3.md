17 More Must-Know Data Science Interview Questions and Answers, Part 3
================
Robert A. Stevens
2021-12-14

<https://www.kdnuggets.com/2017/03/17-data-science-interview-questions-answers-part-3.html>

Tags: 3Vs of Big Data, A/B Testing, Big Data, Data Quality, Data
Science, Data Visualization, Influencers, Interview Questions,
Statistics, Twitter

*The third and final part of 17 new must-know Data Science interview
questions and answers covers A/B testing, data visualization, Twitter
influence evaluation, and Big Data quality.*

By Matthew Mayo, KDnuggets.

Editor’s note: This is the third and final part of this post. See also:

-   17 More Must-Know Data Science Interview Questions and Answers, Part
    1

<https://www.kdnuggets.com/2017/02/17-data-science-interview-questions-answers.html>

-   17 More Must-Know Data Science Interview Questions and Answers, Part
    2

<https://www.kdnuggets.com/2017/02/17-data-science-interview-questions-answers-part-2.html>

This post contains answers to:

-   Q13. What makes a good data visualization?

-   Q14. What are some of the common data quality issues when dealing
    with Big Data? What can be done to avoid them or to mitigate their
    impact?

-   Q15. In an A/B test, how can we ensure that assignment to the
    various buckets is truly random?

-   Q16. How would you conduct an A/B test on an opt-in feature?

-   Q17. How to determine the influence of a Twitter user?

## Q13. What makes a good data visualization?

Gregory Piatetsky answers:

Note: This answer contains excerpts from the recent post “What makes a
good data visualization – a Data Scientist perspective”.

<https://www.kdnuggets.com/2017/03/what-makes-good-data-visualization.html>

Data Science is more than just building predictive models - it is also
about explaining the models and using them to help people to understand
data and make decisions. Data visualization is an integral part of
presenting data in a convincing way.

There is a ton of research of good data visualization and how people
best perceive information - see work by Stephen Few and many others.

Guidelines on improving human perception include:

-   position data along a common scale

-   bars are more effective than circles or squares in communicating
    size

-   color is more discernible than shape in scatterplots

-   avoid pie chart unless it is for showing proportions

-   avoid 3D charts and reduce chartjunk

-   Sunburst visualization is more effective for hierarchical plots

-   use small multiples (even though animation looks cool, it is less
    effective for understanding changing data)

See “39 studies about human perception”, by Washington Post graphics
editor for a lot more detail.

<https://medium.com/@kennelliott/39-studies-about-human-perception-in-30-minutes-4728f9e31a73#.irdxe7jip>

From Data Science point of view, what makes visualization important is
highlighting the key aspects of data - what are the most important
variables, what is their relative importance, what are the changes and
trends.

Data visualization should be visually appealing but not at the expense
of loading a chart with unnecessary junk, like in this extreme example:

<img src="chart-junk-diamonds-300.jpg" style="width:50.0%" />

**Chart Junk**

### How do we make a good data visualization?

To do that, choose the right type of chart for your data:

-   Line Charts to track changes or trends over time and show the
    relationship between two or more variables

-   Bar Charts to compare quantities of different categories

-   Scatter Plots show joint variation of two data items

-   Pie Charts to compare parts of a whole - used them sparingly since
    people have hard time comparing the area of pie slices

-   You can show additional variables on a 2-D plot using color, shape,
    and size

-   Use interactive dashboards to allow experiments with key variables

Here is an example of visualization of US Presidential Elections,
1976-2016, that shows multiple variables at once: the electoral college
votes difference (y-axis), the % popular vote difference (X-axis), the
size of the popular vote (circle area), winner party (color), and winner
name and year (label).

<img src="visualization-us-elections-1976-2016.jpg" style="width:100.0%" />

**US Presidential Elections, 1976-2016**

See my post on “What makes a good data visualization” for more details.

<https://www.kdnuggets.com/2017/03/what-makes-good-data-visualization.html>

References:

-   What makes a good visualization, David McCandless, Information is
    Beautiful

<http://www.informationisbeautiful.net/visualizations/what-makes-a-good-data-visualization/>

-   5 Data Visualization Best Practices, GoodData

<https://www.gooddata.com/blog/5-data-visualization-best-practices>

-   39 studies about human perception in 30 minutes, Kenn Elliott

<https://medium.com/@kennelliott/39-studies-about-human-perception-in-30-minutes-4728f9e31a73#.irdxe7jip>

-   Data Visualization for Human Perception, landmark work by Stephen
    Few

<https://www.interaction-design.org/literature/book/the-encyclopedia-of-human-computer-interaction-2nd-ed/data-visualization-for-human-perception>

-   Key ideas summarized here:

<https://viscomvibz.wordpress.com/2012/02/27/data-visualization-for-human-perception/>

## Q14. What are some of the common data quality issues when dealing with Big Data? What can be done to avoid them or to mitigate their impact?

Anmol Rajpurohit answers:

The most common data quality issues observed when dealing with Big Data
can be best understood in terms of the key characteristics of Big Data –
Volume, Velocity, Variety, Veracity, and Value.

### Volume:

In the traditional data warehouse environment, comprehensive data
quality assessment and reporting was at least possible (if not, ideal).
However, in the Big Data projects the scale of data makes it impossible.
Thus, the data quality measurements can at best be approximations
(i.e. need to be described in probability and confidence intervals, and
not in terms of absolute values). We also need to re-define most of the
data quality metrics based on the specific characteristics of the Big
Data project so that those metrics can have a clear meaning, be measured
(good approximation) and be used for evaluating the alternative
strategies for data quality improvement.

Despite the great volume of underlying data, it is not uncommon to find
out that some desired data was not captured or is not available for
other reasons (such as high cost, delay in getting it, etc.). It is
ironical but true that data availability continues to be a prominent
data quality concern in the Big Data era.

### Velocity:

The tremendous pace of data generation and collection makes it
incredibly hard to monitor data quality within a reasonable overhead on
time and resources (storage, compute, human effort, etc.). So, by the
time data quality assessment completes, the output might be outdated and
of little use, particularly if the Big Data project is to serve any
real-time or near real-time business needs. In such scenarios, you would
need to re-define data quality metrics so that they are relevant as well
as feasible in the real-time context.

Sampling can help you gain speed for the data quality efforts, but this
comes at the cost of a bias (which eventually makes the end result less
useful) because of the fact that samples are rarely an accurate
representation of the entire data. Lesser samples will give higher
speed, but with a bigger bias.

Another impact of velocity is that you might have to do data quality
assessments on-the-fly, i.e. somewhere plugged-in within the data
collection/transfer/storage processes; as the critical time-constraint
does not give you the privilege of making a copy of a selected data
subset, storing it elsewhere and running data quality assessments on it.

### Variety:

One of the biggest data quality issues in Big Data is that the data
includes several data types (structured, semi-structured, and
unstructured) coming in from different data sources. Thus, often a
single data quality metric will not be applicable for the entire data
and you would need to separately define data quality metrics for each
data type. Moreover, assessing and improving the data quality of
unstructured or semi-structured data is way more tricky and complex than
that of structured data. For example, when mining the physician notes
from medical records across the world (related to a particular medical
condition) even if the language (and the grammar) is same the meaning
might be very different due to local dialects and slang. This leads to
low data interpretability, another data quality measure.

Data from different sources often has serious semantic differences. For
example, “profit” can have widely varied definitions across the business
units of an organization or external agencies. Thus, the fields with
identical names may not mean the same thing. This problem is made worse
by the lack of adequate and consistent meta-data from each data source.
In order to make sense of data, you need reliable metadata (such as to
make sense of sales numbers from a store, you need other information
such as date-time, items purchased, coupons used, etc.). Usually, a lot
of these data sources are outside an organization and thus, it is very
hard to ensure good metadata for such data.

Another common issue is syntactic inconsistencies. For example,
“time-stamp” values from different sources would be incompatible unless
they are captured along with the time zone information.

### Veracity:

Veracity, one of the most overlooked Big Data characteristics, is
directly related to data quality, as it refers to the inherent biases,
noise and abnormality in data. Because of veracity, the data values
might not be exact real values, rather they might be approximations. In
other words, the data might have some inherent impreciseness and
uncertainty. Besides data inaccuracies, Veracity also includes data
consistency (defined by the statistical reliability of data) and data
trustworthiness (based on data origin, data collection and processing
methods, security infrastructure, etc.). These data quality issues in
turn impact data integrity and data accountability.

While the other V’s are relatively well-defined and can be easily
measured, Veracity is a complex theoretical construct with no standard
approach for measurement. In a way this reflects how complex the topic
of “data quality” is within the Big Data context.

Data users and data providers are often different organizations with
very different goals and operational procedures. Thus, it is no surprise
that their notions of data quality are very different. In many cases,
the data providers have no clue about the business use cases of data
users (data providers might not even care about it, unless they are
getting paid for the data). This disconnect between data source and data
use is one of the prime reasons behind the data quality issues
symbolized by Veracity.

### Value:

The Value characteristic connects directly to the end purpose.
Organizations are harnessing Big Data for many diverse business
pursuits, and those pursuits are the real drivers of how data quality is
defined, measured, and improved.

A common and old definition of data quality is that it is the “fitness
of use” for the data consumer. This means that data quality is dependent
on what you plan to do with the data. Thus, for a given data two
different organizations with different business goals will most likely
have widely different measurements of data quality.This nuance is often
not well understood – data quality is a “relative” term. A Big Data
project might involve incomplete and inconsistent data, however, it is
possible that those data quality issues do not impact the utility of
data towards the business goal. In such a case, the business would say
that the data quality is great (and will not be interested in investing
in data quality improvements). For example, for a producer of mashed
potato cans a batch of small potatoes would be of same quality as a
batch of big potatoes. However, for a fast food restaurant making fries,
the quality of the two batches would be radically different.

The Value aspect also brings in the “cost-benefit” perspective to data
quality – whether it would be worth to resolve a given data quality
issue, which issues should be resolved on priority, etc.

<img src="BD-5Vs.png" style="width:100.0%" />

Image source:
<http://informationcatalyst.com/index.php/vision-experience/big-data-value/>

### Putting it all together:

Data quality in Big Data projects is a very complex topic, where the
theory and practice often differ. I haven’t come across any standard
theory yet that is widely-accepted. Rather, I see little interest in the
industry towards this goal.In practice, data quality does play an
important role in the design of Big Data architecture. All the data
quality efforts must start from a solid understanding of high-priority
business use cases, and use that insight to navigate various trade-offs
(samples given below) to optimize the quality of the final output.

Sample trade-offs related to data quality:

-   Is it worth improving the timeliness of data at the expense of data
    completeness and/or inadequate assessment of accuracy?

-   Should we select data for cleaning based on cost of cleaning effort
    or based on how frequently the data is used or based on its relative
    importance within the data models consuming it?

    -   Or, a combination of those factors?
    -   What sort of combination?

-   Is it a good idea to improve data accuracy through getting rid of
    incomplete or erroneous data?

    -   While removing some data, how do we ensure that no bias is
        getting introduced?

Given the magnanimous scope of work and very limited resources
(relatively!), one common way for data quality efforts on Big Data
projects is to adopt the baseline approach, in which, the data users are
surveyed to identify and document the bare minimum data quality needed
to ensure that the business processes they support are not disrupted.
These minimum satisfactory levels of data quality are referred to as the
baseline, and the data quality efforts are focused on ensuring that data
quality for each data does not fall beyond its baseline level. It looks
like a good starting point and you may later move into more advanced
endeavors (based on business needs and available budget).

### Summary of Recommendations to improve data quality in Big Data projects:

-   Identify and prioritize the business use cases
    -   Then, use them to define data quality metrics, measurement
        methodology, improvement goals, etc.
-   Based on a strong understanding of the business use cases and the
    Big Data architecture implemented to achieve them, design and
    implement an optimal layer of data governance
    -   Data definitions, metadata requirements, data ownership, data
        flow diagrams, etc.
-   Document baseline quality levels for key data
    -   Think of “critical-path” diagram and “throughput-bottleneck”
        assessment
-   Define ROI for data quality efforts
    -   In order to create feedback loop on the ROI metric to improve
        efficiency and to sustain funding for data quality efforts
-   Integrate data quality efforts
    -   To achieve efficiency through minimizing redundancy
-   Automate data quality monitoring
    -   To reduce cost as well as to let employees stay focused on
        complex tasks

Do not rely on machine learning to automatically take care of poor data
quality (machine learning is science and not magic!)

## Q15. In an A/B test, how can we ensure that assignment to the various buckets is truly random?

Matthew Mayo answers:

First, let’s consider how we can best ensure comparability between
buckets prior to bucket assignment, without knowledge of any
distribution of attributes in the population.

The answer here is simple: random selection and bucket assignment.
Random selection and assignment to buckets without regard to any
attribute of the population is a statistically sound approach, given a
large enough population to draw from.

For example, let’s say you are testing a change to a website feature and
are interested in response from only a particular region, the US. By
first splitting into 2 groups (control and treatment) without regard to
user region (and given a large enough population size), assignment of US
visitors should be split between these groups. From these 2 buckets,
visitor attributes can then be inspected for the purposes of testing,
such as:

    if (region == "US" && bucket == "treatment"):
        # do something treatment-related here
    else:
        if (region == "US" && bucket == "control"):
            # do something control-related here
        else:
            # catch-all for non-US (and not relevant to testing scenario)

<img src="bias-ab-testing.png" style="width:100.0%" />

**Bias AB testing**

Image Source:
<https://blog.twitter.com/2015/detecting-and-avoiding-bucket-imbalance-in-ab-tests>

Bear in mind that, even after performing a round of random bucket
assignment, statistical testing can be utilized to inspect/verify random
distribution of bucket member attributes (e.g. ensure that significantly
more US visitors did not get assigned to bucket A). If not, a new random
assignment can be attempted (with a similar inspection/verification
process), or - if it is determined that the population does not conform
to a cooperative distribution - an approach such as the following can be
pursued.

If we happen to know of some uneven population attribute distribution
prior to bucket assignment, stratified random sampling may be helpful in
ensuring more evenly distributed sampling.

<https://en.wikipedia.org/wiki/Stratified_sampling>

Such a strategy can help eliminate selection bias, which is the
archenemy of A/B testing.

### References:

-   Detecting and avoiding bucket imbalance in A/B tests

<https://blog.twitter.com/2015/detecting-and-avoiding-bucket-imbalance-in-ab-tests>

-   What are the methods to ensure that the population split for A/B
    test is random?

<https://datascience.stackexchange.com/questions/10406/what-are-the-methods-to-ensure-that-the-population-split-for-a-b-test-is-random>

-   A/B Testing

<https://www.optimizely.com/ab-testing/>

## Q16. How would you conduct an A/B test on an opt-in feature?

Matthew Mayo answers:

This seems to be a somewhat ambiguous question with a variety of
interpretable meanings (an idea supported by this post).

<https://stats.stackexchange.com/questions/95620/how-to-conduct-am-a-b-test-for-a-feature-which-cannot-be-accessed-by-every-visit>

Let’s first look at the different possible interpretations of this
questions and go from there.

### 1. How would you conduct an A/B test on an opt-in version of a feature to a non-opt-in-version?

This would not allow for a fair or meaningful A/B test, since one bucket
would be filled from the entire site’s users, while the other would be
filled from the group which has already opted in. Such a test would be
akin to comparing some apples to all oranges, and thus ill-advised.

### 2. How would you conduct an A/B test on the adoption (or use) of an opt-in feature (i.e. test the actual opting-in)?

This would be testing the actual opting in - such as the testing between
2 versions of a “click here to sign up” feature - and as such is just a
regular A/B test (see the above question for some insight).

### 3. How would you conduct an A/B test on different versions of an opt-in feature (i.e. for those having already opted in)?

This could, again, be construed as one of a few meanings, but I intend
to approach it as a complex scenario of the chaining together of events,
expanded upon below.

<img src="choose-ab-test-type.png" style="width:100.0%" />

**Choose your A/B weapon**

Let’s flesh out #3 from the list above. Let’s first look at a simple
chaining of events which can be tested, and then generalize. Suppose you
are performing an A/B test on an email campaign. Let’s say the variable
will be subject line, and that content remains constant between the 2.
Suppose the subject lines are as follows:

1.  We have something for you

2.  The greatest online data science courses are free this weekend! Try
    now, no commitment!

Contrived, to be sure. All else aside, intuition would say that subject
#2 would get more action.

But beyond that, there is psychology at play. Even though the content
which follows after clicking either of the subjects is the same, the
individual clicking the second subject could reasonably be assumed to
have a higher level of excitement and anticipation of what is to follow.
This difference in expectations and level of commitment between the
groups may lead to a higher percentage of click-throughs for those in
the bucket with subject line #2 - again, even with the same content.

Pivoting slightly… How would you conduct an A/B test on different
versions of an opt-in feature (i.e. for those having already opted in)?

If my interpretation of evaluating a series of chained events is
correct, such an A/B test could commence with different feeder locations
to the same opt-in - of the same content - and move to to different
follow-up landing spots after opt-in, with the intent of measuring what
users do on the resulting landing page being the goal.

Do different originating locations to the same opt-in procedure result
in different follow-up behavior? Sure, it’s still an A/B test, with the
same goals, setup, and evaluation; however, the exact user psychology
being measured is different.

What does this have to do with an interview question? Beyond being able
to identify the basic ideas of A/B testing, being able to walk through
imprecise questions is an asset to people working in analytics and data
science.

## Q17. How to determine the influence of a Twitter user?

Gregory Piatetsky answers:

Social networks are at the center of today’s web, and determining the
influence in a social network is a huge area of research. Twitter
influence is a narrow area within the overall social network influence
research.

The influence of a Twitter user goes beyond the simple number of
followers. We also want to examine how effective are tweets - how likely
they are to be retweeted, favorited, or the links inside clicked upon.
What exactly is an influential user depends on the definition -
different types of influence discussed included celebrities, opinion
leaders, influencers, discussers, innovators, topical experts, curators,
commentators, and more.

A key challenge is to compute influence efficiently. An additional
problem on Twitter is separating humans and bots.

Common measures used to quantify influence on Twitter include many
versions of network centrality - how important is the node within the
network, and PageRank-based metrics.

<img src="kdnuggets-nodexl-20140525-social-network-600.jpg" style="width:100.0%" />

**KDnuggets Twitter Social Network, as visualized in NodeXL in May
2014**

<https://www.kdnuggets.com/2014/05/kdnuggets-social-network-nodexl-may-2014.html>

Traditional network measures used include:

-   Closeness Centrality, based on the length of the shortest paths from
    a node to everyone else
    -   It measures the visibility or accessibility of each node with
        respect to the entire network
-   Betweenness centrality considers for each node i all the shortest
    paths that should pass through i to connect all the other nodes in
    the network
    -   It measures the ability of each node to facilitate communication
        within the network

<https://arxiv.org/pdf/1508.07951.pdf>

Other proposed measures include retweet impact (how likely is the tweet
be retweeted) and variations of PageRank, such as TunkRank - see “A
Twitter Analog to PageRank”.

<http://thenoisychannel.com/2009/01/13/a-twitter-analog-to-pagerank>

An important refinement to overall influence is looking at influence
within a topic - done by Agilience and RightRelevant. For instance,
Justin Bieber may have high influence overall, but he is less
influential than KDnuggets in the area of Data Science.

Twitter provides a REST API which allows access to key measures, but
with limits on the number of requests and the data returned.

<https://dev.twitter.com/>

There were a number of websites that measured Twitter user influence,
but many of their business models did not pan out, since many of them
were acquired or went out of business. Ones which are currently active
include the following:

### Free:

-   Agilience (KDnuggets is #1 in Machine Learning, #1 is Data Mining,
    #2 in Data Science)

<https://www.kdnuggets.com/tag/agilience>

-   Klout (KDnuggets Klout score is 79)

<http://klout.com/>

-   Influence Tracker (KDnuggets influence metric 39.2)

<http://www.influencetracker.com/>

-   Right Relevance - measures specific relevance of twitter users
    within a topic

<http://www.rightrelevance.com/about>

### Paid:

-   Brandwatch (bought PeerIndex)

-   Hubspot

-   Simplymeasured

### Relevant KDnuggets posts:

-   Agilience Top Data Mining, Data Science Authorities

<https://www.kdnuggets.com/2016/11/agilience-top-data-mining-data-science-authorities.html>

-   12 Data Analytics Thought Leaders on Twitter

<https://www.kdnuggets.com/2016/01/menlotechnologies-12-data-analytics-thought-leaders-twitter.html>

-   The 123 Most Influential People in Data Science

<https://www.kdnuggets.com/2015/09/123-influential-people-data-science.html>

-   RightRelevance helps find key topics, top influencers in Big Data,
    Data Science, and Beyond

<https://www.kdnuggets.com/2015/08/rightrelevance-topics-influencers-big-data-science-data-mining.html>

### Relevant KDnuggets tags:

-   /tag/influencers

<https://www.kdnuggets.com/tag/influencers>

-   /tag/big-data-influencers

<https://www.kdnuggets.com/tag/big-data-influencers>

For a more in-depth analysis, see technical articles below:

-   Quora: What is a good measure of the influence of a Twitter user?

<https://www.quora.com/What-is-a-good-measure-of-the-influence-of-a-Twitter-user>

-   Measuring User Influence in Twitter: The Million Follower Fallacy,
    AAAI, 2010

<https://www.aaai.org/ocs/index.php/ICWSM/ICWSM10/paper/viewFile/1538/1826>

-   Measuring user influence on Twitter: A survey, arXiv, 2015

<https://arxiv.org/abs/1508.07951>

-   Measuring Influence on Twitter, I. Anger and C. Kittl

<http://www.l2f.inesc-id.pt/~fmmb/wiki/uploads/Work/misnis.ref07.pdf>

-   A Data Scientist Explains How To Maximize Your Influence On Twitter,
    Business Insider, 2014

<http://www.businessinsider.com/how-to-maximize-your-influence-on-twitter-2014-1>

## Related:

-   17 More Must-Know Data Science Interview Questions and Answers

<https://www.kdnuggets.com/2017/02/17-data-science-interview-questions-answers.html>

-   17 More Must-Know Data Science Interview Questions and Answers, Part
    2

<https://www.kdnuggets.com/2017/02/17-data-science-interview-questions-answers-part-2.html>

-   21 Must-Know Data Science Interview Questions and Answers

<https://www.kdnuggets.com/2016/02/21-data-science-interview-questions-answers.html>

-   21 Must-Know Data Science Interview Questions and Answers, part 2

<https://www.kdnuggets.com/2016/02/21-data-science-interview-questions-answers-part2.html>
