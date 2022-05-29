# Muhammad Ghani Taufiqurrahman Atmaja
# 5025201110
# Kelas D

## No 1
Seorang peneliti melakukan penelitian mengenai pengaruh aktivitas 𝐴 terhadap
kadar saturasi oksigen pada manusia. Peneliti tersebut mengambil sampel
sebanyak 9 responden. Pertama, sebelum melakukan aktivitas 𝐴, peneliti mencatat
kadar saturasi oksigen dari 9 responden tersebut. Kemudian, 9 responden tersebut
diminta melakukan aktivitas 𝐴. Setelah 15 menit, peneliti tersebut mencatat kembali
kadar saturasi oksigen dari 9 responden tersebut. Berikut data dari 9 responden
mengenai kadar saturasi oksigen sebelum dan sesudah melakukan aktivitas 𝐴

![image](https://user-images.githubusercontent.com/88977654/170876430-5bcbd62c-9989-4c8c-b9ee-e430290fd297.png)

Berdasarkan data pada tabel diatas, diketahui kadar saturasi oksigen dari
responden ke-3 ketika belum melakukan aktivitas 𝐴 sebanyak 67, dan setelah
melakukan aktivitas 𝐴 sebanyak 70.

### a =>
```r
org.ke = c(seq(1:9))
o2.sblm = c(78, 75, 67, 77, 70, 72, 78, 74, 77)
o2.ssdh = c(100, 95, 70, 90, 90, 90, 89, 90, 100)
data = data.frame(org.ke,o2.sblm, o2.ssdh)
n = 9

selisih = data$o2.ssdh - data$o2.sblm
standardev = sd(selisih)
standardev
```
### b =>
```r
xbar = mean(selisih)
m = 0
tstat =( (xbar - m) / (standardev / sqrt(n)))
pvalue = 2 * pt(-abs(tstastistik), df=n-1)
pvalue
```
### c =>
```r
t.test(x=data$o2.ssdh, y=data$o2.sblm,
       alt= "two.sided",
       m = 0, pair= TRUE, var.equal = TRUE,
       conf.level = 0.95)
```

## No 2
### A
Setuju dikarena setelah diujicoba ternyata tolak H0 dengan begitu rata-rata mobil dikemudikan per tahun lebih dari 20.000km

### B
```r
library(BSDA)
tsum.test(mean.x = 23500, sd(3900), n.x = 100)
```
Output dari z-test hipotesis alternatif (true mean) lebih besar dari 20000 atau H1 diterima sehingga dianggap benar.

### C
P-value dari uji z-test adalah 2.2e-16 (mendekati 0), dengan begitu hasil p-value tersebut hipotesis  yang diawal dapat ditolak dan H1 diterima.

## No 3
### A H0 dan H1
# H0 : rata-rata Bandung - rata-rata Bali = 0
# H1 : rata-rata Bandung - rata-rata Bali != 0

### B 
![image](https://user-images.githubusercontent.com/77779184/170880386-da7915ec-68ed-4ce0-8ff9-d9d40db72187.png)

### C
Uji dengan menggunakan df=2
![image](https://user-images.githubusercontent.com/77779184/170880444-bdb44cc7-51bc-4586-b65f-dfd4d1fc9d73.png)

### D
Diperoleh sebagai berikut
![image](https://user-images.githubusercontent.com/77779184/170880501-f58ec0ba-8000-49fb-8644-cba4fa1e71d2.png)

### E
Karena p-value lebih kecil dari a, dengan begitu hipotesis pertama ditolak atau dapat disimpulkan rata-rata saham di Bandung berbeda dengan yang ada di Bali

### F
Tingkat keyakinan 95% tidak terdapat perbedaan rata-rata saham antara kedua perusahaan

## No 4
### A
Didapatkan group 1 =>
![image](https://user-images.githubusercontent.com/77779184/170881535-8463408a-eaf6-4d4e-ac56-3e4961e11292.png)

Didapatkan group 2 =>
![image](https://user-images.githubusercontent.com/77779184/170881543-c8fc6d42-2d6d-4e00-8789-e26f0c48d88e.png)

Didapatkan group 3 =>
![image](https://user-images.githubusercontent.com/77779184/170881557-0331f05e-a56d-404c-be91-5c74c97b8559.png)

### B
Didapatkan => 

![image](https://user-images.githubusercontent.com/77779184/170881577-24a81c9f-0e12-4390-a368-c2d4d47942a6.png)

### C
Didapatkan dari model 1

![image](https://user-images.githubusercontent.com/77779184/170881624-d1f972c4-c3cc-432e-b2d3-eb8bbb574f0f.png)

### D
Berdasarkan hasil yang didapatkan pada poin sebelumnya, pada taraf uji 5% didapatkan nilai p-value sebesar 0.0013. Maka, terdapat perbedaan panjang kucing yang signifikan berdasarkan grupnya.

### E
![image](https://user-images.githubusercontent.com/77779184/170881709-7e183d4d-6a23-4481-84b2-dcc0f696eee6.png)
Dari hasil uji Tukey, dapat dilihat kombinasi dari kelompok mana yang secara signifikan berbeda. Jika menggunakan 𝛼 = 5%, perbedaan panjang kucing yang signifikan adalah grup 2 (Kucing Hitam) terhadap grup 1 (Kucing Oren) dan grup 3 (Kucing Putih).

### F
Didapatkan visualisasi ggplot2 =>
![image](https://user-images.githubusercontent.com/77779184/170881766-0abb1856-fd2e-47c6-b264-39551a602a13.png)


## No 5
### A
Plot sederhana =>
```r
GTL <- read_csv("data_soal_5.csv")
head(GTL)
str(GTL)

qplot(x = Temp, y = Light, geom = "point", data = GTL) + facet_grid(.~Glass, labeller = label_both)
```
![image](https://user-images.githubusercontent.com/77779184/170882102-a9883107-f3c3-4f90-8d6e-349394f35b24.png)

### B
Uji Anova two way
![image](https://user-images.githubusercontent.com/77779184/170882219-d0e2630f-c493-49d2-a34c-10650b5e0c1b.png)
![image](https://user-images.githubusercontent.com/77779184/170882221-f2797b04-2e38-44c1-b203-1c566e324c62.png)

### C
Menampilkan tabel dengan mean dan standar  deviasi
![image](https://user-images.githubusercontent.com/77779184/170882279-90a3734c-c359-4f87-b441-25b3a91823a3.png)

### D
Uji Tukey
![image](https://user-images.githubusercontent.com/77779184/170882308-3609d871-f9f1-4a00-b514-7d0524f9321c.png)
![image](https://user-images.githubusercontent.com/77779184/170882318-5a64bc79-ca5a-4e4f-8743-730bca1cd669.png)

### E
PLot untuk visualisasi Data
![image](https://user-images.githubusercontent.com/77779184/170882353-331c2b74-b610-4235-8bdf-72d9c1d80d09.png)
![image](https://user-images.githubusercontent.com/77779184/170882361-2e733e37-dc87-42b8-9dfc-528ca678a9a7.png)


