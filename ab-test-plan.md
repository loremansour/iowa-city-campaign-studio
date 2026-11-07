# A/B Test Plan — Iowa City Campaign Studio

## Page and change

I will test the main headline on the Iowa City Campaign Studio homepage.

- Version A (current): “A clear goal. / A campaign with direction.”
- Version B (proposed): “Marketing campaigns / for Iowa City small businesses.”

The slash marks a line break. The headline is the only element I will change. The description, layout, and “Explore campaign services” button will stay the same. I will publish Version B with a `noindex` tag and leave it out of the sitemap.

## Hypothesis

I predict that a higher percentage of simulated Iowa City small business owners will say they would click “Explore campaign services” after seeing Version B. The new headline names the service, location, and audience up front, which may help owners comparing local providers decide whether the studio is relevant to them.

## Model and exact prompt

I will use Anthropic’s Claude Opus 5.5 with the same settings for all 100 trials. Each trial will start in a fresh chat with no memory of previous trials. I will paste the full visible homepage text for the assigned version in the same format each time. The model will see only one version per trial.

> You own a small business in Iowa City and are comparing local marketing providers to help launch a new service. Read the homepage below. Imagine this is a real business you found during your search. Based on this page, would you click the “Explore campaign services” button to learn more? Start your answer with Yes or No, then give one sentence explaining your decision.
>
> [Insert the full homepage text for the assigned version here.]

## Random assignment and sample size

Before running any trials, I will create a list with 50 A assignments and 50 B assignments, shuffle it using a random number generator, and save the order. I will run all 100 trials in that order and expect to finish by November 20, 2026. I will save the assigned version and full response for every trial.

## Primary outcome and analysis

The primary outcome is the percentage of trials in each version that start with an explicit “Yes.” I will keep and flag any response that does not start with a clear Yes or No and count it as a non-Yes in the primary analysis.

After all 100 trials, I will compare the Yes percentages, report the difference in percentage points (B minus A), and use a one-sided Fisher’s exact test. A higher Yes percentage for B with a p-value below 0.05 will count as support for my hypothesis. The test measures what simulated visitors say they would do.
