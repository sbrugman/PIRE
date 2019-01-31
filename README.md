# PIRE: Adversarial queries for blocking Content-based Image Retrieval (CBIR).

This repository release the pytorch code for PIRE that generates adversarial examples for neural feature-based CBIR.
Now we only support generate adversarial queries for GeM.


To get the PIRE (T = 500) results in our paper, please run:

```
python3 gen_pire.py -T "500" -gpu_id "0" -cnnmodel "gem" -in_dir "./img_input/" -out_dir "./img_output/" -p True
```


Detailed explanation of PIRE's parameters can be checked by:

```
python3 gen_pire.py -h
```

# Results:

The Table shows that adversarial image query generated with enough rounds (T=500) and fewer rounds (T=200) can both
strongly decreases the performance of neural-feature-based CBIR.


|                  | Oxford5k (BB/WI)                   | Paris6k(BB/WI)                     |
|------------------|-----------------------------|-----------------------------|
| Original Queries | 78.39/74.42                 | 87.27/87.26                 |
| PIRE (T = 200)   | 22.98/18.00                 | 34.49/26.53                 |
| PIRE (T = 500)   | 3.93/2.31                   | 10.53/7.18                  |
	
Some examples of generated images are shown below:

![patches](https://github.com/liuzrcc/PIRE/examples/PIRE_exp_1.jpg)



Please cite the following paper if you use PIRE in your research.

      @misc{pire2019,
      Author = {Zhuoran Liu and Zhengyu Zhao and Martha Larson},
      Title = {Who's Afraid of Adversarial Queries? The Impact of Image Modifications on Content-based Image Retrieval},
      Year = {2019},
      Eprint = {arXiv:1901.10332},
      }
      

