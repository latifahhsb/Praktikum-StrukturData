Penjelasan Implementasi Stack dan Queue di Python
Stack (LIFO - Last In, First Out)
Stack adalah struktur data yang bekerja berdasarkan prinsip LIFO (Last In, First Out), di mana data yang terakhir dimasukkan akan menjadi data pertama yang dikeluarkan. Di Python, stack dapat diimplementasikan menggunakan list, karena list menyediakan fungsi untuk menambah dan menghapus data di bagian akhir.

Membuat Stack Kosong
python

Copy code
stack = []
Pada baris ini, kita membuat stack yang masih kosong menggunakan list. Stack belum memiliki data.

Push (Menambahkan Data ke Stack)
python
3 lines
Copy code
Download code
Click to expand
stack.append('A')
stack.append('B')
...
Setiap append() akan menambahkan data ke posisi paling atas stack. Setelah ketiga perintah ini dijalankan, isi stack menjadi:


Copy code
['A', 'B', 'C']
Output:


Copy code
Stack: ['A', 'B', 'C']
Pop (Mengambil dan Menghapus Data Teratas)
python

Copy code
element = stack.pop()
pop() berfungsi untuk menghapus data paling atas sekaligus mengembalikan nilainya. Karena 'C' adalah elemen terakhir yang dimasukkan, maka 'C'-lah yang akan dikeluarkan.

Output:


Copy code
Pop: C
Peek (Melihat Data Teratas Tanpa Menghapus)
python

Copy code
topElement = stack[-1]
stack[-1] digunakan untuk mengecek elemen paling terakhir. Setelah 'C' di-pop, elemen teratas sekarang adalah 'B'.

Output:


Copy code
Peek: B
Mengecek Apakah Stack Kosong
python

Copy code
isEmpty = not bool(stack)
bool(stack) akan bernilai True jika stack masih ada isinya. Karena stack masih berisi dua elemen ('A' dan 'B'), maka hasilnya False.

Output:


Copy code
isEmpty: False
Mengetahui Jumlah Elemen dalam Stack
python

Copy code
len(stack)
len() menghitung berapa banyak data yang masih ada di dalam stack. Saat ini ada dua elemen, jadi ukuran stack adalah 2.

Output:


Copy code
Size: 2
Output Keseluruhan

Copy code
Stack: ['A', 'B', 'C']
Pop: C
Peek: B
isEmpty: False
Size: 2
Queue (FIFO - First In, First Out)
Queue adalah struktur data yang bekerja dengan prinsip FIFO (First In, First Out), di mana data yang pertama dimasukkan akan menjadi data pertama yang dikeluarkan. Di Python, queue dapat diimplementasikan menggunakan list, dengan aturan bahwa data baru ditambah di belakang (enqueue) dan data dikeluarkan dari depan (dequeue).

Membuat Queue Kosong
python

Copy code
queue = []
Baris ini digunakan untuk membuat queue kosong menggunakan list. Belum ada elemen di dalamnya.

Enqueue (Menambah Elemen ke Queue)
python
3 lines
Copy code
Download code
Click to expand
queue.append('A')
queue.append('B')
...
append() menambahkan elemen ke bagian belakang queue. Ini mengikuti aturan FIFO: data yang masuk pertama akan keluar pertama. Setelah tiga elemen dimasukkan, isi queue:


Copy code
['A', 'B', 'C']
Output:


Copy code
Queue: ['A', 'B', 'C']
Dequeue (Menghapus Elemen Depan Queue)
python

Copy code
element = queue.pop(0)
pop(0) menghapus elemen pada indeks 0, yaitu elemen paling depan. Karena 'A' masuk pertama, maka 'A'-lah yang dikeluarkan.

Output:


Copy code
Dequeue: A
Peek (Melihat Elemen Depan Tanpa Menghapus)
python

Copy code
frontElement = queue[0]
Karena 'A' sudah dikeluarkan, elemen depan sekarang adalah 'B'. queue[0] digunakan untuk melihat isi antrian paling awal tanpa menghapusnya.

Output:


Copy code
Peek: B
Mengecek Apakah Queue Kosong
python

Copy code
isEmpty = not bool(queue)
bool(queue) memberikan True jika queue berisi elemen. not bool(queue) akan menghasilkan False jika queue tidak kosong. Queue masih berisi: ['B', 'C'], jadi hasilnya False.

Output:


Copy code
isEmpty: False
Mengetahui Jumlah Elemen pada Queue
python

Copy code
len(queue)
len(queue) menghitung berapa banyak data dalam queue. Sekarang ada dua elemen: 'B' dan 'C'.

Output:


Copy code
Size: 2
Output Lengkap
Hasil lengkap saat program dijalankan:


Copy code
Queue: ['A', 'B', 'C']
Dequeue: A
Peek: B
isEmpty: False
Size: 2





