# Template LaTeX AKPRO IME FTUI 

Template LaTeX ini dirancang untuk mempermudah pembuatan diktat. Template ini memberikan format untuk pendahuluan, soal, jawaban, dan pembahasan teori. 

---

## Cara Penggunaan

### Prasyarat

- Distribusi LaTeX (contoh: TeX Live, MikTeX).
- Editor yang direkomendasikan: Overleaf, VSCode dengan extention "Latex Worshop"

### Struktur Template

Dokumen ini terdiri dari bagian-bagian berikut:

1. **Informasi Pendahuluan**
   - `\tableofcontents` akan terisi otomatis berdasarkan bagian dan soal yang Anda tambahkan.
   - File `pendahuluan` berisi disclaimer serta kata pengantar, pastikan untuk merubah nama mata kuliah pada bagian ini. 
   
2. **Paket Ujian**
   - Setiap paket ujian diawali dengan `\section` dengan data soal masing-masing.

3. **Soal**
   - Gunakan environment `soal` untuk menambahkan soal. Penomoran dilakukan otomatis.

4. **Jawaban**
   - Gunakan environment `jawaban` untuk menambahkan jawaban untuk setiap soal.

5. **Pembahasan Teori**
   - Untuk pembahasan teori, gunakan lingkungan `teori*` yang telah diberikan.

---

### Commands dan Environments


#### 1. Placeholder

```latex
\placeholder[Text Placeholder]
```

- Memberikan peringatan jika placeholder belum diganti.
> [!WARNING]
> Pastikan Tidak ada placeholder yang belum diganti.

#### 2. Awal Tiap Paket Soal 

```latex
\newpage
\section{UAS Kalkulus 2024 Paket 1}
\begin{datasoal}
	Dosen            &: \placeholder[Nama Dosen] \\
	Jumlah Soal      &: \placeholder[Jumlah Soal] \\
	Waktu Pengerjaan &: \placeholder[Waktu Pengerjaan] \\
	Pengetikan Soal  &: \placeholder[Nama Pengetik] \\
	Pembahasan Soal  &: \placeholder[Nama Pembahas] \\
	Pengecek Jawaban &: \placeholder[Nama Pengecek]
\end{datasoal}
```

- Berisi informasi untuk setiap paket ujian.
- Ganti placeholder dengan data sebenarnya.

#### 3. Environment Soal

```latex
\begin{soal}
    % Masukkan soal di sini.
\end{soal}
```
- Bagian untuk menulis tiap soal
- Menambahkan sub-section pada daftar isi

#### 4. Environment Jawaban

```latex
\begin{jawaban}
    % Masukkan pembahasan di sini.
\end{jawaban}
```
- Bagian untuk menulis pembahasan dari soal
- Untuk jawaban diberi kotak dengan
  - ```\fbox{jawaban dalam kalimat}```
  - ```\boxed{jawaban matematika} ```
  - ```\Aboxed{jawaban matemaika dalam enviroment align} ```
> [!CAUTION]
> Pastikan kotak jawaban menggunakan command yang sesuai, jika tidak dapat menyebabkan compile error.


#### 5. Bagian Teori 

```latex
\begin{teori*}{Judul Teori}
   % Masukkan pembahasan teori atau formula di sini.
   \highlight{rumus penting}
\end{teori*}
```

- Menambahkan kotak khusus untuk dasar teori.
- Gunakan ```\highlight{ }``` untuk menandakan rumus penting, command ini dapat digunakan bagi tulisan dan matematika, tetapi tidak direkomendasikan jika didalam sebuah align 
> [!CAUTION]
> Jangan gunakan ```\highlight{ }``` jika terdapat ```&``` didalamnya, hal ini akan menyebabkan compile error.



---

## Contoh Penggunaan

```latex
\newpage
\section{UAS Kalkulus 2024 Paket 1}

\begin{datasoal}
	Dosen            &: Dr. Budi Tabudi \\
	Jumlah Soal      &: 3 \\
	Waktu Pengerjaan &: 60 menit \\
	Pengetikan Soal  &: Budi E'24 \\
	Pembahasan Soal  &: Bob E'24 \\
	Pengecek Jawaban &: Natan Biom'24
\end{datasoal}

\begin{soal}
    Hitung integral $\int x^2 \,\mathrm{d}x$.
\end{soal}

\begin{jawaban}
	\begin{teori*}{Integral Polinomial}
		Integral Polinomial dapat diselesaikan dengan rumus berikut:
		\begin{equation*}
			\highlight{\int x^n dx = \frac{x^{n+1}}{n+1} + C} \quad \text{Untuk $n \neq -1$}
		\end{equation*}
	\end{teori*}

	Nilai integral dapat ditentukan dengan: 
	\begin{align*}
		\int x^n dx &= \frac{x^{n+1}}{n+1} + C \\ 
		\Aboxed{\int x^2 \,\mathrm{d}x &= \frac{x^3}{3} + C}
	\end{align*}
\end{jawaban}


\begin{soal}
    Soal nomor dua
\end{soal}

\begin{jawaban}
    Jawaban soal nomor dua
\end{jawaban}
```

---


### Kustomisasi Lanjutan

- **Tambah Gaya Baru**: Modifikasi `macros.sty` atau `preamble.sty` untuk menambahkan `package` baru.

---

### Pemecahan Masalah

1. **Spasi Kurang atau Berlebih**:
   - Tambahkan `\vspace{n \baselineskip}` untuk menambahkan spacing kelipatan dari `\baselineskip`,
     	- n = bilangan rasional (dapat berupa negatif dan desimal)
```latex
% Environment yang menyebabkan spacing berlebih 
\end{...}
\vspace{-2\baselineskip}	
dan seterusnya 
```

---

### Kontribusi

Silakan beri saran atau laporkan masalah. 

---

### Penulis
Dibuat oleh **Kevin Imanuel Hutagaol** dan **Natano Juditya Sihan**.
