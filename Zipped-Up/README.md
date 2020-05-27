

# Zipped Up
**Soal**

My friend changed the password of his Minecraft account that I was using so that I would stop being so addicted. Now he wants me to work for the password and sent me this [zip file](https://github.com/lumbricina/TJCTF-2020-05311840000044/blob/master/Miscellaneous/Zipped%20Up/0.zip). I tried unzipping the folder, but it just led to another zipped file. Can you find me the password so I can play Minecraft again?
____________________________________

**Jawaban**

Pada folder 0 terdapat folder 1 yang didalamnya terdapat folder 2 dan seterusnya. Setiap folder berbentuk `.zip` atau `.tar.bz2` atau `.kz3` atau lainnya. Pada setiap folder juga terdapat 1 file txt yang berisi `tjctf{n0t_th3_fl4g}`. Hanya ada 1 file txt diantara total 1001 folder yang berisi flag asli dan tidak pada folder terakhir.
Buka folder tersebut satu per satu, untuk mempercepat gunakan aplikasi [Kuaizip](http://www.kuaizip.com/en/).
Setelah membuka tiap file, file yang asli terdapat pada folder ke 829.

____________________________________
**Flag**

tjctf{p3sky_z1p_f1L35}
