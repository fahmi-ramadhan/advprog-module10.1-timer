## 1.2. _Understanding How it Works_

![understanding how it works](https://i.imgur.com/i7ri3Fe.png)

Pada program tersebut, terdapat sebuah _task_ asinkronus yang akan mencetak `"howdy!"`, kemudian menunggu selama dua detik menggunakan `TimerFuture` dan akhirnya mencetak `"done!"` setelah waktu tunggu selesai. Namun, dapat dilihat bahwa sebelum _task_ tersebut selesai, program mencetak `"Fahmi's computer: hey hey"` terlebih dahulu. Jadi, dapat disimpulkan bahwa yang terjadi adalah program tidak akan terblokir saat menunggu _task_ asinkronus selesai.

## 1.3. _Multiple Spawn and removing drop_

![multiple spawn and removing drop 1](https://i.imgur.com/9DtlFKA.png)
![multiple spawn and not removing drop](https://i.imgur.com/YrVp1aE.png)
![multiple spawn and removing drop 2](https://i.imgur.com/m7IzL67.png)

Ketika baris `drop(spawner)` dihapus, itu berarti `spawner` akan tetap aktif meskipun semua _task_ sudah ditambahkan. Hal ini menyebabkan `executor` tetap menerima _task_ baru untuk dijalankan meskipun dalam kasus ini tidak ada _task_ baru yang ditambahkan sehingga program tidak akan berhenti. Pada program ini, `spawner` berfungsi untuk menambahkan _task_ ke dalam antrean `executor` sementara `executor` berfungsi untuk menjalankan _task_ tersebut. Ketika `spawner` di-_drop_, `executor` mendapatkan sinyal bahwa tidak ada lagi _task_ yang ditambahkan sehingga akan berhenti setelah semua _tas_ saat ini selesai diproses. Selain itu, dapat dilihat pada gambar di atas bahwa urutan cetak dapat bervariasi. Hal tersebut dapat terjadi karena sifat asinkronus dari eksekusi _task_ tersebut oleh `executor` yang menjalankan _task_ secara konkuren.
