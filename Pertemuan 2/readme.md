# * Kelas Node digunakan sebagai struktur dasar tiap elemen dalam linked list
class Node:
    # * Konstruktor Node menyimpan data dan pointer ke node berikutnya
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer


# * Kelas LinkedList sebagai wadah utama yang mengelola node-node
class LinkedList:
    # * Konstruktor LinkedList menginisialisasi head sebagai node pertama (kosong)
    def __init__(self):
        self.head = None

    # * Menambahkan node baru di posisi paling awal (head)
    def insert_at_first(self, data):
        node = Node(data, self.head)  # * Node baru menunjuk ke head lama
        self.head = node              # * Node baru menjadi head yang baru

    # * Menambahkan node baru di posisi terakhir
    def insert_at_last(self, data):
        if self.head is None:         # * Jika list masih kosong, head langsung diisi
            self.head = Node(data)
        else:
            node_sekarang = self.head # * Mulai dari head
            while node_sekarang.next: # * Mencari node terakhir
                node_sekarang = node_sekarang.next

            node = Node(data)         # * Node baru dibuat
            node_sekarang.next = node # * Node terakhir menunjuk ke node baru

    # * Menambahkan node berdasarkan indeks tertentu
    def insert_at(self, index, data):
        if index < 0 or index > self.length() - 1:  # * Validasi index
            print("index tidak valid")
        elif index == 0:                             # * Kalau index 0, masukkan ke awal
            self.insert_at_first(data)
        else:
            urutan = 0
            node_sekarang = self.head

            while urutan < index - 1:   # * Menelusuri sampai posisi sebelum index
                urutan += 1
                node_sekarang = node_sekarang.next

            node = Node(data, node_sekarang.next)  # * Node baru menunjuk node setelahnya
            node_sekarang.next = node              # * Node sebelumnya menunjuk node baru

    # * Menghapus node pertama (head)
    def remove_first(self):
        if self.head is None:               # * Jika kosong, tidak bisa hapus
            print("tidak ada data yang bisa dihapus")
        else:
            self.head = self.head.next      # * Head berpindah ke node berikutnya

    # * Menghapus node terakhir
    def remove_last(self):
        if self.head is None:
            print("tidak ada data yang bisa dihapus")
        elif self.head.next is None:        # * Jika hanya satu node
            self.head = None
        else:
            node_sebelumnya = None
            node_sekarang = self.head

            while node_sekarang.next:       # * Menelusuri sampai node terakhir
                node_sebelumnya = node_sekarang
                node_sekarang = node_sekarang.next

            node_sebelumnya.next = None     # * Putuskan hubungan dari node sebelum terakhir

    # * Menghapus node berdasarkan index
    def remove_at(self, index):
        if index < 0 or index > self.length():  # * Validasi index
            print("index invalid")
        elif index == 0:                         # * Kalau index 0, hapus depan
            self.remove_first()
        else:
            urutan = 0
            node_sekarang = self.head

            while urutan < index - 1:   # * Cari node sebelum target
                node_sekarang = node_sekarang.next
                urutan += 1

            node_sekarang.next = node_sekarang.next.next  # * Loncat, menghapus node target

    # * Mencetak seluruh node dalam list
    def print(self):
        if self.head is None:
            print("data kosong")
        else:
            text_print = ''
            node_sekarang = self.head

            while node_sekarang:                       # * Menelusuri semua node
                text_print += str(node_sekarang.data) + " -> "
                node_sekarang = node_sekarang.next

            print(text_print)

    # * Menghitung total node dalam linked list
    def length(self):
        urutan = 0
        data_sekarang = self.head

        while data_sekarang:           # * Menambah counter setiap pindah node
            data_sekarang = data_sekarang.next
            urutan += 1

        return urutan


# * Membuat objek LinkedList
ll = LinkedList()

# * Penyisipan data
ll.insert_at_first("jeruk")   # * jeruk jadi head
ll.insert_at_first("mangga")  # * mangga jadi head baru
ll.insert_at_first("manggis") # * manggis jadi head baru
ll.insert_at_last("apel")     # * apel masuk di paling akhir
ll.insert_at(2, "anggur")     # * anggur masuk pada index 2

# * Penghapusan data
ll.remove_first()  # * Hapus node pertama (manggis)
ll.remove_last()   # * Hapus node terakhir (apel)
ll.remove_at(1)    # * Hapus node pada index 1
ll.remove_at(1)    # * Hapus node pada index 1 lagi

# * Cetak hasil linked list
ll.print()

# * Cetak panjang linked list
print(ll.length())
