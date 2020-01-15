# Sysdig Monitoring Kubernetes Installation

You can use the [helm chart](https://github.com/helm/charts/tree/master/stable/sysdig) to install sysdig into your kubernetes cluster. You can download the chart by using the command

`helm fetch stable/sysdig --untar`

This command simply downloads sysdig chart as tar then unzip it into your current directory. Now, it has some default settings that you might need to change especiall the access key. To avoid changing the default value, lets overwrite with our own values instead. To that, we make a file called **values-dev.yaml**

```yaml
sysdig:
  accessKey: "1234-5678-18992"
  settings:
    prometheus:
      enabled: false
      histograms: true
      max_metrics: 2000
      max_metrics_per_process: 400
```

Now, you can either install into the cluster directing using helm via

```yaml
helm install --name sysdig-monitor sysdig/ -n monitoring -f sysdig/values-dev.yaml 
```

or something like

```yaml
helm template sysdig-monitor sysdig/ -n monitoring -f sysdig/values-dev.yaml | kubectl apply -n monitoring -f -
```

to pass the manifest directly to kubectl.

Note, you have the option to enable **Sysdig Secure** in your cluster by enabling it in the values.yaml