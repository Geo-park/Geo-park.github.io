<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Selamat Lebaran</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background: url('eid.webp') no-repeat center center fixed;
            background-size: cover;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            max-width: 500px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        input, button {
            margin-top: 10px;
            padding: 10px;
            width: 100%;
            font-size: 16px;
        }
        .ucapan-container img {
            max-width: 100px;
            display: block;
            margin: 10px auto;
        }
        .button-group {
            margin-top: 10px;
        }
        .button-group button {
            margin: 5px;
            padding: 10px;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Selamat Hari Raya Idul Fitri!</h1>
        <p>Masukkan nama Anda untuk mendapatkan ucapan spesial:</p>
        <input type="text" id="nama" placeholder="Masukkan nama Anda Huruf kecil semua">
        <button onclick="tampilkanUcapan()">Tampilkan Ucapan</button>
        <div id="ucapan" class="ucapan-container"></div>
    </div>

    <script>
        function tampilkanUcapan() {
            let nama = document.getElementById('nama').value.toLowerCase();
            let ucapanText;
            let imageSrc = "ss.jpg";
            
            switch (nama) {
                case "intan":
                    ucapanText = "SELAMAT LEBARAN<br><img src='" + imageSrc + "' alt='Lebaran Image'><br>Sorry ya kalau gua pernah masuk ig lu, suka nyebelin, suka kaya stalker lu, suka ngirimin video hansen, gak ngerti mood lu, ya intinya gua minta maaf dari hati terdalam. Jadi dimaafin ga?";
                    ucapanText += "<div class='button-group'><button onclick='jawabMaaf(\"iya\")'>Iya</button><button onclick='jawabMaaf(\"tidak\")'>Tidak</button></div>";
                    break;
                case "dwi":
                    ucapanText = "Selamat Lebaran<br><img src='" + imageSrc + "' alt='Lebaran Image'><br>Kalo ada salah maaf ya.";
                    break;
                case "mbul":
                    ucapanText = "Selamat Lebaran<br><img src='" + imageSrc + "' alt='Lebaran Image'><br>Sorry kalau gua pernah ngalahin lu, sebenernya gua g enak ngalahin lu. Janji nanti dikasih menang deh.";
                    ucapanText += "<br><img src='100.png' alt='Mbul Special Image'>";
                    break;
                default:
                    ucapanText = "Selamat Idul Fitri, " + nama + "!<br><img src='" + imageSrc + "' alt='Lebaran Image'><br>Mohon maaf lahir dan batin.";
            }
            
            document.getElementById('ucapan').innerHTML = ucapanText;
        }
        
        function jawabMaaf(jawaban) {
            let responseText;
            let imageSrc;
            if (jawaban === "iya") {
                responseText = "Makasih! Semoga kita bisa jadi diri yang lebih baik lagi! :)";
                imageSrc = "10.PNG";
            } else {
                responseText = "Yahh :( Semoga di lain waktu kita bisa ketemu lagi entah itu di kehidupan selanjutnya.";
                imageSrc = "8.jpeg";
                responseText += "<br>Sekarang masih marah g?";
                responseText += "<div class='button-group'><button onclick='jawabMarah(\"engga\")'>ENGGA</button><button onclick='jawabMarah(\"masih\")'>MASIH</button></div>";
            }
            document.getElementById('ucapan').innerHTML = "<p>" + responseText + "</p><img src='" + imageSrc + "' alt='Response Image'>";
        }

        function jawabMarah(jawaban) {
            let responseText;
            let imageSrc;
            if (jawaban === "engga") {
                responseText = "Yeay! Akhirnya, Makasih! Semoga kita bisa jadi diri yang lebih baik lagi! :) .";
                imageSrc = "10.PNG";
            } else {
                responseText = "Huft :( Maaf ya... :( Semoga di lain waktu kita bisa ketemu lagi entah itu di kehidupan selanjutnya.";
                imageSrc = "9.webp";
            }
            document.getElementById('ucapan').innerHTML = "<p>" + responseText + "</p><img src='" + imageSrc + "' alt='Final Response Image'>";
        }
    </script>
</body>
</html>
