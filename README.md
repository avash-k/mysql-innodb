A) Check that "kubectl" Client is running in your Local, else install from https://kubernetes.io/docs/tasks/tools/install-kubectl/

B) Go to cloud.ibm.com 

C) Follow the Steps in file "IBM-Cloud-IKS-Install&Configure" to Setup IKS 

D) Verify the Setup
   < kubectl version >
   < kubectl cluster-info >

E) Check that "helm" Client is running in your Local, else install from https://helm.sh/docs/intro/install/

F) Verify the Setup
   < helm version >

G) Check Git is installed in your Local else install from https://git-scm.com/book/en/v2/Getting-Started-Installing-Git/

H) Clone the Git Repo:
   < git clone  avash-k/mysql-innodb && cd mysql-innodb >

I) Create a namespace "mysql"
   < kubectl create ns mysql >

J) Install mysql-operator using Helm Chart
   < helm install mysql-innodb-operator --name mysql-innodb-operator >

K) Create the configmap for Innodb cluster
   < kubectl create -f innodb-mycnf.yaml >

L) Create root user password for Innodb cluster
   < kubectl create secret generic root-password --from-literal=password=foobar -n mysql >

M) Check if any storage class is present else create one using this link https://kubernetes.io/docs/concepts/storage/storage-classes/

N) Create the Innodb Cluster
   < kubectl create -f innodb-cluster.yaml >

 



