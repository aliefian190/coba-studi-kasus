#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Struktur data untuk menyimpan informasi film
typedef struct {
    char judul[100];
    char genre[50];
    int durasi;
} Film;

// Struktur data untuk menyimpan informasi studio
typedef struct {
    int nomor;
    Film film;
} Studio;

// Struktur data untuk menyimpan informasi bioskop
typedef struct {
    char nama[100];
    Studio studio[5]; // Misalkan ada 5 studio di setiap bioskop
    float hargaTiket;
    char jadwal[7][20]; // Misalkan ada 7 hari dalam seminggu
} Bioskop;

int main() {
    // Inisialisasi data bioskop
    Bioskop royalPlaza;
    strcpy(royalPlaza.nama, "Royal Plaza");
    royalPlaza.hargaTiket = 45000; // Harga tiket di Royal Plaza
    strcpy(royalPlaza.jadwal[1], "Senin: sinden gaib");
    strcpy(royalPlaza.jadwal[2], "Senin: lampir");
    strcpy(royalPlaza.jadwal[3], "Senin: agak laen");
    strcpy(royalPlaza.jadwal[4], "Senin: munkar");
    // Informasi studio
    royalPlaza.studio[0].nomor = 1;
    strcpy(royalPlaza.studio[0].film.judul, "Film A");
    strcpy(royalPlaza.studio[0].film.genre, "horor");
    royalPlaza.studio[0].film.durasi = 110;

    // Lanjutkan inisialisasi untuk pusat perbelanjaan lainnya seperti Ciputra World, Tunjungan Plaza, dst.

    // Menampilkan informasi bioskop
    printf("Informasi Bioskop:\n");
    printf("Nama: %s\n", royalPlaza.nama);
    printf("Harga Tiket: Rp %.2f\n", royalPlaza.hargaTiket);
    printf("Jadwal:\n");
    for (int i = 0; i < 7; i++) {
        printf("%s\n", royalPlaza.jadwal[i]);
    }
    printf("Informasi Studio:\n");
    printf("Studio %d - Film: %s, Genre: %s, Durasi: %d menit\n", royalPlaza.studio[0].nomor, royalPlaza.studio[0].film.judul, royalPlaza.studio[0].film.genre, royalPlaza.studio[0].film.durasi);

    // Lanjutkan untuk menampilkan informasi studio lainnya

    return 0;
}
