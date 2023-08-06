
- 生成SSH密钥（这里是生成Obsidian-CS库的）

``` java
ksia@bogon ~ % ssh-keygen -t rsa -C "ksiafor@gmail.com"
-----
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/ksia/.ssh/id_rsa): Obsidian-CS
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in Obsidian-CS
Your public key has been saved in Obsidian-CS.pub
The key fingerprint is:
SHA256:jsbOkE+REJAFT4nOLWcvkVFzNW56pz6trkxvhJEdnYI ksiafor@gmail.com
The key's randomart image is:
+---[RSA 3072]----+
|  o*+oo .oo. .   |
|  ooo. oE.o.o    |
| o .oo   ooo     |
|  + *. .oo.      |
|   + oo So. .    |
|    .o.+...o     |
|    o.= o...     |
|     B o oo .    |
|      + o+=o     |
+----[SHA256]-----+

ksia@bogon ~ % cat /Users/ksia/Obsidian-CS.pub
-----
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDMTRIiQydU9ZVNBvwMmheAWsgt7YS7v2Lm2GxZ1V9yGwgNfaoafr9NNxYSXfyBJTD2nHoawbj3yA36jtx+q1HOhVlVshJRFyXBJxJv6SnkUTZG+iE4EBKf0RzsDP5FnjDAZz77SsqwafYaVX38s0ApsRMa/cmCkda46MbdTU2DwHu6CgA8cNCCiQfaT6sy1Hs0zuxwl1hqH7hyHBwh9eUCceqBrG4UjZKyt+XYFKar01yAnG44UjI5So3rU5kJxG3XkHgiRmJD1nLCi6SgMTRIRfqHbAjCmKW/GK7dky801Uy/waHi2tQUbXQVrG440h2YLSA1iB7zET6Ls7oq6DItd+EltJxDTZ2LSbZgJWGNI1qEGMN2wMM4zRLZED8a5geeCUG3ke/xvHP4ThI/xTqjZHaCorKEDpRuBLhpsXSNKuKP1Iu1ZqtHAIx8rM7+XeGNcv9Gab+ki/Kl0dFsNjTMCbPAvdwiXTmsYIr57sV0nb+Ru7MODtKGykhLB4rGmZ0= ksiafor@gmail.com

```