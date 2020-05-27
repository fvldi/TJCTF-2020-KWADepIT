

# Gym
**Soal**

Aneesh wants to acquire a summer bod for beach week, but time is running out. Can you help him [create a plan](https://github.com/lumbricina/TJCTF-2020-05311840000044/blob/master/Reversing/Gym/gym) to attain his goal? 
`nc p1.tjctf.org 8008`
____________________________________

**Jawaban**

Langkah pertama jalankan `nc p1.tjctf.org 8008` di terminal. Akan muncul 7 pertanyaan yang sama untuk dijawab. Melalui berbagai percobaan, program tersebut di reverse menjadi c program dengan ketentuan berikut :

1. eat_healthy = -4
2. do_pushup = -1
3. go_run = -5
4. go_sleep = -3

Karena diminta untuk menurunkan dari 211 ke 180, dapat dilakukan dengan `1`, `3`, `1`, `3`, `1`, `3`, `1` untuk mencapai goal.
____________________________________
**Flag**

tjctf{w3iGht_l055_i5_d1ff1CuLt}
