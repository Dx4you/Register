 How To Create A Form Register/Sign Up

 
 Cara Membuat Form Registrasi/Sign Up

# Name Files : index.html
A Code :
<code> <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Pendaftaran</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        .container {
            max-width: 500px;
            margin: 50px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h2 {
            text-align: center;
            color: #333;
        }
        .form-group {
            margin-bottom: 20px;
        }
        .form-group label {
            display: block;
            font-weight: bold;
            margin-bottom: 5px;
            color: #555;
        }
        .form-group input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-sizing: border-box;
        }
        .form-group input[type="submit"] {
            background-color: #4caf50;
            color: #fff;
            cursor: pointer;
            border: none;
        }
        .form-group input[type="submit"]:hover {
            background-color: #45a049;
        }
        .form-group input[type="submit"]:focus {
            outline: none;
        }
        .form-group input[type="text"]:focus,
        .form-group input[type="email"]:focus,
        .form-group input[type="password"]:focus {
            border-color: #4caf50;
            box-shadow: 0 0 5px #4caf50;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Form Pendaftaran</h2>
        <form action="proses_pendaftaran.php" method="post">
            <div class="form-group">
                <label for="nama">Nama:</label>
                <input type="text" id="nama" name="nama" required>
            </div>
            <div class="form-group">
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
            </div>
            <div class="form-group">
                <label for="password">Password:</label>
                <input type="password" id="password" name="password" required>
            </div>
            <div class="form-group">
                <input type="submit" value="Daftar">
            </div>
        </form>
    </div>
</body>
</html>
</code>

# 2 Name Files : proses_pendaftaran.php
Code : <code> <?php
// Cek apakah form telah disubmit
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // Ambil data dari formulir
    $nama = $_POST['nama'];
    $email = $_POST['email'];
    $password = $_POST['password'];

    // Susun data yang akan disimpan
    $data = "Nama: $nama\nEmail: $email\nPassword: $password\n";

    // Tentukan nama file untuk menyimpan data
    $file = "data_pendaftaran.txt";

    // Buka file (jika file tidak ada, akan dibuat baru)
    $file_handle = fopen($file, 'a'); // 'a' untuk mode append (menambahkan ke akhir file)

    // Tulis data ke dalam file
    fwrite($file_handle, $data);

    // Tutup file
    fclose($file_handle);

    // Redirect ke halaman sukses atau halaman lainnya
    header("Location: sukses.php");
    exit; // Penting: pastikan untuk keluar setelah redirect
}
?>
</code>

# 3 Name Files : sukses.php
Code : <code> <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pendaftaran Berhasil</title>
</head>
<body>
    <h1>Pendaftaran Berhasil</h1>
    <p>Terima kasih telah mendaftar!</p>
    <!-- Anda bisa tambahkan link atau konten lainnya di sini -->
</body>
</html>
</code>

# 4 Name Files : data_pendaftaran.txt ( To Check or Automatically Save Registration Data ) , ( Untuk Mengecek Atau Simpan Otomatis Data-Data Pendaftaran )

Follow For More Code
