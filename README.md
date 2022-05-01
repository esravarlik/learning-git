# learning-git

# Senaryo 1
Uzak bir repodan kodu indirmek için;
1. Github code kısmındaki url kopyalanır.
2. Intelij Idea terminal kısmına git clone (kopyalanan url)

---

Bu dosyada değişiklik yaptığımızı varsayalım.
1. git status (değişiklik yaptığımız dosyaları gösterir.)
2. git add . (dosyalar stage denilen ara bir konuma atıyor.)
3. git commit -m "yapılan degisiklik hakkında mesaj"
Uzak sunucuya göndermek içinse;
4. git push
Gönderme işlemi tamamlandı.

---

# Senaryo 2
Uzak sunucuda içi boş bir repo oluşturalım.
1. git init
2. git remote add origin (uzak repo url)
3. git status
4. git add .
5. git commit -m "initial commit"
6. git push (git push --set-upstream origin master)

kullanıcı adı, şifre
Gönderme işlemi tamamlandı.
