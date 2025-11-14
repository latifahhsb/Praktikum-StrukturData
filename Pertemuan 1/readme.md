Stack adalah struktur data yang cara kerjanya LIFO (Last In, First Out), artinya data yang terakhir dimasukkan akan menjadi data pertama yang dikeluarkan. Di Python, struktur stack bisa dibuat dengan memanfaatkan list, karena list sudah menyediakan fungsi untuk menambah dan menghapus data di bagian akhir.


Penjelasan Setiap Bagian dengan Contoh Output
1. Membuat Stack Kosong
stack = []

Pada baris ini kita membuat stack yang masih kosong menggunakan list. Stack belum memiliki data.

2. Push (Menambahkan Data ke Stack)
stack.append('A')
stack.append('B')
stack.append('C')

Setiap append() akan menambahkan data ke posisi paling atas stack. Setelah ketiga perintah ini dijalankan, isi stack menjadi:

['A', 'B', 'C']

Output:

Stack:  ['A', 'B', 'C']

3. Pop (Mengambil dan Menghapus Data Teratas)
element = stack.pop()

pop() berfungsi untuk menghapus data paling atas sekaligus mengembalikan nilainya. Karena C adalah elemen terakhir yang dimasukkan, maka C-lah yang akan dikeluarkan.

Output:

Pop:  C

4. Peek (Melihat Data Teratas Tanpa Menghapus)
topElement = stack[-1]


stack[-1] digunakan untuk mengecek elemen paling terakhir. Setelah C di-pop, elemen teratas sekarang adalah B.

Output:

Peek:  B

5. Mengecek Apakah Stack Kosong
isEmpty = not bool(stack)

bool(stack) akan bernilai True jika stack masih ada isinya. Karena stack masih berisi dua elemen (A dan B), maka hasilnya False.

Output:

isEmpty:  False

6. Mengetahui Jumlah Elemen dalam Stack
len(stack)

len() menghitung berapa banyak data yang masih ada di dalam stack. Saat ini ada dua elemen, jadi ukuran stack adalah 2.

Output:

Size:  2

Output Keseluruhan
Stack:  ['A', 'B', 'C']
Pop:  C
Peek:  B
isEmpty:  False
Size:  2


Penjelasan Implementasi Queue di Python

Queue adalah struktur data yang bekerja dengan prinsip FIFO (First In, First Out), artinya data yang pertama dimasukkan akan menjadi data pertama yang dikeluarkan. Python dapat membuat queue dengan menggunakan list, dengan aturan bahwa data baru ditambah di belakang (enqueue) dan data dikeluarkan dari depan (dequeue).

Penjelasan Per Baris + Output
1. Membuat Queue
queue = []


Baris ini digunakan untuk membuat queue kosong menggunakan list. Belum ada elemen di dalamnya.

2. Enqueue (Menambah Elemen ke Queue)
queue.append('A')
queue.append('B')
queue.append('C')


append() menambahkan elemen ke bagian belakang queue.

Ini mengikuti aturan FIFO: data yang masuk pertama akan keluar pertama.

Setelah tiga elemen dimasukkan, isi queue:

['A', 'B', 'C']

Output:
Queue:  ['A', 'B', 'C']

3. Dequeue (Menghapus Elemen Depan Queue)
element = queue.pop(0)


pop(0) menghapus elemen pada indeks 0, yaitu elemen paling depan.

Karena A masuk pertama, maka A-lah yang dikeluarkan.

Output:
Dequeue:  A

4. Peek (Melihat Elemen Depan Tanpa Menghapus)
frontElement = queue[0]


Karena A sudah dikeluarkan, elemen depan sekarang adalah B.

queue[0] digunakan untuk melihat isi antrian paling awal tanpa menghapusnya.

Output:
Peek:  B

5. Mengecek Apakah Queue Kosong
isEmpty = not bool(queue)


Penjelasan:

bool(queue) memberikan True jika queue berisi elemen.

not bool(queue) akan menghasilkan False jika queue tidak kosong.

Queue masih berisi: ['B', 'C'], jadi hasilnya False.

Output:
isEmpty:  False

6. Mengetahui Jumlah Elemen pada Queue
len(queue)


len(queue) menghitung berapa banyak data dalam queue.

Sekarang ada dua elemen: 'B' dan 'C'.

Output:
Size:  2

Output Lengkap

Hasil lengkap saat program dijalankan:

Queue:  ['A', 'B', 'C']
Dequeue:  A
Peek:  B
isEmpty:  False
Size:  2





