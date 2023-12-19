# Storage

## Possible Type of Question

- Create a new PersistentVolume named my-pv. It should have a capacity of 1Gi, accessMode ReadWriteOnce, hostPath /mnt/data and no storageClassName defined.

- Next create a new PersistentVolumeClaim in Namespace development named my-pvc-claim . It should request 2Gi storage, accessMode ReadWriteOnce and should not define a storageClassName. The PVC should bound to the PV correctly.

- Finally create a new Deployment my-deployment in Namespace development which mounts that volume at /tmp/my-data. The Pods of that Deployment should be of image httpd:2.4.41-alpine.

Tips

Copy PV and PVC manifest examples from

For Deployment ```kubectl create deployment my-deployment -n development --image=httpd:2.4.41-alpine --dry-run=client -o yaml > deployment.yaml```

Then edit deployment to mount pvc. See

## Links


- [Claim as Volumes Example](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#claims-as-volumes)
- [Kubernetes Docs PV/PVC](https://kubernetes.io/docs/concepts/storage/persistent-volumes/)
- [Example of host path type Volume](https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/#create-a-persistentvolume)