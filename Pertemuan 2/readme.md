 *Linked List* — Python

Linked List adalah struktur data yang setiap elemennya (node) saling terhubung menggunakan pointer. Elemen disimpan secara dinamis dan tidak bersebelahan di memori.

##  Membuat Node & Linked List

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer

class LinkedList:
    def __init__(self):
        self.head = None

##  Insert (Menambah Node)

### **Insert di Awal (insert_at_first)**

```python
ll.insert_at_first("jeruk")
ll.insert_at_first("mangga")
ll.insert_at_first("manggis")

### Output:

manggis -> mangga -> jeruk ->


### **Insert di Akhir (insert_at_last)**

```python
ll.insert_at_last("apel")


### Output:

manggis -> mangga -> jeruk -> apel ->

### **Insert di Index Tertentu (insert_at)**

```python
ll.insert_at(2, "anggur")


### Output:

manggis -> mangga -> anggur -> jeruk -> apel ->

## Remove (Menghapus Node)

### **Hapus Node Pertama (remove_first)**

```python
ll.remove_first()

### Output:

mangga -> anggur -> jeruk -> apel ->


### **Hapus Node Terakhir (remove_last)**

```python
ll.remove_last()


### Output:

mangga -> anggur -> jeruk ->

### **Hapus Node di Index Tertentu (remove_at)**

```python
ll.remove_at(1)


### Output:

mangga -> jeruk ->

##  Menampilkan Isi Linked List

```python
ll.print()


### Output:

mangga -> jeruk ->


##  Menghitung Panjang Linked List

```python
print(ll.length())


### Output:

2

