Analisa yang dilakukan untuk monitoring operasi mesin cuci adalah melalui analisis getaran menggunakan sensor SW420 dan ESP8266 (Wemos D1 Mini)

Parameter uji coba:
- Operasi mesin cuci pada mode Spin+Drain selama 12 menit
- Sensor diletakkan pada bodi mesin cuci
- Pengamatan terhadap getaran dilakukan mulai dari buka/tutup pintu mesin cuci --> memilih mode --> tekan start --> proses berjalan --> End --> buka/tutup pintu mesin cuci
- Karakteristik getaran yang timbul pada mesin cuci beroperasi diamati untuk menentukan logika status IN USE, PROCESS, dan AVAILABLE
- Perubahan status berdasarkan Variabel sbb: getaran yang muncul/hilang, rentang waktu, dan kontinuitas getaran
- rentang waktu 0–60 detik getaran → IN USE; >60–150 detik getaran → PROCESS; >150 detik tanpa getaran → AVAILABLE dan hitungan getaran direset

Status ketika mesin cuci beroperasi pada mode Spin+Drain selama 12 menit:
- Status IN USE muncul pada saat di awal dan di akhir pencucian. 
- Status IN USE juga muncul pada saat kondisi Idle ketika mesin cuci masih beroperasi
- Status PROCESS muncul ketika getaran terjadi secara kontinyu
- Status AVAILABLE muncul pada saat mesin tidak beroperasi, dan ketika ada getaran dari Buka/Tutup pintu mesin cuci (gap getaran lama)

Implementasi pada aplikasi:
- Status IN USE & PROCESS mengindikasikan bahwa mesin cuci sedang beroperasi
- Status AVAILABLE menunjukkan bahwa mesin cuci tidak operasi
- Status AVAILABLE juga mengindikasikan jika ada getaran yang muncul pada saat buka/tutup pintu mesin cuci dengan gap getaran yang lama
