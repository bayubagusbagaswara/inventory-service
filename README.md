# Inventory Service

1. Running Docker Compose
- docker compose up -d

# Access MySQL via terminal
- mysql -h localhost -P 3307 -u root -p

# Penjelasan Volume pada docker-compose
Dalam file docker-compose.yml, bagian volumes digunakan untuk melakukan mounting antara direktori atau file pada host (komputer lokal) dengan container Docker. Berikut adalah kegunaan dari masing-masing baris yang Anda sebutkan:

./docker/mysql/data:/var/lib/mysql:

Ini melakukan mounting direktori ./docker/mysql/data yang ada di host (komputer lokal) ke dalam container pada direktori /var/lib/mysql.
Kegunaannya adalah untuk menyimpan data database MySQL di luar container, yaitu di host. Dengan cara ini, data tetap ada meskipun container dihapus atau dimulai ulang. Direktori /var/lib/mysql di dalam container adalah lokasi default di mana MySQL menyimpan semua datanya.
./mysql/init.sql:/docker-entrypoint-initdb.d/init.sql:

Ini melakukan mounting file ./mysql/init.sql yang ada di host ke dalam container pada direktori /docker-entrypoint-initdb.d/init.sql.
Kegunaannya adalah untuk menginisialisasi database saat container pertama kali dijalankan. File init.sql akan dieksekusi oleh MySQL saat container dimulai. Ini biasanya digunakan untuk menjalankan skrip SQL awal, seperti pembuatan tabel atau pengisian data awal.
Secara keseluruhan, penggunaan volumes ini memberikan fleksibilitas dalam mengelola data persisten dan konfigurasi awal pada container Docker.