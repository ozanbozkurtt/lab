# Kubernetes Lab Repository

Bu repo Kubernetes öğrenme ve geliştirme süreçlerinde kullanılacak temel bileşenleri içerir.

## 📁 Klasör Yapısı

```
lab/
├── Pods/                    # Tekil pod tanımları
│   ├── nginx.yml
│   ├── redis.yml
│   └── postgres.yml
├── Deployments/             # Deployment tanımları
│   ├── web-app.yml
│   ├── api-service.yml
│   └── database.yml
├── Services/                # Service tanımları
│   ├── clusterip.yml
│   ├── nodeport.yml
│   └── loadbalancer.yml
├── ConfigMaps/              # Konfigürasyon dosyaları
│   ├── app-config.yml
│   └── nginx-config.yml
├── Secrets/                 # Gizli bilgiler
│   ├── database-secret.yml
│   └── api-keys.yml
├── PersistentVolumes/       # Kalıcı depolama
│   ├── pv.yml
│   └── pvc.yml
├── Namespaces/              # Namespace tanımları
│   ├── development.yml
│   └── production.yml
├── RBAC/                    # Yetkilendirme
│   ├── roles.yml
│   ├── rolebindings.yml
│   └── serviceaccounts.yml
├── Ingress/                 # Ingress kuralları
│   ├── web-ingress.yml
│   └── api-ingress.yml
├── HPA/                     # Horizontal Pod Autoscaler
│   └── web-app-hpa.yml
├── Jobs/                    # Job ve CronJob
│   ├── backup-job.yml
│   └── cleanup-cronjob.yml
├── NetworkPolicies/         # Ağ güvenliği
│   └── default-deny.yml
├── StorageClasses/          # Depolama sınıfları
│   └── fast-storage.yml
└── Examples/                # Örnek uygulamalar
    ├── wordpress/
    ├── microservices/
    └── monitoring/
```

## 🚀 Mutlaka Olması Gerekenler

### 1. **Temel Bileşenler**
- [ ] Pod tanımları (nginx, redis, postgres vb.)
- [ ] Deployment örnekleri
- [ ] Service tanımları (ClusterIP, NodePort, LoadBalancer)
- [ ] ConfigMap ve Secret örnekleri

### 2. **Güvenlik**
- [ ] RBAC (Role, RoleBinding, ServiceAccount)
- [ ] NetworkPolicy örnekleri
- [ ] SecurityContext tanımları
- [ ] Pod Security Standards

### 3. **Depolama**
- [ ] PersistentVolume ve PersistentVolumeClaim
- [ ] StorageClass tanımları
- [ ] Volume mount örnekleri

### 4. **Ağ ve Erişim**
- [ ] Ingress kuralları
- [ ] Service mesh örnekleri (istio/linkerd)
- [ ] Load balancing stratejileri

### 5. **Ölçeklendirme ve Otomasyon**
- [ ] Horizontal Pod Autoscaler (HPA)
- [ ] Vertical Pod Autoscaler (VPA)
- [ ] Job ve CronJob örnekleri

### 6. **Monitoring ve Logging**
- [ ] Prometheus deployment
- [ ] Grafana dashboard
- [ ] ELK stack (Elasticsearch, Logstash, Kibana)
- [ ] Fluentd/Fluent Bit

### 7. **CI/CD**
- [ ] Tekton pipeline örnekleri
- [ ] ArgoCD application tanımları
- [ ] Helm chart örnekleri

### 8. **Troubleshooting**
- [ ] Debug pod'ları
- [ ] Network troubleshooting araçları
- [ ] Monitoring ve logging araçları

## 📝 Kullanım

```bash
# Tüm kaynakları uygula
kubectl apply -f .

# Belirli bir klasördeki kaynakları uygula
kubectl apply -f Pods/

# Kaynakları sil
kubectl delete -f .

# Durumu kontrol et
kubectl get all
```

## 🔧 Geliştirme İpuçları

1. **Namespace kullanın** - Geliştirme ve production için ayrı namespace'ler
2. **Resource limits belirleyin** - CPU ve memory sınırları koyun
3. **Health check ekleyin** - Liveness ve readiness probe'ları
4. **Security context kullanın** - Pod güvenliği için
5. **Network policy uygulayın** - Pod'lar arası iletişimi kısıtlayın

## 📚 Faydalı Komutlar

```bash
# Pod loglarını görüntüle
kubectl logs <pod-name>

# Pod'a bağlan
kubectl exec -it <pod-name> -- /bin/bash

# Service port forward
kubectl port-forward svc/<service-name> 8080:80

# Resource kullanımını görüntüle
kubectl top pods

# Event'leri görüntüle
kubectl get events --sort-by='.lastTimestamp'
```
