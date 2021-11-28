/etc/eks/bootstrap.sh eks --kubelet-extra-args '--node-labels=eks.amazonaws.com/nodegroup-image=ami-00836a7940260f6dd,eks.amazonaws.com/capacityType=ON_DEMAND,eks.amazonaws.com/nodegroup=node1 --max-pods=12' --b64-cluster-ca $B64_CLUSTER_CA --apiserver-endpoint $API_SERVER_URL --dns-cluster-ip $K8S_CLUSTER_DNS_IP --use-max-pods true

sed -i s/'KUBELET_EXTRA_ARGS'/'KUBELET_EXTRA_ARGS --fail-swap-on=false'/g /etc/eks/containerd/kubelet-containerd.service /etc/systemd/system/kubelet.service
systemctl daemon-reload
systemctl restart kubelet
sudo su
mkswap /dev/sdb
swapon /dev/sdb
