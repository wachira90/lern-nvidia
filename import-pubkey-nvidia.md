### error message

````
Reading package lists... Done                                               
W: GPG error: https://developer.download.nvidia.com/compute/cuda/repos/debian10/x86_64  Release: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY F60F4B3D7FA2AF80
E: The repository 'https://developer.download.nvidia.com/compute/cuda/repos/debian10/x86_64  Release' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
````

## download pub key
````
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1404/x86_64/7fa2af80.pub
````

### check infile 
````
root@test-imac:~# cat 7fa2af80.pub 
-----BEGIN PGP PUBLIC KEY BLOCK-----
Version: GnuPG v1

mQINBFdtt4UBEAC8FDSWMR07GJZ265giLn7kLF+EsJCWESUq6Cd13QN0JQ/tLibi
QlW4ZjeOnEH9VPlqh/mKqNMG4SwRt8S+GHpePMQrr0aOkiRGfCclnAWIZURSAP+t
PLelCt43fkw1BBTopd/0oOzO8kHu8j8WU4A8GHxqghfFWPv54FQs2iaZ2eWR7a6d
79IJrbDKaVCCiQrkhCM8m648pNKHhuoJ9cQXFV+uvwkpfmKWGQ4ultxlOyjLHJLF
vuML2RuAO9IxbdZjzeYNN+T+wjFIBVcPnwEO+WrYgvGkT4r9aqVqTeg3EPb7QclV
sKBVJdxk4jZl0y22HAWqScVi6SJ15uK9pXxywDZkbpuRBWx4ThWiGe/FiUa2igi9
/SIvqN2TBY0g18sRTrylVr1wE1UGa/y7nDx6PoGCP1frBt8YUYt3pkM8Xvb2CRxx
CyWwmuFEQHC6jCEWf7FnoBHBYQwTVGNrU0vkuIeDrm+ZAcv8wx+ie1hlFhqCCJnf
jqeQ0/zA9RPmCPOkLyTdSsNZtlxxk7bzCdTdFFKzBjGTR7Gz3SMSp23d11eIyRiF
HQsp2v0SvnPJ6OcgB95Hmo544vi3RuoVfovtDOdfSBCRxP+GhhxkKSrTleQjD0/r
CGkdG2Kox3m9YllAsvZchLXlS7bZV9mGRF61mVMjF3HJRUQfBBm89VPQ+QARAQAB
tCBjdWRhdG9vbHMgPGN1ZGF0b29sc0BudmlkaWEuY29tPokCNwQTAQgAIQUCV223
hQIbAwULCQgHAwUVCgkICwUWAgMBAAIeAQIXgAAKCRD2D0s9f6KvgNArEAChnfcW
rYItgt7xXXubT6E+KpJyJ0RPrXf51S2mhciFbjDl+3EXRMRjOutVmgWYPWUUZaKR
8Iez3Lz4BRmwYOWBLtdnOLbKoSsQUX95rnPFjfly/DFLfjKxz4NRBmh4r4/rCYWm
2hmnXmOAi8kV7fqx3g5XMpJ//N6+T8ctEol2iZ82GrXjadcRWE4rAe7UyuEzJ74y
6ZKIzk5ijdgEKtcaBhzEWvoV5Pr9nkn7ByGsdehKR/gNnjPMYXrklSHGfphJIsS2
S32lMk/kuRjihBcWcYBXIPEQ7CV+PNW2TlkZj/YqTg637sZHwkhcjcNzxeqKvRYG
8V7Ju5hTDxL1UQBmgDS3cRx1lw7tYRG5bS67tbC2dc/CpPkG5agiZ/WyoHQDnn4r
1fRuOFx694QR6+0rAP6171xEEoNAPaH7gdJdhWKiYiJD0T2EEbW7wBUi/EupeKRv
kR12R1jUa1mlpxNtWQxJ7qp98T9+DmkxI1XDmWx0/g4ryuicwLDSqoPgNcRNdSQb
b8YfTqrkqaDdYzwLr/n0YKW3cYIvIeisV0WxRjb6OP7oAlAtaAhImlIc//51qNO7
/WAud6qMtnhFoZayR/BzLKqnCioN5GYr9BAKskpPHe9cDKVS3fg+Qvc1sNJID+jf
k52PqyW24Qsr0A9+5zQyE4tH9dfv120gj9avmg==
=0nKc
-----END PGP PUBLIC KEY BLOCK-----
root@test-imac:~#
````

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
