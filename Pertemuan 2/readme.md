#  Implementasi Linked List Sederhana (Python)

# Fitur

Implementasi ini mendukung berbagai operasi dasar Linked List, antara lain:

* Menambah data di awal list (`insert_at_first`)
* Menambah data di bagian akhir (`insert_at_last`)
* Menyisipkan data pada posisi tertentu (`insert_at`)
* Menghapus elemen pertama (`remove_first`)
* Menghapus elemen terakhir (`remove_last`)
* Menghapus elemen berdasarkan index (`remove_at`)
* Menampilkan isi list (`print`)
* Menghitung jumlah elemen (`length`)


#  Penjelasan Class

Class adalah konsep dasar dalam pemrograman berorientasi objek yang berfungsi sebagai **cetak biru** (blueprint) untuk membuat objek.
Melalui class, kita dapat mendefinisikan atribut dan method yang kemudian dapat digunakan oleh objek yang dihasilkan dari class tersebut.



#  Penjelasan Sintaks & Fungsi

##  Class `Node`

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer


**Node** adalah unit dasar penyusun Linked List.

* `data` → menyimpan informasi
* `next` → menyimpan referensi ke node selanjutnya



##  Class `LinkedList`

```python
class LinkedList:
    def __init__(self):
        self.head = None


Class ini berfungsi sebagai wadah yang mengelola seluruh node.
`self.head` selalu menunjuk ke elemen pertama dalam list.



##  `insert_at_first(data)`

Menambahkan node baru sebagai elemen pertama.

```python
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node
```

Node baru dibuat dengan mengarah ke head lama, kemudian head diperbarui.



##  `insert_at_last(data)`

Menambahkan data di bagian paling akhir.

```python
def insert_at_last(self, data):
    if self.head is None:
        self.head = Node(data)
    else:
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next
        node_sekarang.next = Node(data)
```

Jika list masih kosong → langsung dijadikan head.
Jika tidak → telusuri list sampai node terakhir dan tambahkan node baru.



##  `insert_at(index, data)`

Menyisipkan node pada posisi tertentu.

```python
def insert_at(self, index, data):
    if index < 0 or index > self.length() - 1:
        print("index tidak valid!")
    elif index == 0:
        self.insert_at_first(data)
    else:
        urutan = 0
        node_sekarang = self.head
        while urutan < index - 1:
            urutan += 1
            node_sekarang = node_sekarang.next
        node = Node(data, node_sekarang.next)
        node_sekarang.next = node


Jika posisi valid, program menelusuri node sampai satu langkah sebelum target, lalu menyisipkan node baru.



##  `remove_first()`

Menghapus node pertama.

```python
def remove_first(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    else:
        self.head = self.head.next


Head digeser ke node berikutnya sehingga node sebelumnya otomatis terlepas.


##  `remove_last()`

Menghapus node terakhir.

```python
def remove_last(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    elif self.head.next is None:
        self.head = None
    else:
        node_sebelumnya = None
        node_sekarang = self.head
        while node_sekarang.next:
            node_sebelumnya = node_sekarang
            node_sekarang = node_sekarang.next
        node_sebelumnya.next = None


Jika hanya ada satu node → head dihapus.
Jika lebih dari satu → cari node terakhir dan putuskan hubungannya.



##  `remove_at(index)`

Menghapus node pada index tertentu.

```python
def remove_at(self, index):
    if index < 0 or index >= self.length():
        print("index invalid!")
    elif index == 0:
        self.remove_first()
    else:
        urutan = 0
        node_sekarang = self.head
        while urutan < index - 1:
            node_sekarang = node_sekarang.next
            urutan += 1
        node_sekarang.next = node_sekarang.next.next


Program mencari node sebelum posisi target, lalu menghubungkannya ke node setelah target.



##  `print()`

Menampilkan seluruh node dalam list.

```python
def print(self):
    if self.head is None:
        print("data kosong")
    else:
        text_print = ''
        node_sekarang = self.head
        while node_sekarang:
            text_print += str(node_sekarang.data) + " -> "
            node_sekarang = node_sekarang.next
        print(text_print)


Output disajikan dalam format berantai:
`data -> data -> ...`



##  `length()`

Menghitung jumlah elemen.

```python
def length(self):
    urutan = 0
    data_sekarang = self.head
    while data_sekarang:
        data_sekarang = data_sekarang.next
        urutan += 1
    return urutan


Menggunakan perulangan sederhana untuk menghitung total node.



#  Eksekusi Program

```python
LL = LinkedList()

# insert
LL.insert_at_first("jeruk")
LL.insert_at_first("mangga")
LL.insert_at_first("manggis")
LL.insert_at_last("apel")
LL.insert_at(2, "anggur")

# remove
LL.remove_first()
LL.remove_last()
LL.remove_at(1)
LL.remove_at(1)

LL.print()
print(LL.length())
```



#  Proses Eksekusi (Ringkas)

1. Membuat list kosong (`head = None`)
2. Menambahkan jeruk → menjadi elemen pertama
3. Menambahkan mangga → menjadi head baru
4. Menambahkan manggis → menduduki posisi head
5. Menambahkan apel di bagian akhir
6. Menyisipkan anggur pada index 2
7. Menghapus elemen pertama (manggis)
8. Menghapus elemen terakhir (apel)
9. Menghapus elemen index 1 (anggur)
10. Menghapus index 1 lagi (jeruk)

---

# 🟢 Output Akhir

```
mangga -> 
1
```

List hanya menyisakan satu elemen, yaitu **mangga**.

---

Kalau mau dibuatkan **versi yang tampilannya seperti dokumentasi profesional**, atau ingin **ditambah diagram alur / flowchart**, tinggal bilang!




