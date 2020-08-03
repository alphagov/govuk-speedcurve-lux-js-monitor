# govuk-speedcurve-lux-js-monitor

Concourse job for monitoring our embedded Speedcurve LUX.js.

## Deploying

Changes should be picked up automatically, but if that doesn't happen the job can be deployed manually:

```sh
$ fly -t govuk set-pipeline --pipeline govuk-speedcurve-lux-js-monitor --config concourse.yml
```
