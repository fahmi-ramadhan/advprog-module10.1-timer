## 1.2. _Understanding How it Works_

![understanding how it works](https://i.imgur.com/i7ri3Fe.png)

Pada program tersebut, terdapat sebuah _task_ asinkronus yang akan mencetak `"howdy!"`, kemudian menunggu selama dua detik menggunakan `TimerFuture` dan akhirnya mencetak `"done!"` setelah waktu tunggu selesai. Namun, dapat dilihat bahwa sebelum _task_ tersebut selesai, program mencetak `"Fahmi's computer: hey hey"` terlebih dahulu. Jadi, dapat disimpulkan bahwa yang terjadi adalah program tidak akan terblokir saat menunggu _task_ asinkronus selesai.
