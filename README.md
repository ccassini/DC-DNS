Windows Komut İstemi (CMD) ile DNS adresini değiştirmek için şu adımları izleyebilirsin:

## 1. Komut İstemini Yönetici Olarak Aç
- **Başlat Menüsü**ne sağ tıklayıp "Komut İstemi (Yönetici)" veya "Windows PowerShell (Yönetici)"yi seç.
![figure1-3](https://github.com/user-attachments/assets/3fe2912a-1480-48e2-b052-17665ab0d20d)

## 2. Ağ Bağdaştırıcını Öğrenmek İçin Komutu Çalıştır
İlk olarak, bilgisayarındaki ağ bağdaştırıcılarının adını öğrenmek için şu komutu yaz:

```bash 
netsh interface ipv4 show config
```

Bu komut, bilgisayarındaki tüm ağ bağdaştırıcılarını gösterecek. "Bağdaştırıcı" adını belirle (örneğin, "Ethernet" veya "Wi-Fi").

## 3. DNS Sunucusunu Değiştirmek İçin Komutları Kullan
Aşağıdaki komutu, senin kullandığın bağdaştırıcı adına göre düzenleyip çalıştır. Örneğin, "Wi-Fi" için:

 ```bash  
 netsh interface ipv4 set dns name="Wi-Fi" static 8.8.8.8
```

Alternatif DNS sunucusu olarak Google'ın ikinci DNS adresini eklemek için şu komutu kullan:

```bash
netsh interface ipv4 add dns name="Wi-Fi" 8.8.4.4 index=2
```

Eğer "Ethernet" kullanıyorsan, "Wi-Fi" yerine "Ethernet" yazabilirsin.

## 4. Ayarları Doğrulamak İçin
DNS sunucusunun değiştiğini doğrulamak için şu komutu kullan:

```bash
nslookup
```

Burada, yeni DNS ayarlarının etkin olup olmadığını görebilirsin.
![image](https://github.com/user-attachments/assets/90bf7083-6164-42e9-bc04-2deb473533b8)


