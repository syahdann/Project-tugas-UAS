# Project-tugas-UAS

Nama : Muhammad Syahdan Junus
NIM  : 312210285
Kelas : TI.22.A3

from ensurepip import version
from os import stat, system
d_nama = []
d_nim = []
d_tugas = []
d_uts = []
d_uas =  []
d_akhir = []

def judul():
    print('=====================================')
    print('|          PROGRAM BIODATA          |')
    print('=====================================')

def menu():
    system('cls')
    judul()
    print('| 1. Tambah Biodata                 |')
    print('| 2. Lihat Biodata                  |')
    print('| 3. Ubah Biodata                   |')
    print('| 4. Hapus Biodata                  |')
    print('| 5. Keluar                         |')
    print('=====================================')
    pilih2 = input('Pilih Menu : ')

    if pilih2 == '1':
        tambah()
    elif pilih2 == '2':
        lihat()
    elif pilih2 == '3':
        ubah()  
    elif pilih2 == '4':
        hapus()
    elif pilih2 == '5':
        selesai()
    else:
        tidak = input('Menu Tidak Ada ')
        system('cls')
        menu()
def tambah():
    system('cls')
    judul()
    print('Tambah Data'.center(40))
    print('=====================================')

    nama = input('Masukkan Nama           : ')
    d_nama.append(nama)
    nim = int (input('Masukkan Nim            : '))
    d_nim.append(nim)
    tugas = int (input('Masukkan Nilai Tugas    : '))
    d_tugas.append(tugas)
    uts = int (input('Masukkan Nilai Uts      : '))
    d_uts.append(uts)
    uas = int (input('Masukkan Nilai Uas      : '))
    d_uas.append(uas)
    akhir = (tugas * 0.30) + (uts * 0.35) + (uas * 0.35)
    d_akhir.append(akhir)
    
    print('=====================================')
    print ('Data Tersimpan'.center(40))
    print('=====================================')
    kembali = input('Kembali [enter]')
    menu()
def lihat():
    system('cls')
    judul()
        
    for i in range (len(d_nama)):

        print('%d.  Nama                 : %s'%(i+0, d_nama[i]))
        print('    NIM Mahasiswa        : %d'%d_nim[i])
        print('    Nilai Tugas          : %d'%d_tugas[i])
        print('    Nilai UTS            : %d'%d_uts[i])
        print('    Nilai UAS            : %d'%d_uas[i])
        print('    Nilai Akhir          : %f'%d_akhir[i])
    kembali = input('Kembali Tekan [enter]')
    menu()
def ubah():
    system('cls')
    judul()
    def rubah():
        try:
            i = int (input('Inputkan ID : '))
            print('=====================================')
            
            if (i > len(d_nama[i])):
                print('')
            
            else:   
                namabaru = input('Nama                 : ')
                d_nama[i] = namabaru

                nimbaru = int (input('Masukkan NIM          : '))
                d_nim[i] = nimbaru

                tugasbaru = int (input('Masukkan Nilai Tugas    : '))
                d_tugas[i] = tugasbaru

                utsbaru = int (input('Masukan Nilai Uts          : '))
                d_uts[i] = utsbaru

                uasbaru = int (input('Masukan Nilai Uas          : '))
                d_uas[i] = uasbaru
                
                akhirbaru = (tugasbaru * 0.30) + (utsbaru * 0.35) + (uasbaru * 0.35)
                d_akhir[i] = akhirbaru

            print('=====================================')
            print ('Data Tersimpan'.center(40))
            print('=====================================')
            kembali = input ('Kembali Tekan [enter]')
            menu()  

        except (IndexError,ValueError):
            kembali = input("Input ID bukan angka/Data tidak ada [enter]") 
            ubah()
    rubah()
def hapus():
    system('cls')
    judul()
    def hapuss():
        try:
            print('Hapus Data'.center(40))
            print('=====================================')
            i = int(input('Masukkan ID : '))
            
            if (i > len(d_nama[i])):
                print('')
            else:

                d_nama.remove(d_nama[i])
                d_nim.remove(d_nim[i])
                d_tugas.remove(d_tugas[i])
                d_uts.remove(d_uts[i])
                d_uas.remove(d_uas[i])
                d_akhir.remove(d_akhir[i])
            print('-------------------------------------')
            print ('Data Berhasil Dihapus'.center(40))
            print('-------------------------------------')
            kembali = input ('Kembali Tekan [enter]')
            menu()

        except (IndexError,ValueError):
            kembali = input("Input ID bukan angka/Data tidak ada [enter]") 
            hapus()

    hapuss()
def selesai():
    exit()
menu()
