# GOV.UK Speedcurve LUX JS Monitor

This is the repo for a Concourse job which checks that the version of the [SpeedCurve LUX] JavaScript we've embedded into GOV.UK matches the latest version. SpeedCurve LUX is a tool that monitors how quickly pages load, we're [embedding the script ourselves][self-host] for security reasons.

[SpeedCurve LUX]: https://speedcurve.com/features/lux/
[self-host]: https://support.speedcurve.com/en/articles/3378439-can-lux-js-be-self-hosted

## If the job fails

If the job fails, that likely means that a new version of the JavaScript has been released and we need to update the version we've embedded. Once the embedded version of the script has been deployed, we can [update the expected version in this job to the latest version][version].

[version]: https://github.com/alphagov/govuk-speedcurve-lux-js-monitor/blob/87b705adc60a4091e94c39817848a110ac7f2cb8/concourse.yml#L51

## Deploying the job

Changes should be picked up automatically, but if that doesn't happen the job can be deployed manually:

```sh
$ fly -t govuk set-pipeline --pipeline govuk-speedcurve-lux-js-monitor --config concourse.yml
```
