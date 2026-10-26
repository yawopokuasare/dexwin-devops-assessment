after runnung scripts/doctor.sh i found that the pods had failed due to readiness and liveness checks that were not configured. 

i checked kubernetes/service.yaml and found that targetPod was set to 8081 instead of 8080 in the application listening port. 

also the app in spec in the service.yaml file was set to customer-service instead of customer-api which is what the pod was set to.

the deployment.yaml had some misconfigurations in readiness probe. it has been changed from /ready in order to avoid the error 404 issue.
the  was 

