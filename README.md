### Helm Practise Example helm-kubernetes-packaging-manager-for-developers-and-devops

Udemy Course-> https://xebia.udemy.com/course/helm-kubernetes-packaging-manager-for-developers-and-devops

1. For any helm updates visit the https://helm.sh/docs/ site
2. For all bitnami repository charts visit the https://bitnami.com/stacks/helm
3. If you are looking for source code referred in chart visit https://github.com/bitnami/charts/tree/main/bitnami
4. For installing helm on windows use command "choco install kubernetes-helm"
5. For helm command list kindly referrer the helm+install+commands.txt in this project root directory
   [helm+install+commands.txt](helm%2Binstall%2Bcommands.txt)


### Create local chart repository
1) create a folder chartsrepo
2) --- helm repo index chartsrepo/
The above command will create index.yaml inside chartsrepo folder
3) Package any local chart to the folder chartsrepo
   --- helm package helm/firstchart -d chartsrepo/
4) Now add the newly added chart in index.yaml using following command
   --- helm repo index .


docker run -d -p 5000:5000 --restart always --name registry registry:2

Push chart to oci registry
helm push myappchart-0.1.0.tgz oci://localhost:5000
helm show all oci://localhost:5000/myappchart --version 0.1.0
helm pull oci://localhost:5000/myappchart --version 0.1.0
helm template oci://localhost:5000/myappchart --version 0.1.0
helm install oci://localhost:5000/myappchart --version 0.1.0 --generate-name

On Docker hub

helm push myapp3chart-0.1.0.tgz oci://registry-1.docker.io/amsidhmicroservice
helm show all oci://registry-1.docker.io/amsidhmicroservice/myappchart --version 0.1.0
helm template oci://registry-1.docker.io/amsidhmicroservice/myapp2chart --version 0.1.0
helm show all oci://registry-1.docker.io/amsidhmicroservice/myappchart
