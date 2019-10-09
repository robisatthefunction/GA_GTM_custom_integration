Create a custom analytics extension with this, update it to the right custom dimensions
And then add the custom events in the account

#GA GTM custom integrationLog

This GA GTM custom integration makes it possible to integrate Optimizely with GA via GTM easily, and makes it easy to debug any data discrepancies that might occur.

Implementation steps:

Copy the JSON from this repo
Create a custom analytics integration: https://help.optimizely.com/Integrate_Other_Platforms/Custom_analytics_integrations_in_Optimizely_X
Create custom dimensions in GA for Optimizely experiments, each experiment that is running at the same time needs it’s own custom dimension.
Adjust the custom analytics integration to use your own defined custom dimensions.
Create the following custom events under Implementation>Events:

I. aa_test_activated

II. set_ga_event

III. sent_ga_event

IV. failed_to_find_ga

V. ga_error

Set up an A/A test to test the integration:

I. Create an experiment that runs on all pages, so you can check GA and Optimizely on your complete website.

II. Add the integration to the experiment.

III. Set up the following metrics:
  a. aa_test_activated: total conversions per visitor
  b. set_ga_event: unique conversions per visitor
  c. sent_ga_event: unique conversions per visitor
  d. sent_ga_event: total value per conversion
  e. failed_to_find_ga: unique conversions per visitor f. failed_to_find_ga: total conversions per visitor g. ga_error: unique conversions per visitor

IV. Run the A/A test for everyone (no audience), set the traffic allocation to 10% (no need to run it for all visitors). We recommend to run an A/A test for 1 week, to take out any fluctuations in traffic you have during the week. Do not make changes to the experiment once it has started, if you do notice an error after it has started, you need to duplicate the experiment and run the A/A test from the start again.

V. Compare GA and Optimizely numbers, using this google sheet (link to be added).
