# noobaa-replication

This repository contains the files to set up Noobaa bucket replication across three OpenShift Clusters using bucket replication and namespace stores.

![noobaa-bkt-replication](./noobaa-bkt-repl.png)


# Get the replication status from noobaa-core-0
oc logs noobaa-core-0 -n openshift-storage | grep "replication" | tail -10

# Check noobaa for any errors:
oc logs noobaa-core-0 -n openshift-storage --tail=200 | grep -iE "error|warn|exception|reject"

# Upload file:
aws s3 --endpoint-url http://<s3endPoint> --profile <profileName> cp <fileName> s3://<bucketName>
