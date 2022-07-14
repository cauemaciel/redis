# redis
redis




helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
#helm show values bitnami/redis >> values.yaml (Opcional) # Alterar parametros necessários

helm upgrade -i redis-enviromentname-production \
--set replica.replicaCount=0 \
--set auth.enabled=false \
--set master.persistence.enabled=false \
--set replica.persistence.enabled=false \
bitnami/redis -n serpro-production

helm upgrade -i redis-enviromentname-homolog-01 \
--set architecture=standalone \
--set auth.enabled=false \
--set master.persistence.enabled=false \ 
bitnami/redis -n serpro-homolog \

helm upgrade -i redis-enviromentname-homolog-02 --set architecture=standalone --set auth.enabled=false --set master.persistence.enabled=false  bitnami/redis -n enviromentname-homolog
