# learning-git

Git’te “şu anda bulunduğumuz yer”, “HEAD” adı verilen özel bir referanstır. Master veya Main, ana branch anlamına gelir.

Commit version control systemlerinin en temel kavramıdır. Bir insanın hayatını zaman tüneli olarak düşünürsek;
- X şehrinde doğdu 1980
- ABC ilköğretimine başladı 1986
- ...

Buradaki listenin her elamanının VCS'deki karşılığı committir.

---

### Temel Git Komutları;
- git help (command): bir git komutu için yardım alın.
- git init: Yeni bir git repo’su oluşturur, ilgili verileri .git dizininde saklar.
- git status: Güncel git durumunu gösterir.
- git add (filename): Dosyaları staging area’ya ekler.
- git commit: Yeni bir commit oluşturur.
- git log: Commit geçmişini sade bir şekilde gösterir.
- git log --all --graph --decorate: git geçmişini DAG’a göre görselleştirir.
- git diff (filename): son commit’ten bu yana yapılan değişiklikleri gösterir.
- git diff birincicommitid ikincicommitid: Snapshot’lar arasındaki dosya farklılığını gösterir.
- git checkout (commitId): HEAD’i ve mevcut brach’ı günceller. git checkout komutu git deposunda başka bir yere gitmemizi sağlar.

---
### Dallanma (Branching) ve birleştirme (merging);

- git branch: Güncel brach’ları gösterir.
- git branch (branchName): Yeni bir branch oluşturur.
- git branch -D (branchName): Branch siler.
- git switch (geçmekIstediğimizBranchName): İlgili branche geçer.
- git checkout -b (branchName): Bir branch oluşturur ve ona geçer.
	- buna eşdeğerdir git branch (name); git checkout (name)
- git merge (mergeEdilecekBranchAdı): Mevcut branchı merge eder.
- git rebase: Yeni base’e yamaları yükler.
fast forwarding: mainde bir değişiklik yapmadan yeni bir branch oluşturup değişiklikleri orda yapıp tekrar mainle birleştirmeye denir.
---
### Remotes (Uzak repo);

- git remote: uzak depoları listeler.
- git remote add (name) (url): uzak bir depo ekler.
- git push (remote) (local branch):(remote branch): nesneleri uzak depoya gönderir ve uzak depo referansını günceller.
- git branch --set-upstream-to=<remote>/<remote branch>: yerel ve uzak branch’lar arasındaki yazışmaları ayarlar.
- git fetch: uzaktaki objeleri/referansları çeker.
- git pull: git pull = git fetch + git merge

---
### Geri alma;

- git commit --amend: bir commit’in içeriği/mesajını günceller.
- git reset HEAD (file): bir dosyayı stagin area’dan çıkarır.
- git checkout -- (file): değişiklikleri gözardı eder.
---
### Gelişmiş Git;

- Yanlışlıkla bir klasöre git eklersek eğer; rm -rf .git 
- Git istemcisine kendimizi tanıtmak için;
  - git config --global user.name 
  - git config --global user.email
- git clone --depth=1: tüm versiyon geçmişi olmadan, yüzeysel bir klonlama yapar
- git add -p: etkileşimli staging
- git rebase -i: etkileşimli rebasing
- git blame: kimin en son hangi satırı düzenlediğini göstertir
- git stash: Çalışma dizinindeki değişiklikleri geçici olarak saklar. Saklanan değişiklikleri görmek için commiti ekleyeceğimiz branche gelip; git stash pop
- git bisect: binary search’le geçmişi arar (örneğin ilişki yoklaması)
- .gitignore: bilinçli şekilde izlenmeyen dosyaları yoksayılan olarak belirtir

---

### Senaryo 1
Uzak bir repodan kodu indirmek için;
1. Github code kısmındaki url kopyalanır.
2. Intelij Idea terminal kısmına git clone (kopyalanan url)

---

Bu dosyada değişiklik yaptığımızı varsayalım.
1. git status (değişiklik yaptığımız dosyaları gösterir.)
2. git add . (dosyaları stage denilen ara bir konuma atar.)
3. git commit -m "yapılan degişiklik hakkında mesaj"
Uzak sunucuya göndermek içinse;
4. git push

Gönderme işlemi tamamlandı.

---

### Senaryo 2
Uzak sunucuda içi boş bir repo oluşturalım.
1. git init
2. git remote add origin (uzak repo url)
3. git status
4. git add .
5. git commit -m "initial commit"
6. git push (git push --set-upstream origin master)

kullanıcı adı, şifre,
Gönderme işlemi tamamlandı.
