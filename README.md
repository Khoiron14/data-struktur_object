# Data Struktur Object

Tipe data object ini sering digunakan dalam konsep Object Oriented Programming (OOP). Dimana sebuah object terbentuk dari proses instansiasi. Tipe data object tidak hanya
digunakan untuk menyimpan data, tetapi juga informasi untuk mengolah data.

### Contoh
```PHP
class basic {
    var $hello = "Hello Word";
}
//membuat object
$pesan = new basic();
//menampilkan pesan
echo $pesan->hello;
```

### Contoh Lainnya
```PHP
class pick {
    var nama;
    var hero;
}
//membuat object
$heroKhoiron = new pick();

//set property
$heroKhoiron->nama="Vheriv3";
$heroKhoiron->hero="Venomancer";

//menampilkan
echo $heroKhoiron->nama." Memilih Hero ".$heroKhoiron->hero;
```
- Saya membuat class pick(), kemudian membuat variable nama dan hero didalamnya.
- Membuat objek baru dari class pick(), bernama '$heroKhoiron'.
- Kemudian menampilkan hasilnya.

Kode diatas akan menampilkan "Vheriv3 Memilih Hero Venomancer".
