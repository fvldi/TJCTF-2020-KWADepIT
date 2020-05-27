

# Titanic
**Soal**

I wrapped tjctf{} around the lowercase version of a word said in the 1997 film "Titanic" and created an MD5 hash of it: `e246dbab7ae3a6ed41749e20518fcecd`.
____________________________________
**Jawaban**

Yang kita ketahui adalah hash MD5 tersebut berasal dari script film "Titanic". Setiap katanya dibuat lowercase dan di tambahi dengan tjctf{}. 
Langkah pertama adalah mengkopi script film Titanic terlebih dahulu di [sini](http://sites.inka.de/humpty/titanic/script.html). Kemudian dengan bantuan visual studio code, ubah semua menjadi lowercase, hapus `.` `,` `:` `/` , ubah spasi menjadi enter dan tambahkan tjctf{} di setiap barisnya.
Setelah itu gunakan hashcat pada terminal dengan command sebagai berikut :

    hashcat -m 0 -a 0 e246dbab7ae3a6ed41749e20518fcecd titanic.txt --force --show

Titanic.txt adalah script dari film "Titanic" yang sudah diubah. Tekan enter dan hasil akan langsung muncul.
____________________________________
**Flag**

tjctf{ismay's}
