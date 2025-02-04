# Deploy GKE with terraform

# Create Compute Engine ubuntu for NFS


# Install nfs

```
sudo apt install nfs-kernel-server
sudo nano /etc/exports


/data-k8s/minio    10.128.0.22(rw,sync,no_subtree_check)
/data-k8s/wordpress    10.128.0.22(rw,sync,no_subtree_check)
/data-k8s/mysql    10.128.0.22(rw,sync,no_subtree_check)

/data-k8s/minio    10.128.0.21(rw,sync,no_subtree_check)
/data-k8s/wordpress    10.128.0.21(rw,sync,no_subtree_check)
/data-k8s/mysql    10.128.0.21(rw,sync,no_subtree_check)

/data-k8s/minio    10.128.0.20(rw,sync,no_subtree_check)
/data-k8s/wordpress    10.128.0.20(rw,sync,no_subtree_check)
/data-k8s/mysql    10.128.0.20(rw,sync,no_subtree_check)
```

# install ingress

# Add SSL from file from zero ssl

```
cat dev.anakdevops.online/certificate.crt dev.anakdevops.online/ca_bundle.crt > dev.anakdevops.online/gabung.crt
kubectl create secret tls my-tls-secret --cert=dev.anakdevops.online/gabung.crt --key=dev.anakdevops.online/private.key


kubectl create secret tls my-tls-secret --cert=dev.anakdevops.online/gabung.crt --key=dev.anakdevops.online/private.key --dry-run=client -o yaml > dev-wp-nginx/templates/secret-ssl.yaml

```
