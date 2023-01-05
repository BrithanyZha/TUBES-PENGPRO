# TUBES-PENGPRO
tugas besar pengenalaan pemrograman

#membuat list 
inputan = []
for x in openfile:
    n = x.split()
    inputan.append(n)
#close file
openfile.close()

#membuat dictionary
daftar_poin = {}
for z in inputan:
#membuat variabel pertiap index
    Pemain_Putih = z[0]
    Pemain_Hitam = z[1]
    skor = z[2]

# memisahkan skor putih dengan skor hitam
    Split_skor = skor.split("-")

#skor putih dan skor hitam
    skor_putih = Split_skor[0]
    skor_hitam = Split_skor[1]

#mengubah skor nilai 1/2 menjadi 0.5 
    #pengkondisian untuk skor putih
    if skor_putih == "1/2":
        skor_putih = 0.5
    #pengkondisian untuk skor hitam
    if skor_hitam == "1/2":
        skor_hitam = 0.5
    
    #casting nilai skor menjadi float
    skor_putih = float(skor_putih)
    skor_hitam = float(skor_hitam)

#membuat pengkondisian agar nilai skor yang ada di daftar poin terupdate
    #skor putih
    if Pemain_Putih in daftar_poin:
        daftar_poin[Pemain_Putih] =  daftar_poin[Pemain_Putih] + skor_putih
    else:
        daftar_poin[Pemain_Putih] = skor_putih
    #skor Hitam
    if Pemain_Hitam in daftar_poin:
        daftar_poin[Pemain_Hitam] =  daftar_poin[Pemain_Hitam] + skor_hitam
    else:
        daftar_poin[Pemain_Hitam] = skor_hitam



#membuat fungsi pemain
def pemain(dct):
    return len(dct)


#membuat fungsi  juara 
def  juara (dct):
    #membuat list untuk value dan key
    list_value = list(dct.values())
    list_key = list(dct.keys())
    #menggunakan fungsi max untuk mencari poin tertinggi
    fungsi_max = max(list_value)
    #mencari index dari poin tertinggi
    cari_index = list_value.index(fungsi_max)
    #mencari pemain dengan index yang telah ditemukan
    cari_key = list_key[cari_index]
    return cari_key


#menampilkan dictionary 
print(daftar_poin)
#memanggil fungsi permain
panggil_fungsi_pemain = pemain(daftar_poin)
print("Jumlah pemain adalah", panggil_fungsi_pemain)
#memanggil fungsi juara
panggil_fungsi_juara = juara(daftar_poin)
print("Pemain dengan poin tertinggi adalah", panggil_fungsi_juara)





