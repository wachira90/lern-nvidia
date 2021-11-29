## download pub key

https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1404/x86_64/7fa2af80.pub


## on root user
## a) For Ubuntu distributions
````
cat 7fa2af80.pub | apt-key add -
````
## b) For Fedora, RHEL and SUSE distributions
````
rpm --import 7fa2af80.pub
````

### At a future date, CUDA packages will begin removing the old public key with ID 5C37D3BE. If you are only using the newly signed repositories, it is safe to remove the old key manually by running, as root:
## a) For Ubuntu distributions
````
apt-key del 5C37D3BE
````
## b) For Fedora, RHEL and SUSE distributions
````
rpm -e gpg-pubkey-5c37d3be
````
