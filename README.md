

# Reflection

**1. What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?**
- JMeter berfokus untuk mengukur bagaimana aplikasi merespons saat menerima banyak permintaan secara bersamaan. JMeter digunakan untuk menganalisis performa sistem secara keseluruhan, seperti watku respons.
Sementara, IntelliJ Profiler lebih berfokus pada profiling kode dan analisis performa internal aplikasi. Profiling dapat digunakan untuk mengidentifikasi _method_ yang membutuhkan waktu eksekusi lama,
penggunaan CPU/memori yang tinggi, dan potensi kebocoran memori.

**2. How does the profiling process help you in identifying and understanding the weak points in your application?**
- Profiling membantu dengan memberikan data rinci tentang bagaimana aplikasi bekerja secara internal, seperti penggunaan CPU dengan menunjukkan
metode atau proses yang memiliki waktu eksekusi paling lama, pengalokasian memori dengan mengidentifikasi objek yang sering dibuat dan menyebabkan
pemakaian memori yang tinggi, dan lainnya.

**3. Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?**
- Ya, IntelliJ Profiler sangat efektif dalam menganalisis performa kode karena menyediakan visualisasi yang intuitif, seperti Flame Graph, Call Tree, dan CPU Usage, sehingga memudahkan dalam memahami permasalahan yang terjadi.
Selain itu, karena terintegrasi langsung dengan IntelliJ IDEA, dapat dengan cepat melihat sumber kode yang menyebabkan masalah tanpa perlu berpindah aplikasi.
IntelliJ Profiler juga mampu menganalisis berbagai aspek performa, termasuk penggunaan CPU, konsumsi memori, aktivitas thread, dan alokasi objek, sehingga sangat membantu dalam mengoptimalkan aplikasi.

**4. What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?**
- Tantangan yang dihadapi saat melakukan pengujian performa dan profiling adalah memahami dan melihat hasil profiling agar dapat melakukan refactoring pada permasalahan yang ditemukan dan setelah menemukan permasalahan
tersebut, saya harus melakukan refactoring pada permasalahan agar performa aplikasi menjadi lebih baik.

**5. What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?**
- Dengan menggunakan IntelliJ Profiler dapat mengidentifikasi bottleneck dengan cepat, menampilkan visualisasi performa aplikasi, mengintegrasikan langsung dengan IntelliJ IDEA, menganalisis terhadap memory leaks, dan 
meningkatkan efisiensi debugging.

**6. How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?**
-  Jika saya mengalami situasi ini, saya akan memeriksa kembali konfigurasi yang dilakukan pada JMeter dan memeriksa kembali hasil profiling yang saya dapatkan dari Intellij Profiler.

**7. What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?**
- Pada method `getAllStudentsWithCourses()` saya mengubah kode dengan menggunakan `studentCourseRepository.findAll()` sehingga seluruh data hubungan mahasiswa dan mata kuliah
dapat diperoleh dalam satu kali pemanggilan database. Selain itu, saya memanfaatkan HashMap untuk menyimpan ID mahasiswa, sehingga cukup dengan satu iterasi pada daftar StudentCourse, saya dapat langsung
mencocokkannya dengan mahasiswa yang sesuai dalam HashMap.
- Pada method `joinStudentNames()`, saya mengganti String menjadi StringBuilder yang memungkinkan manipulasi string tanpa membuat objek baru di setiap operasi,
sehingga lebih hemat memori dan meningkatkan efisiensi eksekusi.
- Pada method `findStudentWithHighestGpa()` saya melakukan perbaikan dengan menggunakan query langsung di repository.
- Untuk memastikan perubahan yang dilakukan tidak merusak fungsionalitas aplikasi, idealnya saya membuat unit test sebelum dan sesudah refactoring.













