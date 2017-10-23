# Data Struktur Object

Tipe data object ini sering digunakan dalam konsep Object Oriented Programming (OOP). Dimana sebuah object terbentuk dari proses instansiasi. Tipe data object tidak hanya
digunakan untuk menyimpan data, tetapi juga informasi untuk mengolah data.

### Contoh
```PHP
class Basic
{
    var $hello = "Hello Word";
}
//membuat object
$pesan = new Basic();
//menampilkan pesan
echo $pesan->hello;
```

### Contoh Lainnya
```PHP
class Pick
{
    var nama;
    var hero;
}
//membuat object
$heroKhoiron = new Pick();

//set property
$heroKhoiron->nama="Vheriv3";
$heroKhoiron->hero="Venomancer";

//menampilkan
echo $heroKhoiron->nama." Memilih Hero ".$heroKhoiron->hero;
```
- Saya membuat class Pick(), kemudian membuat variable nama dan hero didalamnya.
- Membuat objek baru dari class Pick(), bernama '$heroKhoiron'.
- Kemudian menampilkan hasilnya.

Kode diatas akan menampilkan "Vheriv3 Memilih Hero Venomancer".

### Cara Mengonversi Array ke Object atau Sebaliknya.

#### Konversi Array ke Object

```PHP
function arrayToObject($array)
{
    if (is_array($array)) {
        return (object) array_map(__FUNCTION__, $array);
    } else {
        return $array;
    }
}

$test = [
    'A' => 'Test A',
    'B' => 'Test B',
    'C' => [
        'CA' => 'Test CA',
        'CB' => [
            'CBA' => 'Test CBA'
        ]
    ],
    'D' => 'Test D'
];

$object_test = arrayToObject($test);

// Pemanggilan...
echo $object_test->A; // Hasil => `Test A`
echo $object_test->C->CB; // Hasil => `Test CB`
echo $object_test->C->CB->CBA; // Hasil => `Test CBA`
```

#### Konversi Object ke Array

```PHP
function objectToArray($object)
{
    if (is_object($object)) {
        $object = get_object_vars($object);
    }
    if (is_array($object)) {
        return array_map(__FUNCTION__, $object);
    } else {
        return $object;
    }
}

$test = new stdClass;
$test->A = 'Test A';
$test->B = 'Test B';
$test->C = new stdClass;
$test->C->CA = 'Test CA';
$test->C->CB = new stdClass;
$test->C->CB->CBA = 'Test CBA';
$test->D = 'Test D';

$array_test = objectToArray($test);

// Pemanggilan
echo $array_test['A']; // Hasil => `Test A`
```
- Sumber konversi [http://www.dte.web.id](http://www.dte.web.id/2014/04/php-konversi-array-menjadi-objek.html)
