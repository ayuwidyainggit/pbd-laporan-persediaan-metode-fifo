

*PROYEK BASIS DATA*
======================================================================================================================

a. Nama Aplikasi
APLIKASI BUKU PEMBANTU HUTANG

b. Desripsi:
- Pokok Masalah :
Membangun aplikasi perhitungan hutang dari masing masing suplier.

- Batasan masalah :
1. Aplikasi ini digunakan untuk mengisi data hutang dari masing-masing suplier.
2. Aplikasi yang dihasilkan berupa laporan hutang per periode

c. Pembuat :
Ayu Widya Inggit
D3 KA - 163210012

d. Development Tools
Java Script, Express, MariaDB

e. Instalasi Development Tools
node JS, mariaDB, Virtual Studio Code, express

f. Cara  Menjalankan
1. mengisi data suplier terlebih dahulu dengan isi:
   - id_suplier(PK)
   - nama_suplier
   - alamat_suplier
 
2. mengisi data hutang 
  - id_hutang (PK)
  - id_suplier (FK)
  - tanggal hutang
  


g. Lisensi
nodeJS: https://nodejs.org/en/
mongoDB :
 https://www.quora.com/Where-can-I-find-MongoDB-for-a-32bit-windows-installer
 https://www.mongodb.com/dr/fastdl.mongodb.org/win32/mongodb-win32-i386-3.2.14-signed.msi/download
 
virtual studio code :
https://code.visualstudio.com/Download



PROGRESS
1. routing 

const express = require('express')
const app = express()

app.get('/', (req, res) => res.send('Hello World!'))
 app.route('/pers')
  .get(function (req, res) {
    res.send('Get a random suplier')
  })
  .post(function (req, res) {
    res.send('Add a data_sup')
  })
  .put(function (req, res) {
    res.send('Update suplier')
  })
  

app.listen(3000, () => console.log('Example app listening on port 3000!'))

2. membuat form data suplier
<!DOCTYPE html>
<html>
	<head>
		<title>form data suplier </title>
		<link rel="styleshet" type="text/css" href="style.css">
	</head>
	<body>
		<center><h2>DAFTAR SUPLIER</h2></center>
		<div class="login">
			<form action="#" method="POST" onSubmit="validasi()">
				<div>
					<label>ID SUPLIER:</label>
					<input type="text" name="id_sup" id="id_sup" />
				</div>
				<div>
					<label>NAMA SUPLIER:</label>
					<input type="text" name="nama" id="nama" />
				</div>
				<div>
					<label>ALAMAT:</label>
					<textarea cols="40" rows="5" name="alamat" id="alamat"></textarea>
				</div>
				<div>
					<input type="submit" value="daftar" class="tombol">
				</div>
			</form>
		</div>
	</body>
	<script type="text/javascript">
		function validasi() {
			int id_sup = document.getElementById("no_sup").value;
			var nama = document.getElementById("nama").value;
			var alamat = document.getElementById("alamat").value;
			if (id_sup !="" && nama !="" && alamat !="") {
				return true;
			}else{
				alert('Anda harus mengisi dengan lengkap !');
			}
		}
	</script>
</html>

