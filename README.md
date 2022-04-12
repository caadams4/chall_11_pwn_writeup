chall_11_pwn_writeup


Ok, lets recon

![image](https://user-images.githubusercontent.com/79220528/162876905-c1849f1a-fcff-4a19-853e-24d5157ef22b.png)

![image](https://user-images.githubusercontent.com/79220528/162876974-74f66c2b-3121-4e20-8845-4014534de8aa.png)

We see there's no PIE and a win function. This is good; that win() won't change.

![image](https://user-images.githubusercontent.com/79220528/162877118-46719c16-06e2-475d-90af-90808e98b74c.png)

![image](https://user-images.githubusercontent.com/79220528/162877169-f2e15a7d-ce2c-4dbf-a590-04931b853d86.png)

We see the system call puts is called twice. We can target the GOT using a write what where and fmtstr w/ pwntools. We also know our payload is being read at the 7th arg ( %7$p )

Our exploit script:

![image](https://user-images.githubusercontent.com/79220528/162877474-57b54d74-18ea-4614-bf3d-ab7f01465800.png)

![image](https://user-images.githubusercontent.com/79220528/162877591-fbf8a0ca-ace2-4678-9e74-0eda8ef0be25.png)

