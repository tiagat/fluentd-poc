docker build . --tag tiagat/fluentd:X.X.X




## Testing 

### Basic Usage


```bash
# Post a record with the tag "studio.log"
$ curl -u fluentd:password -X POST -d 'json={"message":"OK"}' http://localhost:9880/studio.log
```


### Apache Bench
```bash
$ echo "json={\"message\":\"OK\"}" > test.json 
$ ab -c 10 -n 1000 -p test.json -A fluentd:password -T application/x-www-form-urlencoded http://localhost:9880/
```
