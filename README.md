# cfcharts
Crowdfox maintained public Helm charts.


## Usage

```
helm repo add crowdfox https://crowdfoxgmbh.github.io/cfcharts/
# now you can install any chart by running e.g:
helm install crowdfox/external-service-operator
```


## Adding Charts

When you want to add charts, create a PR and add the chart to the charts directory.
After you have done so, you have to package that folder via

```
tar -C charts -zvcf .cr-release-packages/external-service-operator-0.0.1.tgz external-service-operator
```

After you have done so, you can upload that package as release.
Therefore you need a Token with "repo" rights which you can get [here](https://help.github.com/en/articles/creating-a-personal-access-token-for-the-command-line)

```
./cr upload --config config.yaml -t <your token>
```

Now we have to update the index file:

```
./cr index --config config.yaml
```

When this PR now gets merged, the new Chart(version) should be available.

## Links

* https://github.com/helm/chart-releaser used to release this chart hosted at Github. (the  cr executeable in this repo)
* https://github.com/helm/chart-releaser/tree/polish-readme Useful Readme not yet in the master of the chart.
