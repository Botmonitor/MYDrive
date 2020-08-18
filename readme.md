Install program first, then add onedrive in setup after login.  
Instal program terlebih dahulu, dan tambahkan onedrive ke pengaturan setelah masuk.

# Deploy to Heroku  
Official: https://heroku.com  
Demo: https://herooneindex.herokuapp.com/  

How to Install: Click the button [![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/Botmonitor/MYDrive) to Deploy a new app, or create an app then deploy via connect to your github fork.  


# Deploy to Tencent Serverless Cloud Function (SCF 腾讯无服务器云函数)  
Official: https://cloud.tencent.com/product/scf  
DEMO: Tidak ada
Catatan: SCF memiliki batasan baru. Variabel lingkungan maksimum keseluruhan adalah 4KB, sehingga Anda dapat menambahkan hingga 4 disk.

Cara Memasang: Tidak Ada
  
Saat menambahkan disk jaringan, SCF tidak dapat merespons, dan penambahan akan gagal. Harap jangan hapus. Tambahkan yang sama lagi. 


# Deploy to Virtual Private Server (VPS)  
DEMO:  Tidak Ada
How to Install:  
    1.Start web service on your server (httpd or other), make sure you can visit it.  
    Mulai server web dan pastikan Anda dapat mengaksesnya.
    2.Make the rewrite works, the rule is in .htaccess file, make sure any query redirect to index.php.  
    Nyalakan fungsi pseudo-static (rewrite), aturan ada di file .htaccess, dan ngnix disalin darinya.Tujuan kita adalah membiarkan index.php menangani apa pun yang diakses.。  
    3.Upload code.  
    Unggah kodenya. 
    4.Change the file config.php can be read&write (666 is suggested).  
    Untuk membuat program file config.php dalam kode tersebut dapat dibaca dan ditulis, direkomendasikan chmod 666 config.php.
    5.View the website in chrome or other.  
    Kunjungi di browser.  


# Deploy to Huawei cloud Function Graph (FG 华为云函数工作流)  
Official: https://console.huaweicloud.com/functiongraph/  
DEMO: Tidak
Catatan: Di FG, ukuran keseluruhan variabel lingkungan adalah 2KB, jadi tambahkan paling banyak 2 disk.

Bagaimana cara meng-install:
1. Dalam daftar fungsi, klik di sebelah kanan untuk membuat fungsi
2. Masukkan nama, pilih bahasa runtime sebagai PHP7.3, klik Unggah file ZIP, pilih file, dan klik fungsi buat di sebelah kanan (file ZIP di sini tidak dapat langsung digunakan sebagai file ZIP yang diunduh dari Github. Setelah mendekompresi, Setelah menghapus folder luar, kompres ke ZIP.)
3. Buat pemicu: pilih API gateway, pilih Tidak ada untuk otentikasi keamanan, ubah batas waktu backend (milidetik) dari 5000 menjadi 30000, buat grup di atas, dan lainnya sedikit demi sedikit
4. Kunjungi url yang diberikan oleh pemicu dan mulai penginstalan
5. Klik nama pemicu pada antarmuka pemicu, lompat ke manajemen gateway API, lebih banyak URL di sebelah kanan, Anda dapat menambahkan nama domain khusus, setelah menyesuaikan nama domain, Anda masih memerlukan xxxx.com/fungsi nama untuk mengakses, klik edit di atas, 1 halaman tidak perlu diubah, klik Berikutnya, minta Path untuk diubah ke /, perhatikan bahwa mode pencocokan adalah pencocokan awalan, Metode APAPUN, lalu tidak perlu mengklik Berikutnya, klik Selesai sekarang, lalu buka terbitkan untuk menerapkannya  


# Deploy to Aliyun Function Compute (FC 阿里云函数计算)  
Official: https://fc.console.aliyun.com/  
DEMO:  Tidak

Bagaimana cara meng-install:
1. Fungsi baru - Fungsi HTTP
2. Pilih php7.2 untuk lingkungan operasi
3. Pilih anonim sebagai metode otentikasi pemicu. Dalam metode permintaan, klik DAPATKAN dan kemudian POSKAN. Ada 2 ini di kotak terakhir
4. Unggah kode
5. Klik di pelatuk, temukan konfigurasi nama domain kustom, klik Buka, buat, isi / * di jalur, dan opsi drop-down lainnya.
6. Kunjungi nama domain Anda dan mulai penginstalan


# Deploy to Baidu Cloud Function Compute (CFC 百度云函数计算)  
Official: https://console.bce.baidu.com/cfc/#/cfc/functions  
DEMO:  Tidak
Nama domain khusus perlu menggunakan gerbang API secara terpisah dan mencatatnya.

Bagaimana cara meng-install:
1. Dalam daftar fungsi, klik Buat Fungsi
2. Ubah metode pembuatan menjadi fungsi kosong, klik Berikutnya
3. Masukkan nama, pilih PHP7.2 saat dijalankan, dan klik Next
4. Trigger: drop down untuk memilih HTTP trigger, isi jalur URL / {filepath +}, pilih semua metode HTTP, authentication: no verification, klik submit
5. Masuk ke halaman pengeditan kode, ubah jenis edit untuk mengunggah fungsi paket ZIP, dan pilih file (file Zip di sini tidak dapat langsung digunakan sebagai file ZIP yang diunduh dari Github. Setelah mendekompresi, hapus folder luar dan kemudian kompres ke ZIP .),Mulai mengunggah  
6. Klik pemicu di sebelah kanan, salin dan kunjungi url yang disediakan untuk memulai instalasi


# Features 特性  
When downloading files, the program produce a direct url, visitor download files from MS OFFICE via the direct url, the server expend a few bandwidth in produce.  
下载时，由程序解析出直链，浏览器直接从微软Onedrive服务器下载文件，服务器只消耗与微软通信的少量流量。  
When uploading files, the program produce a direct url, visitor upload files to MS OFFICE via the direct url, the server expend a few bandwidth in produce.  
上传时，由程序生成上传url，浏览器直接向微软Onedrive的这个url上传文件，服务器只消耗与微软通信的少量流量。  
The XXX_path in setting is the path in Onedrive, not in url, program will find the path in Onedrive.  
设置中的 XXX_path 是Onedrive里面的路径，并不是你url里面的，程序会去你Onedrive里面找这个路径。  
LOGO ICON: put your 'favicon.ico' in the path you showed, make sure xxxxx.com/favicon.ico can be visited.   
网站图标：将favicon.ico文件放在你要展示的目录中，确保 xxxxx.com/favicon.ico 可以访问到。  
Program will show content of 'readme.md' & 'head.md'.  
可以在文件列表显示head.md跟readme.md文件的内容。  
guest up path, is a folder that the guest can upload files, but can not be list (exclude admin).  
游客上传目录（也叫图床目录），是指定一个目录，让游客可以上传文件，不限格式，不限大小。这个目录里面的内容不列清单（除非管理登录）。  
If there is 'index.html' file, program will only show the content of 'index.html', not list the files.  
如果目录中有index.html文件，只会输出显示html文件，不显示程序框架。  
Click 'EditTime' or 'Size', the list will sort by time or size, Click 'File' can resume sort.  
点击“时间”、“大小”，可以排序显示，点“文件”恢复原样。  

QQ Group: 943919989 (请看完上面的中英双语再加群，谢谢！)  
Telegram Group: https://t.me/joinchat/I_RVc0bqxuxlT-d0cO7ozw  
