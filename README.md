
## 📊 Analisis MANCOVA pada Data Adult Income

Repositori ini berisi implementasi dan analisis **Multivariate Analysis of Covariance (MANCOVA)** menggunakan dataset *Adult Income* dari UCI Machine Learning Repository. Analisis ini bertujuan untuk mengetahui pengaruh variabel sosio-ekonomi terhadap dua indikator keuangan utama—`capital.gain` dan `capital.loss`—dengan mengontrol efek usia (`age`) sebagai kovariat.

### 🎯 Tujuan Analisis

* Menilai pengaruh variabel independen `occupation` dan `income` terhadap gabungan `capital.gain` dan `capital.loss`.
* Mengendalikan variabel `age` sebagai kovariat agar pengaruh usia tidak mendistorsi hasil.
* Menentukan apakah perbedaan antar kelompok signifikan setelah mengontrol variabel kontinyu.

### 🧪 Hasil Utama

* Berdasarkan uji multivariat (Pillai's Trace, Wilks' Lambda, Hotelling-Lawley Trace, Roy's Largest Root), **terdapat pengaruh signifikan dari paling tidak satu variabel independen terhadap gabungan dua variabel dependen**, dengan p-value < 0.001.
* Uji ANOVA univariat menunjukkan bahwa:

  * `income` berpengaruh signifikan terhadap **kedua** variabel dependen (`capital.gain` dan `capital.loss`),
  * sedangkan `occupation` tidak signifikan secara univariat, tetapi berkontribusi secara multivariat.
* Setelah mengontrol `age`, tetap terdapat perbedaan yang signifikan dalam rata-rata gabungan antara `capital.gain` dan `capital.loss` berdasarkan setidaknya satu dari `occupation` atau `income`.

### 🧰 Tools & Libraries

Analisis dilakukan menggunakan bahasa **R** dengan bantuan library:

* `car` – untuk analisis MANCOVA dan uji ANOVA lanjutan
* `tidyverse` – untuk manipulasi data
* `ggplot2` & `ggpubr` – untuk visualisasi
* `MVN` – untuk menguji asumsi normalitas multivariat
* `biotools` – untuk uji Box’s M (homogenitas matriks kovarian)

