---
---
[HOME](index.md)
[ABOUT](README.md)
[WEB](https://osp4diss.vlsm.org/)
[GITHUB](https://github.com/UI-FASILKOM-OS/osp4diss/)
[TOP](#)
[BOTTOM](#endofpage)
[PREV](CBKadal.md)
[NEXT](index.md)

# Eg. User: cbkadal (2)

These following examples is for user **cbkadal** of guest *osp*.
Replace **cbkadal** with your own user name.

```
cbkadal@badak:~$ gpg2 --gen-key
gpg (GnuPG) 2.0.26; Copyright (C) 2013 Free Software Foundation, Inc.
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Please select what kind of key you want:
   (1) RSA and RSA (default)
   (2) DSA and Elgamal
   (3) DSA (sign only)
   (4) RSA (sign only)
Your selection? 1
RSA keys may be between 1024 and 4096 bits long.
What keysize do you want? (2048) 4096
Requested keysize is 4096 bits
Please specify how long the key should be valid.
         0 = key does not expire
      <n>  = key expires in n days
      <n>w = key expires in n weeks
      <n>m = key expires in n months
      <n>y = key expires in n years
Key is valid for? (0) 1y
Key expires at Tue 28 Sep 2021 05:41:04 PM WIB
Is this correct? (y/N) y

GnuPG needs to construct a user ID to identify your key.

Real name: Cicak Bin Kadal
Email address: cbk@dummy
Comment: CBK
You selected this USER-ID:
    "Cicak Bin Kadal (CBK) <cbk@dummy>"

Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit? o
You need a Passphrase to protect your secret key.

Enter passphrase

Passphrase: 
Warning: You have entered an insecure passphrase.
A passphrase should be at least 8 characters long.
  Take this one anyway
  Enter new passphrase
[te]? t
Warning: You have entered an insecure passphrase.
A passphrase should contain at least 1 digit or
special character.
  Take this one anyway
  Enter new passphrase
[te]? t
You have not entered a passphrase - this is in general a bad idea!
Please confirm that you do not want to have any protection on your key.
  Yes, protection is not needed
  Enter new passphrase
[ye]? y
Please re-enter this passphrase
Passphrase: 
You don't want a passphrase - this is probably a *bad* idea!
I will do it anyway.  You can change your passphrase at any time,
using this program with the option "--edit-key".

We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
gpg: /home/demo/.gnupg/trustdb.gpg: trustdb created
gpg: key 097E273A marked as ultimately trusted
public and secret key created and signed.

gpg: checking the trustdb
gpg: 3 marginal(s) needed, 1 complete(s) needed, PGP trust model
gpg: depth: 0  valid:   1  signed:   0  trust: 0-, 0q, 0n, 0m, 0f, 1u
gpg: next trustdb check due at 2021-09-28
pub   4096R/097E273A 2020-09-28 [expires: 2021-09-28]
      Key fingerprint = DD9C C4EC 797B 2027 92B0  9BA9 6B0E E9B6 097E 273A
uid       [ultimate] Cicak Bin Kadal (CBK) <cbk@dummy>
sub   4096R/77021270 2020-09-28 [expires: 2021-09-28]

cbkadal@badak:~$
```
```
cbkadal@badak:~$ gpg2 --list-keys
/home/demo/.gnupg/pubring.gpg
-----------------------------
pub   4096R/097E273A 2020-09-28 [expires: 2021-09-28]
uid       [ultimate] Cicak Bin Kadal (CBK) <cbk@dummy>
sub   4096R/77021270 2020-09-28 [expires: 2021-09-28]

cbkadal@badak:~$ gpg2 --output secret.asc --export-secret-key --armor cbk@dummy
cbkadal@badak:~$ gpg2 --output mypubkey.txt --export --armor cbk@dummy
cbkadal@badak:~$ ls -F secret.asc mypubkey.txt 
mypubkey.txt  secret.asc
cbkadal@badak:~$
```
```
cbkadal@osp:~$ scp -P 6023 demo@localhost:~/"*.asc" .
demo@localhost's password: 
mypubkey.txt                  100% 3108   134.9KB/s   00:00    
secret.asc                    100% 6604   243.8KB/s   00:00    
cbkadal@osp:~$
```

```
cbkadal@osp:~$ gpg --import Cicak-Bin-Kadal-SK.asc 
gpg: directory '/home/cbkadal/.gnupg' created
gpg: keybox '/home/cbkadal/.gnupg/pubring.kbx' created
gpg: /home/cbkadal/.gnupg/trustdb.gpg: trustdb created
gpg: key 420959134762F757: public key "Cicak Bin Kadal (CBK) <cbkadal@DELETE.vlsm.org>" imported
gpg: key 420959134762F757: secret key imported
gpg: Total number processed: 1
gpg:               imported: 1
gpg:       secret keys read: 1
gpg:   secret keys imported: 1
cbkadal@osp:~$ gpg --import ospubkey.txt 
gpg: key D0F5DBDD67DF6DDE: public key "Operating Systems (OS) <operatingsystems@DELETE.vlsm.org>" imported
gpg: Total number processed: 1
gpg:               imported: 1
cbkadal@osp:~$ gpg --list-secret-keys
/home/cbkadal/.gnupg/pubring.kbx
--------------------------------
sec   rsa4096 2020-05-28 [SC] [expires: 2021-05-23]
      0EFC7183596281364D6CB349420959134762F757
uid           [ unknown] Cicak Bin Kadal (CBK) <cbkadal@DELETE.vlsm.org>
ssb   rsa4096 2020-05-28 [E] [expires: 2021-05-23]

cbkadal@osp:~/$ gpg --list-keys
/home/cbkadal/.gnupg/pubring.kbx
--------------------------------
pub   rsa4096 2020-05-28 [SC] [expires: 2021-05-23]
      0EFC7183596281364D6CB349420959134762F757
uid           [ unknown] Cicak Bin Kadal (CBK) <cbkadal@DELETE.vlsm.org>
sub   rsa4096 2020-05-28 [E] [expires: 2021-05-23]

pub   rsa4096 2020-02-13 [SC] [expires: 2021-02-12]
      B4507B533F7F22840BD8E93ED0F5DBDD67DF6DDE
uid           [ unknown] Operating Systems (OS) <operatingsystemsDELETE.@vlsm.org>
sub   rsa4096 2020-02-13 [E] [expires: 2021-02-12]

cbkadal@osp:~$
```
```
cbkadal@osp:~/git/os202/TXT$ gpg --list-keys
/home/cbkadal/.gnupg/pubring.kbx
--------------------------------
pub   rsa4096 2020-05-28 [SC] [expires: 2021-05-23]
      0EFC7183596281364D6CB349420959134762F757
uid           [ unknown] Cicak Bin Kadal (CBK) <cbkadal@DELETE.vlsm.org>
sub   rsa4096 2020-05-28 [E] [expires: 2021-05-23]

pub   rsa4096 2020-02-13 [SC] [expires: 2021-02-12]
      B4507B533F7F22840BD8E93ED0F5DBDD67DF6DDE
uid           [ unknown] Operating Systems (OS) <operatingsystems@DELETE.vlsm.org>
sub   rsa4096 2020-02-13 [E] [expires: 2021-02-12]

cbkadal@osp:~/git/os202/TXT$ gpg -o mypubkey.txt --armor --export 4762F757
cbkadal@osp:~/git/os202/TXT$ ls -al
total 16
drwxr-xr-x 2 cbkadal cbkadal 4096 Sep 28 19:46 .
drwxr-xr-x 6 cbkadal cbkadal 4096 Sep 20 18:22 ..
-rw-r--r-- 1 cbkadal cbkadal  630 Sep 28 18:11 mylog.txt
-rw-r--r-- 1 cbkadal cbkadal 3098 Sep 28 19:46 mypubkey.txt
cbkadal@osp:~/git/os202/TXT$ 
```
```
cbkadal@osp:~/git/os202/TXT$ ls -al
total 16
drwxr-xr-x 2 cbkadal cbkadal 4096 Sep 28 19:46 .
drwxr-xr-x 6 cbkadal cbkadal 4096 Sep 20 18:22 ..
-rw-r--r-- 1 cbkadal cbkadal  630 Sep 28 18:11 mylog.txt
-rw-r--r-- 1 cbkadal cbkadal 3098 Sep 28 19:46 mypubkey.txt
cbkadal@osp:~/git/os202/TXT$ sha256sum mylog.txt mypubkey.txt > SHA256SUM
cbkadal@osp:~/git/os202/TXT$ gpg -o SHA256SUM.asc -a -sb SHA256SUM 
cbkadal@osp:~/git/os202/TXT$ ls -al
total 24
drwxr-xr-x 2 cbkadal cbkadal 4096 Sep 28 19:51 .
drwxr-xr-x 6 cbkadal cbkadal 4096 Sep 20 18:22 ..
-rw-r--r-- 1 cbkadal cbkadal  630 Sep 28 18:11 mylog.txt
-rw-r--r-- 1 cbkadal cbkadal 3098 Sep 28 19:46 mypubkey.txt
-rw-r--r-- 1 cbkadal cbkadal  155 Sep 28 19:49 SHA256SUM
-rw-r--r-- 1 cbkadal cbkadal  833 Sep 28 19:51 SHA256SUM.asc
cbkadal@osp:~/git/os202/TXT$ gpg --verify SHA256SUM.asc SHA256SUM
gpg: Signature made Mon 28 Sep 2020 07:51:56 PM WIB
gpg:                using RSA key 0EFC7183596281364D6CB349420959134762F757
gpg: Good signature from "Cicak Bin Kadal (CBK) <cbkadal@DELETE.vlsm.org>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: 0EFC 7183 5962 8136 4D6C  B349 4209 5913 4762 F757
cbkadal@osp:~/git/os202/TXT$
```

<br>
#### ENDOFPAGE
[HOME](index.md)
[ABOUT](README.md)
[WEB](https://osp4diss.vlsm.org/)
[GITHUB](https://github.com/UI-FASILKOM-OS/osp4diss/)
[TOP](#)
[BOTTOM](#endofpage)
[PREV](CBKadal.md)
[NEXT](index.md)
