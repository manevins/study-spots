# A/B Test Plan — Study Space IC

**Status:** Written and committed on November 24, 2026, before collecting any test data. This is later than the handout's required November 9 plan deadline and November 17 launch deadline. The dates are disclosed rather than backdated. Ask the instructor whether a late-start test can still receive credit.

## Page and single element
- **Page:** Homepage, `index.html`.
- **Version A (control):** Current headline: “Your Colorful & Fresh Guide to the Best Workspaces and Coffee Shops around Iowa City”.
- **Version B (variant):** “Find the Best Places to Study in Iowa City”.
- **Only tested change:** The one-line headline below the site name. No other visible content or design element is intentionally changed. Version B is a noindex test copy with a canonical tag to Version A and is excluded from the sitemap to protect search rankings.

## Hypothesis and rationale
I predict Version B will receive a higher average usefulness rating than Version A because it states the site's core benefit and Iowa City topic more directly. A student arriving with a study-location need may understand the page's purpose faster from a concrete, keyword-aligned headline than from the more decorative “Colorful & Fresh Guide” wording. This prediction could be wrong: the original headline may feel more welcoming or communicate a broader range of workspaces.

## Visitors, model, and persona
- **Model:** GPT-6, using the same model selection and settings for every trial. Record the exact model label/settings visible at the time each batch is run.
- **Persona:** An undergraduate University of Iowa student who sometimes studies on campus and sometimes in Iowa City cafes. They want a practical place to work between classes or during a longer study block, care about understanding what the site offers, and have not seen this website before.
- **Freshness:** Each trial must be run in a fresh conversation with no memory of earlier trials. Do not reuse a conversation.

## Exact prompt
Use the exact text in `ab-test-prompt.txt` for every trial. Only replace the page-text placeholder with the complete text for the assigned version. Keep the model and settings unchanged.

## Assignment and sample
- **Target sample:** 100 completed trials: 50 assigned to A and 50 assigned to B.
- **Assignment:** Use the pre-generated randomized order in `ab-test-data-template.csv`. Keep the assignment fixed; do not re-randomize after seeing outcomes.
- **Collection:** Complete all 100 trials before analyzing the results. Do not stop early because one version appears to be winning. Record every response, including unusual or unfavorable responses.
- **Timing:** The plan was committed late on November 24, 2026. Complete collection in batches over the remaining days before the December 1 site freeze, if the instructor permits the late start. Record the actual date of every batch. Do not claim the original November 17 launch date.

## Primary outcome and analysis
The primary outcome is a single **usefulness rating from 1 to 7**, where 1 means “not useful at all” and 7 means “extremely useful.” The visitor must also provide one brief reason, but that reason is qualitative context and is not a second outcome.

After all 100 trials, calculate the mean and standard deviation for A and B, and the difference in means (B minus A). Use a two-sided Welch independent-samples t-test at alpha = .05. Report the p-value and an effect-size estimate, and interpret the practical size of the difference rather than treating statistical significance as the only consideration. A result near zero is a valid finding.

## Decision rule
The hypothesis is supported only if B's average usefulness rating is higher than A's and the pre-specified two-sided test indicates a difference at p < .05. If not, report that the test did not provide evidence that B is better. Do not change this rule after viewing the data.

## Limitations
These are AI-simulated evaluations, not observations of actual student behavior. The test can compare how a consistent model responds to two tightly controlled versions under the stated prompt. It cannot establish actual click-through rates, search rankings, time on page, real student preferences, or whether a real visitor would choose a location. A sample of 100 AI evaluations may also be too small to detect a modest difference. Report the model, settings, dates, all raw outputs, and any deviations.
