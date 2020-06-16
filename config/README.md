# Sample Knative composition of analytiics for workflow events


Example analytics is aggreagting events to determine how long activities take and generats alert if workflow takes longer than 10 days from Receive.

We start with analytics 

```sh
kubectl apply -f 100-aggregate-analytics.yaml
```

Combine analytic with alert - output from analytics is used ot send alert:

```
200-send-alert.yaml
201-analytics-sequence.yaml
```

Add storing events in data lake in paralle to calling event analytics. In case events can not be processed send them to event audit service using deadLetterSink:

```
300-store-event-in-data-lake.yaml
301-event-audit.yaml
302-analytics-parallel.yaml
```


Now add front filtering of events and dynamic routing.

```
400-event-supported-analytics-v1-filter.yaml
401-event-supported-in-new-analytics-filter.yaml
402-router-parallel.yaml
403-summary-analyics-alert-pipelinexx.yaml
410-loan-events-filter.yaml
411-router-sequence.yaml
```


Finally combined router-sequence.yaml and analytics-parallel into loan-app-sequence:

```
500-loan-app-sequence.yaml
```
