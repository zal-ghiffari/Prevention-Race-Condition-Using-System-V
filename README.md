# Prevention Race Condition Using System V

pada php dapat menggunakan --enable-sysvsem untuk menanganinya, dalam hal ini percobaan ini dilakukan dengan fungsi sem_get, sem_acquire, dan sem_release untuk mengamankan transaksi. Namun memiliki kelemahan yaitu hanya bisa dijalankan jika --enable-sysvsem pada  php diaktifkan. Dilakukan percobaan pada windows namun pada system tersebut tidak dapat menggunakan sysvsem. Untuk itu pada percobaan ini dapat menggunakan Lampp pada kali linux

Pada variable sem, menggunakan sem_get untuk mendapatkan key, dimana pada contoh tersebut menggunakan 1234 sebagai kunci kemudian 1 sebagai parameter yang ditentukan untuk menentukan jumlah maksimum proses/request yang dapat mendapatkan key sekaligus. Artinya jika sebuah request telah memperoleh key 1234 tetapi belum menggunakannya, dan request lain melakukan pemanggilan fungsi sem_acquire pada kunci yang sama, panggilan akan ditolak sampai request pertama menggunakan kuncinya. Jadi teknik ini dapat mencegah serangan race condition. 

Fix vuln by zal - RPLK

Untuk memenuhi UTS Secure Programming
