## Prompts to 'kubectl-ai' to Generate K8S Manifests

### System Prompt
I want you to act as a senior DevOps and site reliability engineer who is proficient with Kubernetes, Helm, ArgoCD, Terraform, AWS, GCP, Linux, Bash, Python and other role-specific tools. I will ask you to generate a K8S manifest according to my request and information provided. Do not try to apply generated manifest - I want to get YAML output only. Apply image tags as specified - don't verify if such tag actually exists.


| NAME | PROMPT | DESCRIPTION | EXAMPLE |
| ---- | ------ | ----------- | ------- |
|app|Request: create a pod using Nginx image of version "1.29.3" with port 8080.|Simple pod|[app.yml](./manifests/app-cron_job.yml)|
|app with liveness probe|Request: create a pod using Nginx image of version "1.29.3" with port 8080 and liveness probe on the same port. Path for the probe: '/'.|Pod with liveness probe.|[app-liveness_probe.yml](./manifests/app-liveness_probe.yml)|
|app with readiness probe|Request: create a pod using Nginx image of version "1.29.3" with port 80 and liveness and readiness probes on the same port. Path for the probe: '/'.|Pod with liveness and readiness probes|[app-readiness_probe.yml](./manifests/app-readiness_probe.yml)|
|app with volume mount|Request: create a pod using Nginx image of version "1.29.3" with port 80 and liveness and readyness probes on the same port. Path for the probe: '/'. Add volume mount of 'hostPath' type. Path on the host: /tmp/workdir; path to mount inside container: /workdir.|Pod with 'hostPath' volume mount|[app-volume_mount.yml](./manifests/app-volume_mount.yml)|
|cron-job|Request: cron job that runs every hour and executes command `df -h`|Cron job|[app-cron_job.yml](./manifests/app-cron_job.yml)|
|app-multicontainer|Request: multicontainer pod|Pod with more than one container|[app-multicontainer.yml](./manifests/app-multicontainer.yml)|
|app with resources|Requests: pod with requests and limits|Pod with resource requests and limites set up|[app-resources.yml](./manifests/app-resources.yml)|
|app with secret mount|Request: pod with "secret" volume mount.|Secret mounted as a volume|[app-secret.yml](./manifests/app-secret.yml)|
