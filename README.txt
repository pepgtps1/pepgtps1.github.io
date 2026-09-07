ZIPPYPS GTPS WEB — Firebase + Realtime + Purchase Approval

1. Firebase
- Buat project di Firebase.
- Authentication > Sign-in method > aktifkan Email/Password.
- Firestore Database > Create database.
- Di Project settings > Your apps, ambil Firebase Web config.
- Edit index.html dan isi firebaseConfig.
- Buat akun owner ZIPPYPS lewat Sign Up, lalu ambil UID dari Firebase Authentication.
- Isi OWNER_UID di index.html dan UID yang sama pada firestore.rules.
- Publish/deploy ulang setelah rules diubah.

2. Cara akun tersimpan online
- Firebase Authentication menyimpan akun email/password.
- Firestore users/{UID} menyimpan username, role, dan titles.
- Data tetap ada saat user login dari perangkat lain.

3. Role realtime
- Owner mengubah role dari panel Profile.
- Profil memakai onSnapshot, jadi perubahan role/title akan tampil realtime.

4. Sistem pembelian
- User login -> klik BUY -> website membuat purchaseOrders dengan status pending.
- User diarahkan ke WhatsApp dengan ID order.
- Owner melihat pesanan pending di PURCHASE APPROVAL.
- APPROVE: role/title diberikan ke akun secara realtime.
- REJECT: order ditandai rejected dan asset tidak diberikan.
- Pembelian TIDAK otomatis memberikan role/title.

5. Firestore rules
- Ganti placeholder UID owner di firestore.rules.
- Rules mencegah member mengubah role/title dirinya sendiri.

Catatan: Untuk produksi, gunakan Firebase Hosting atau hosting HTTPS. Jangan menaruh password atau secret service-account di frontend.
