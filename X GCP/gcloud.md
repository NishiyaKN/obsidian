`gcloud auth list` - list active account name
`gcloud config list project` - list prject ID
`gcloud compute project-info describe --project $(gcloud config get-value project)` - details about the project

`gcloud config set compute/region europe-west1` - set project region
`gcloud config set compute/zone europe-west1b` - set project zone
`gcloud config get-value compute/region` - get project region
`gcloud config get-value compute/zone` - get project zone

`export REGION=europe-west1` - set region env
`export ZONE=europe-west1-b` - set zone env
`export ZONE=$(gcloud config get-value compute/zone)` - set zone env that is setted
`export PROJECT_ID=$(gcloud config get-value project)` - set pid env

`gcloud compute instances create gcelab2 --machine-type e2-medium --zone=$ZONE` - create a VM
`gcloud compute instances delete --keep-disks` - delete VM but keep disks
`gcloud compute ssh gcelab2 --zone=europe-west1-b` - ssh to VM
`gcloud compute instances list` - list VMs
`gcloud compute instances list --filter="name=('gcelab2')"` VM by name
###### Cloud Storage
`gcloud storage buckets create gs://<YOUR-BUCKET-NAME>` create a bucket
`gcloud storage cp ada.jpg gs://YOUR-BUCKET-NAME` copy local file to bucket
`gcloud storage ls gs://YOUR-BUCKET-NAME` ls the bucket
`gsutil acl ch -u AllUsers:R gs://YOUR-BUCKET-NAME/ada.jpg` make the file accessible to all
`gsutil acl ch -d AllUsers gs://YOUR-BUCKET-NAME/ada.jpg` remove access to all
###### Firewall
`gcloud compute firewall-rules list` - list firewall
`gcloud compute firewall-rules create fw-be \
    --allow tcp:8081-8082 \
    --target-tags=backend`
	