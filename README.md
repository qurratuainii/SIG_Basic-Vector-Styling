# SIG_Basic-Vector-Styling

*Tutorial Basic Vector Stayling

1. Download terlebih dahulu file globalpowerplantdatabasev120.zip dan ne_10m_land.zip

2. Buka ne_10m_land.zip. Pada panel Browser QGIS, cari direktori tempat mengesktark data. Klik file ne_10m_land lalu pilih ne_10m_land.shp seret ke layar kanvas (*Gambar 1*)

3. Kita akan mendapatkan layer baru ne_10m_land ditambahkan ke panel layers. Klik Open data source pada bilah alat sumber data atau bisa menggunakan pintasan keyboard Ctrl+L (*Gambar 2*)

4. Pada jendela Data Source Manager, alihkan ke tab Delimited Text di sebelah nama file terdapat direktori tempat mengestrak file globalpowerplantdatabasev.120.zip. Lalu pilih file tersebut maka QGIS akan otomatis mendeteksi bidang pembatas dan geometri. Lalu biarkan Geometry default EPSG:4326 - WGS84. Kik Add lalu tutup (*Gambar 3*)

5. Pada layer baru global_power_point_database akan ditambahkan ke panel Layers dan akan melihat titik-titik yang mewakili pembangkit listrik di kanvas. Klik Open the Layer Styling panel pada bagian atas panel Layers (*Gambar 4*)

6. Panel Layer Styling akan terbuka di sebelah kanan. Lalu pilih layer ne_10m_land. Ini akan menjadi layer dasar sehingga kita dapat menjaga gaya minimalis agar tidak menganggu. Klik simple fill lalu scroll ke bawah, lalu pilih warna yang diinginkan. Klik drop-down di sebelah Stroke color dan pilih transparent Stroke. Ini akan mengatur garis besar poligon tanah menjadi transparan (*Gambar 5*)

7. Selanjutnya pilih layer global_power_plant_database. Klik pada simple marker dan scroll ke bawah. Pilih marker segitiga (*Gambar 6*)

8. Lalu sroll ke atas lalu pilih warna sesuai keinginan. Teknik kartografi yang berguna adalah memilih versi warna isi yang sedikit lebih gelan sebagai warna stroke. Klik Data defined ovveride dan pilih edit (*Gambar 7*)

9. Masukkan ekspresi berikut untuk mengatur warna menjadi bayangan 30% lebih gelap dari warna isian lalu klik OK (*Gambar 8*)

10. Kita akan melihat tombol ovveride yang ditentukan data di sebelah Stroke Color telah berubah menjadi kuning menunjukkan bahwa properti ini dikendalikan oleh ovveride. Render simbol single symbol dari layer pembangkit listrik tidak terlalu berguna. Itu tidak menyampaikan banyak informasi kecuali lokasi pembangkit listrik. Klik drop-down Symbology dan pilih Categorized renderer (*Gambar 9*) (*Gambar 10*)

11. Layer global_power_plant_database berisi atribut yang menunjukkan bahan bakar utama yang digunakan di setip pembangkit listrik. Kita dapat membuat gaya di mana setiap jenis baha bakar yang unik ditampilkan dalam warna yang berbeda. Pilih primary fuel sebagai kolom. Klik classify. Kita akan melihat beebrapa kategori dan rendering peta berubah (*Gambar 11*)

12. Pada lapisan ini berisi terlalu banyak kategori untuk dapat ditafsirkan peta. Pendekatan yang lebih baik adalah mengelompokkan jenis kategori bahan bakr tertentu dan mengurangi jumlah kelas. Pilih Rule-based, lalu pilih semua kecuali 3 bahan yaitu bahan bakar terbarukan, bahan bakar tidak terbarukan dan lainnya. Setelah dipilih, klik tombol hapus (*Gambar 12*)

13. Pilih aturan yang tersisa dan klik edit aturan saat ini (*Gambar 13*)

14. Masukkan bahan bakar terbarukan sebagai label. Klik tombol eksprei di sebelah filter (*Gambar 14)

15. Pada Expression String Builder, masukkan ekspresi berikut "primary_fuel" IN ('Biomass', 'Geothermal', 'Hydro', 'Solar', 'Wind', 'Storage', 'Wave and Tidal') dan klik OK. Di sini kami mengelompokkan beebrapa kategori energi terbarukan ke dalam satu kategori (*Gambar 15*)

16. Scroll ke bawah dan Klik simple marker. Lalu pilih warna yang sesuai. Setelah selesai, klik tombol kembali (*Gambar 16*)

17. Kita akan melihat satu aturan diterapkan pada layer untuk kategori Renewable fueel. Klik kanan baris dan pilih copy. Klik kanan dan pilih paste. Salinan aturan yang ada akan ditambahkan. Pilih baris yang baru ditambahkan dan klik edit current rule (*Gambar 17*)

18. Masukkan Non-renewable fuel sebagai label. Klik tombol ekspresi di sebelah filter (*Gambar 18*)

19. Dalam Expression String Builder dialog, masukkan ekspresi berikut "primary_fuel" IN ('Coal', 'Gas', 'Nuclear', 'Oil', 'Petcoke') lalu klik OK (*Gambar 19*)

20. Scroll kebawah dan klik Simple marker. Pilih warna yang sesuai. Setelah selesai, klik tombol kembali

21. Ulangi proses Copy/Paste untuk menambahkan aturan ketiga. Pilih dan klik edit current rule (*Gambar 20*)

22. Kategori udah selesai. Kita akan melihat tampilan yang jauh lebih bersih yang menunjukkan distribusi sumber bahan bakar terbarukan vs tidak terbarukan oleh pembangkit listrik dan distribusinya di seluruh negara. Kita bisa menambahkan variabel lain ke styling. Kita dapat menunjukkan ukuran yang proporsional dengan kapasitas pembangkit listrik masing-masing pembangkit. Klik kanan aturan bahan bakar terbarukan dan pilih change size (*Gambar 21*)

23. Klik tombol defines override yang disebelah ukuran. Piliha dan edit (*Gambar 22*)

24. Karna kapasitas pembangkit listrik sangat bervariasi, cara efektif untuk mendapatkan ukuran yang kecil menggunakan fungsi log10. Kita dapat bereksperimen dengan ekspresi yang berbeda untuk sampai pada yang terbaik untuk visualisasi. Masukkan ekspresi berikut log10("capacity_mw") + 1 dan Klik OK. lakukan juga ke yang lainnya (*Gambar 23*)

25. Melihat visualisasi akhir, kita dapat langsung melihat pola di dataset. (*Gambar 24*)

