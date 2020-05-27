

# Login
**Soal**

Could you login into this [very secure site](https://login.tjctf.org/)? Best of luck!

____________________________________
**Jawaban**

Website tersebut berisi tulisan **Can you log in?** dengan 2 space untuk mengisi username dan password beserta tombol **Login** dibawahnya. 
Untuk mengetahui cara login, tekan F12 atau inspect element. Pada Sources dapat kita ketahui bahwa yang digunakan adalah md5 (ada file bernama md5.js). Pada file index, line ke 70 berisi seperti berikut :

    var _0xb31c=['value','c2a094f7d35f2299b414b6a1b3bd595a','Sorry.\x20Wrong\x20username\x20or\x20password.','admin','tjctf{','getElementsByName','toString'];
    
  
Dari situ dapat diketahui bahwa username adalah admin dan c2a094f7d35f2299b414b6a1b3bd595a adalah hash md5 dari passwordnya. Buka [md5 decrypt](https://www.md5online.org/md5-decrypt.html) dan lakukan decrypt pada tersebut. Akan didapat bahwa passwordnya adalah inevitable. 
Masukkan username : Admin dan password : inevitable.
____________________________________
**Flag**

tjctf{inevitable890898}
