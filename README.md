# Layout Flutter Dasar

Ketika sebuah Container tidak didefinisikan ukurannya, 
maka Container akan menggunakan ukuran dari child widget-nya

dan jika Container tidak memiliki widget
maka Container tersebut akan mengambil ukuran yang maksimal.

```
return Center(
      child: Container(
        color: Colors.red,
        child: Container(
          color: Colors.green,
          width: 100,
          height: 100,
        ),
      ),
    );
```
child container bisa child di dalam child container
dan padding.

Container memiliki parameter padding yang dapat memberikan jarak antara border dengan konten di dalamnya. 

Sehingga, ketika Container merah ditambahkan padding akan terlihat karena Container merah memiliki ukuran 100 + 10 + 10 dari padding-nya.