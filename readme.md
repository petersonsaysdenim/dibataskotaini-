Studi Kasus Penggunaan git pull dan git fetch
Untuk mencoba penggunaan git pull dan git fetch kita akan menggunakan repository belajar-git yang sudah dibuat di Github.

Repositori di Github
Repositori di Github
Saat ini sudah terdapat 14 kontributor di dalam repositori tersebut. Sedangkan pada repositori lokal, saya belum melakukan apa pun.

Ini perbedaan commit repo lokal dengan remote:

Perbedaan commit di repo remote dengan lokal
Perbedaan commit di repo remote dengan lokal
Pada repository remote sudah terjadi 48 commit, sedangkan pada lokal hanya 10 saja.

Sekarang saya akan melakukan sebuah commit di repository lokal. Saya akan mengubah file README.md menjadi seperti ini:

Git diff di lokal repositori
Jadi sekarang di repositori lokal ada 11 commit.

Lalu perintah yang mana yang harus kita gunakan untuk mengambil 48 commit di Github?

Tentu saja kita akan menggunakan git fetch, karena saya sudah melakukan perubahan di repo lokal.

git fetch origin master
Hasil fetch akan disimpan dalam branch origin/master.

Perintah git fetch
Kita bisa masuk ke branch origin/master dengan perintah git checkout:

git checkout origin/master
Lalu kita bisa lihat commit apa saja yang ada di sana dengan git log:

Git log origin/master
Ada dua branch dalam log tersebut:

master adalah branch master di lokal
origin/master adalah branch master di remote yang sudah kita fetch.
Apabila kita sudah yakin, kita bisa menggabungkan (merge) dua branch tersebut.

Caranya:

# pindah dulu ke branch master (lokal)
git checkout master
# merge branch
git merge master origin/master
Menggabungkan branch master dengan origin/master
Menggabungkan branch master dengan origin/master
Berhasil 🎉…

Coba lihat hasilnya dengan git log:

Git log setelah di-merge
Lalu Bagaimana Penggunaan Git Pull?
Perintah git pull digunakan saat kita tidak pernah melakukan commit apapun di repo lokal.

Cara kerja git pull:

Ambil semua commit dari repo remote
Gabungkan branch master (lokal) dengan origin/master (remote)
Selesai
Untuk mencoba git pull, saya akan mengubah file README.md dari Github.

Github diff
Artinya sekarang di repositori remote (Github) ada 1 commit baru.

Bagaimana cara mengambilnya dengan git pull?

Caranya:

Gunakan perintah ini.

git pull origin master
Maka semua commit terbaru dari branch origin/master di Github akan diambil ke lokal dan langsung digabungkan dengan branch master.

Mengunakan perintah git pull
Mengunakan perintah git pull
Mudah bukan…

Jadi, Kesimpulannya
Gunakan perintah git pull saat tidak ada commit yang pernah dilakukan di lokal. Sedangkan perintah git fetch digunakan kalau sudah ada commit yang dilakukan.

Penggunaan git fetch lebih aman, karena kita akan melakukan merge branch secara manual. Sehingga kita bisa terhindar dari bentrokan.

Perintah git pull biasanya digunakan untuk sync repo lokal dengan remote.

Jika kamu menggunakan vs Code, pada pojok kanan bawah ada ikon untuk sync repo. Ini juga mungkin saja menggunakan git pull.

Sync Repo
Silahkan baca: Cara Menggunakan Git pada Visual Studio Code


Create a new repository on GitHub. You can also add a gitignore file, a readme and a licence if you want
 Open Git Bash
Change the current working directory to your local project.
Initialize the local directory as a Git repository.
git init
Add the files in your new local repository. This stages them for the first commit.
git add .
 Commit the files that you’ve staged in your local repository.
git commit -m "initial commit"
 Copy the https url of your newly created repo
In the Command prompt, add the URL for the remote repository where your local repository will be pushed.

git remote add origin remote repository URL

git remote -v
 Push the changes in your local repository to GitHub.

git push -f origin master
That’s all
<<<<<<< HEAD



#…or create a new repository on the command line
#echo "# nophising" >> README.md#git init
#git add README.md
#git commit -m "first commit"
#git branch -M main
#git remote add origin https://github.com/petersonsaysdenim/nophising.git
#git push -u origin main


#…or push an existing repository from the command line
#git remote add origin https://github.com/petersonsaysdenim/nophising.git
#git branch -M main
#git push -u origin main

=======
>>>>>>> 39445a91bb5f97787152e5ccad974feaa560421f
