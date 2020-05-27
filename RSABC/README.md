

# RSABC
**Soal**

I was just listening to some relaxing ASMR when a notification popped up with this. ???

n = 57772961349879658023983283615621490728299498090674385733830087914838280699121
e = 65537
c = 36913885366666102438288732953977798352561146298725524881805840497762448828130
____________________________________

**Jawaban**

Soal ini mirip dengan soal Easy as RSA pada TJCTF 2019. Langkah pertama dalah melakukan faktorisasi pada `n` menggunakan [website ini](factordb.com). Faktor dari `n` disimpan dalam `p` dan `q`

```
p = 202049603951664548551555274464815496697
q = 285934543893985722871321330457714807993
```
Masukkan `n`, `e`, `c`, `p` dan `q` ke **rsabc.rb**. Gunakan terminal untuk menjalankan program ruby dan flag akan muncul langsung
`$ruby rsabc.rb`
____________________________________
**Flag**

tjctf{BOLm1QMWi3c}
