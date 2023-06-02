# Layout Constraints : ConstrainedBox, Row, dan Column

Flutter juga memiliki widget yang memungkinkan kita memberikan constraint tambahan terhadap child widget. Widget ini bernama **ConstrainedBox**. 

Perhatikan bahwa constraint dari widget ini hanya bersifat tambahan dan **ConstrainedBox** masih memiliki constraints yang diturunkan dari parent-nya.

---

### Part 1

> Constraint dari ConstrainedBox akan diabaikan karena widget ConstrainedBox masih menggunakan constraints dari root widget yang harus menampilkan sesuai ukuran layar.

* Berbeda ketika kita membungkus ConstrainedBox dengan Center. 

Center memungkinkan ConstrainedBox untuk memiliki ukuran berapa pun selama tidak melebihi ukuran layar. 

**Oleh karena itu, Container di bawahnya hanya dapat memiliki ukuran antara 70 x 70 hingga 150 x 150.**

---

### Part 2

Setelah mempelajari bagaimana constraints dapat memengaruhi posisi dan ukuran dari widget, ada juga widget yang tidak memberikan constraints pada widget di bawahnya. Widget ini adalah **UnconstrainedBox**.

Kita tahu bahwa root widget dari Flutter memberikan constraints agar widget di bawahnya berukuran sama dengan ukuran layar. Namun, UnconstrainedBox memungkinkan widget di bawahnya untuk memiliki ukuran berapa pun. **Sehingga, Container dapat menentukan ukuran dengan bebas bahkan hingga melebihi ukuran layar sekalipun (OVERFLOW)**

---

### Part 3

Lalu, bagaimana dengan widget yang berpola **parent-children seperti Row, Column, dan sebagainya?**

Sama seperti UnconstrainedBox, widget seperti Row tidak memberikan constraints terhadap children-nya, melainkan membiarkan children widget menentukan ukuran yang diinginkan.

---

### Part 4

Karena **Row** tidak memberikan constraints, maka ketika widget di dalamnya melebihi ukuran layar akan muncul **overflow** warning.

Sekarang coba bungkus Container teks yang panjang ke dalam widget **Expanded**.

```
Row(
  children: [
    Expanded(
      child: Container(
        color: Colors.red,
        child: Text('Hello! This is a very long Text!'),
      ),
    ),
    Container(
      color: Colors.green,
      child: Text('Goodbye!'),
    ),
  ],
),
```

Jika setiap child widget dari **Row** dibungkus dengan widget **Expanded**, *maka seluruh children akan memiliki ukuran yang sama.*

Ukuran widget Expanded akan mengembang berdasarkan widget lainnya. Hal ini akan mengabaikan ukuran dari widget Container di bawahnya.

## Solusi :
Kalau pakai Row jadi overflow maka kunci nya di dalam row -> children -> Expanded -> isi code anda.

Jadi Container akan menjadi child dari Expanded().

**Jika setiap child widget dari Row dibungkus dengan widget Expanded, maka seluruh children akan memiliki ukuran yang sama.**

---

Untuk Ukuran Font Default
jadi versi lama pakai bodyText1 dan bodyText2 utk default

Sekarang bodyText1 bisa di ganti dgn bodyLarge
dan bodyText2 bisa diganti dgn bodyMedium.


**Fonts:**
* https://api.flutter.dev/flutter/material/TextTheme-class.html
* https://api.flutter.dev/flutter/material/TextTheme/bodyLarge.html
* https://api.flutter.dev/flutter/material/TextTheme/bodyMedium.html

---

Opsi widget lain yang bisa digunakan adalah Flexible. Perbedaan Flexible dan Expanded adalah widget Flexible memungkinkan child widget-nya berukuran lebih kecil dibandingkan ukuran Flexible. 

Sementara, child widget dari Expanded harus memiliki ukuran sesuai ukuran Expanded.

