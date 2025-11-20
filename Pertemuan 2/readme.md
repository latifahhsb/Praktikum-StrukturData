# **Penjelasan Kode LinkedList**

## **class Node**
- Konstruktor node yang menyimpan:
  - `data`: nilai yang disimpan pada node.
  - `next`: pointer/reference ke node berikutnya (default None).

## **class LinkedList**
- Membuat linked list kosong dengan atribut:
  - `head`: node pertama pada linked list, awalnya None.

## **insert_at_first(self, data)**
- Menambahkan node baru di awal linked list.
- Membuat node baru dengan `data` dan menunjuk `next` ke head saat ini, lalu update head ke node baru tersebut.

## **insert_at_last(self, data)**
- Menambahkan node baru di akhir linked list.
- Jika list kosong (`head` None), node baru langsung jadi head.
- Jika tidak, traversing sampai node terakhir, lalu hubungkan node terakhir ke node baru.

## **insert_at(self, index, data)**
- Menyisipkan node baru pada posisi (index) tertentu (0-based).
- Jika `index` kurang dari 0 atau lebih besar dari panjang list - 1, cetak "index tidak valid".
- Jika index 0, panggil `insert_at_first`.
- Jika valid, traversing ke node sebelum posisi index, lalu sisipkan node baru.

## **remove_first(self)**
- Menghapus node paling awal.
- Jika kosong, cetak "tidak ada data yang bisa dihapus".
- Jika tidak, pindahkan head ke node berikutnya, node pertama sebelumnya akan otomatis terhapus oleh garbage collector.

## **remove_last(self)**
- Menghapus node paling akhir.
- Jika kosong, cetak "tidak ada data yang bisa dihapus".
- Jika hanya satu node, set head ke None.
- Jika lebih dari satu node, traversing ke node kedua terakhir, lalu set `next` ke None.

## **remove_at(self, index)**
- Menghapus node pada posisi index (0-based).
- Jika index kurang dari 0 atau lebih besar sama dengan panjang list, cetak "index invalid".
- Jika index 0, panggil `remove_first`.
- Jika valid, traversing ke node sebelum index, lalu hubungkan node tersebut ke node setelah node yang akan dihapus.

## **print(self)**
- Mencetak semua elemen linked list dalam format `data1 -> data2 -> ...`.
- Jika kosong, cetak "data kosong".

## **length(self)**
- Menghitung dan mengembalikan jumlah node dalam linked list dengan traversing dari head sampai akhir.


# **Contoh Penggunaan Kode**

```python
ll = LinkedList()

# Insert data
ll.insert_at_first("jeruk")
ll.insert_at_first("mangga")
ll.insert_at_first("manggis")
ll.insert_at_last("apel")
ll.insert_at(2, "anggur")

# Hapus data
ll.remove_first()
ll.remove_last()
ll.remove_at(1)
ll.remove_at(1)

# Tampilkan isi linked list dan panjangnya
ll.print()
print(ll.length())
