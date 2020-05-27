# Censorship - 30 points
## Description

My friend has some top-secret government intel. He left a message, but the government censored him! They didn't want the information to be leaked, but can you find out what he was trying to say? ```nc p1.tjctf.org 8003```

## Flag

```
tjctf{TH3_1llum1n4ti_I5_R3aL}
```

## Solution

Untuk menyelesaikan problem ini, diperlukan langkah-langkah sebagai berikut:

1. Buka wireshark (disini saya menggunakan kali linux sebagai operating system). kemudian capture salah satu wired interface yang tersedia;
2. Jalankan perintah ```nc p1.tjctf.org 8003``` pada linux terminal, kemudian jawab pertanyaan yang ada. Dengan demikian, maka terdapat packet-packet baru yang tercapture oleh wireshark seperti pada gambar berikut.

![image](/img/01.jpg)

3. Pada wireshark export packet dengan cara pilih ```File - Export Packet Disserctions - As Plain Text...``` ;

![image](/img/02.jpg)

4. Buka packet yang telah diexport tadi pada text editor (disini saya menggunakan VSCode), kemudian cari kata kunci dengan cara tekan ```ctrl + f``` lalu ketik ```"tjctf{"```. Maka flag akan terlihat seperti pada gambar berikut.

![image](/img/03.jpg)