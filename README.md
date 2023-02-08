https://www.youtube.com/watch?v=SigloINyxlw

Öncelikle Amazon AWS Servisine üye olmalıyız ; 
Amazon AWS kayıt işlemi aşağıdaki adımları izleyerek yapılabilir:

- Amazon AWS web sitesine gidin ve "Create a new AWS account" butonuna tıklayın.
- Kişisel bilgilerinizi (ad, soyad, e-posta adresi, şifre) girin ve "Sign in using our secure server" butonuna tıklayın.
- Kendinize ait bir Amazon hesabınız varsa, Amazon hesabınıza giriş yapın. Aksi takdirde, "Create a new Amazon account" butonuna tıklayarak Amazon hesabı oluşturun.
- Fatura bilgilerinizi (kredi kartı bilgileri tecihen sanal kart) girin ve "Verify your identity" butonuna tıklayın.
- Üye olma işleminizi tamamlayın ve "Sign in to the Console" butonuna tıklayarak Amazon AWS hesabınıza giriş yapın.

## EC2 Server Kurulumu 

1- [Şu]([https://github.com/user/repo/blob/branch/other_file.md](https://aws.amazon.com/tr/)) linke tıklayıp arama kısmına `EC2` yazıp en üstte çıkan EC2'yi açın 

<img width="1353" alt="Ekran Resmi 2023-02-08 22 00 49" src="https://user-images.githubusercontent.com/120671243/217631705-a4d30813-2679-4dfc-8eb5-c53fd2c1b393.png">

2- Daha sonra açılan sayfada alt kısımda turuncu renkli ``Launch instance`` butonuna basın .

<img width="1029" alt="Ekran Resmi 2023-02-08 22 01 31" src="https://user-images.githubusercontent.com/120671243/217631833-ae549bd9-8232-4d47-ade7-b5aff14e9a20.png">

3- Resimde görülen en alt sağ kısımda bulunan `Browse more AMIs`'e basın

<img width="783" alt="Ekran Resmi 2023-02-08 22 02 34" src="https://user-images.githubusercontent.com/120671243/217631936-6b48e2cb-c4b3-42a8-881d-27cc7d05a50c.png">

4- Açılan sayfada AWS Marketplace AMIs sekmesine gelip arama kısmına `openvpn` yazın ve `OpenVPN Access Server`'daki `Select` butonuna basın ve ardından `Continue`'ye basın

<img width="1363" alt="Ekran Resmi 2023-02-08 22 03 21" src="https://user-images.githubusercontent.com/120671243/217631992-377e5d67-6bf1-415b-a2d2-c6f37781134d.png">
<img width="1365" alt="Ekran Resmi 2023-02-08 22 03 50" src="https://user-images.githubusercontent.com/120671243/217632019-2c043f95-7cf8-4e14-ae2c-c1d4bd13f36e.png">
<img width="1361" alt="Ekran Resmi 2023-02-08 22 04 06" src="https://user-images.githubusercontent.com/120671243/217632064-f08469cc-933c-4e5e-8be2-5d924429c115.png">

5- Açılan sayfada `Instance type` kısmındaki seçenekleri açıp `t2.micro`'yu seçin (zaten ücretsiz olan bu)

<img width="783" alt="Ekran Resmi 2023-02-08 22 04 34" src="https://user-images.githubusercontent.com/120671243/217632133-8ca050c4-256e-440c-ae52-e334a0c6e3ea.png">
<img width="756" alt="Ekran Resmi 2023-02-08 22 04 49" src="https://user-images.githubusercontent.com/120671243/217632218-9dbd9851-a002-4724-98c7-f61221d5d69b.png">

6- Hemen altta bulunan `Key pair(login)` de bulunan `Create new key pair`'e basıp Key pair name kısmına (spesifik bir isim verebilirsiniz fakat diğer adımlarda hata yapmamanız için `openvpnkey` kalırsa daha iyi olur) girip en altta bulunan `Launch instance` butonuna basın

<img width="614" alt="Ekran Resmi 2023-02-08 22 05 22" src="https://user-images.githubusercontent.com/120671243/217632268-17dd6092-0d6b-4117-ac84-358fa99c14f9.png">

## Sunucuya Bağlanma

1- Kurduğunuz sunucunu sağında bulunan kutucuğa tik atıp sağ üstteki connect butonuna basın

<img width="1123" alt="Ekran Resmi 2023-02-08 22 32 16" src="https://user-images.githubusercontent.com/120671243/217633663-49198d75-35eb-46a1-94b9-6fb30d217838.png">

2- Açılan sekmede `SSH client`'e basın .

3- Terminali açıp (Windows için Windowslogosu+r basıp açılan pencereye cmd yazın) , terminalde `pwd` komutu ile terminalin nerede çalıştığına bakın ve indirdiğiniz `.pem` dosyasının olduğu dizine gidin . 
- `ls` komutu bulunduğunuz dizindeki alt dosyaları gösterir 
- `cd` komutu ile belirttiğiniz klasöre gidebilrisiniz örneğin ; cd desktop veya cd <dosya adı> 
- `cd ..` komutu ile bir önceki dizine gidebilrisiniz

4- `.pem` dosyasının bulunduğu klasöre gittiğinizde , SSH client sayfasında 3.adımda bulunan kodu koplayayıp terminale yapıştırın ve entera basın ardından en altta bulunan Example: kodunu kopyalayıp entera basın . Ardından are you sure you want continue kısmına `yes` yazıp entera basın ve ardından çıkan bütün seçeneklerde entera basıp hızlıca ilerleyebilirsiniz , yükleme işlemi bittikten sonra diğer adıma geçin .

5- Kurulum bittikten sonra SSH client sayfasında bulunan example kodunu tekrardan yapıştırın ve `sudo passwd openvpn` yazın ,yeni şifre oluşturun burada terminale giridğiniz karakterler görünmeyecektir . Kurulum tamamlandığında kullanıcı adınz ve şifrenizi igirerek openvpn ile bağlanabilirsiniz


### Bağlantı için sunucunuzdaki public ip adresini kopyalayın ve kuullanıcı adı ve oluşturduğunuz şifre ile bağlanın

