# Fragment

Class fragment memiliki kode yang terlihat hampir seperti Activity. Fragment berisi method callback mirip dengan Activity, seperti onCreate (), onStart (), onPause (), dan OnStop (). Siklus hidup dari fragment berhubungan dengan siklus hidup Activity, berikut tahapan siklus hidup fragment yang berkaitan dengan siklus hidup dari activity.

![](https://github.com/WahyuAdeCahaya/gambar/blob/master/fragmen%20cycle.jpg)

Berikut penjelasan tahapan di siklus hidup(LifeCycle) dari gambar diatas.
1. Activity onCreate() dipanggil, dimana activity dapat mengatur tampilan dengan menggunakan method setContentView().
2. onAttach() dipanggil setelah fragment dikaitkan dengan activity. Fragment mendapat refrensi ke objek activity yang dapat digunakan sebagai konteks.
3. onAttachFragment dipanggil oleh activity untuk menotifikasi activity bahwa fragment telah di attach.
4. onCreate () dipanggil ketika saat dibuat fragment.
Apa yang membedakan oncreate() di activity dan Oncreate di fragment ?
Pada oncreate() di Activity, Kita bisa gunakan setContentView() dan menghubungkan dengan tampilan (UI), tapi pada Oncreate() di fragment seharusnya kita tidak mengakses element UI dari fragment karena Activity Oncreate() mungkin belum selesai,namun, kita bisa membuat backgroud thread untuk membuat operasi lebih lama.
5. Method OnCreateView() dipanggil dalam fragment, disinilah kita dapat menautkan layout fragment dengan objeknya.
6. onActivityCreated() dipanggil setelah method activity onCreate() selesai. jadi disini kita dapat mengakses element UI melalui method ini.
7. onStart() dipanggil di dalam activity
8. onStart() dipanggil di dalam fragment
9. onResume() dipanggil di dalam activity
10. onResume() dipanggil di dalam fragment
Pada dalam kotak merah, ini merepresentasikan method yang dipanggil untuk setiap fragment. Untuk setiap fragment method 3,4,5 dipanggil dan akhiri dengan method 6.

Sekarang kita lihat kasus dimana fragment akan dihancurkan (destroyed).

![](https://github.com/WahyuAdeCahaya/gambar/blob/master/destroy.jpg)

1. onPause() dipanggil di dalam fragment.
2. onPause() dipanggil di dalam activity
3. onSaveInstanceState () digunakan untuk menyimpan informasi fragment dalam objek Bundle.
4. onSaveInstanceState () digunakan untuk menyimpan informasi activity dalam objek Bundle.
5. onStop() dipanggil di dalam fragment.
6. onStop() dipanggil di dalam Activity.
7. onDestroyView () dipanggil setelah hirarki view fragment tidak lagi dapat diakses.
8. onDestroy () dipanggil setelah fragment tidak digunakan, masih ada objek java melekat pada activity.
9. onDestroy () dipanggil di dalam activity.
10.onDetach () fragment tidak terikat dengan activity, dan tidak memiliki hirarki view lagi.

![](https://github.com/WahyuAdeCahaya/gambar/blob/master/fragmen1.jpg)
![](https://github.com/WahyuAdeCahaya/gambar/blob/master/fragmen2.jpg)
