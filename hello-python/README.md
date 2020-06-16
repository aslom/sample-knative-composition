Based on https://github.com/knative/docs/tree/master/docs/serving/samples/hello-world/helloworld-python

Local testing

```
pip3 install -r requirements.txt
./app.py
```

Build Docker container

```
docker build -t {username}/hello-python .
docker push {username}/hello-python
```


```shell
kubectl apply --filename ksvc.yaml
```


TODO: deploymnt as ksvc and regular service+deployment

