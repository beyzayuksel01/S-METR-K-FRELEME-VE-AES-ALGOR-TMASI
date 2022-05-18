# SIMETRIK-SIFRELEME-VE-AES-ALGORITMASI
Günümüzde veri güvenliği çok önemli bir konumdadır. Bunun için yapılan 
çalışmaların bir kısmı da kriptolojidir yani şifreleme. Simetrik şifrelemeler, 
şifreleme ve şifre çözme için aynı anahtarı kullanır. Bu anahtar şifrelenecek 
metni gönderen ve metni alan kişide olur. Sadece bu iki kişide olması güvenliği 
sağlar. Anahtarı olmayan kişi şifrelenmiş metni ele geçirse de orijinal metni 
göremez. Bir örnekle anlatacak olursak Ahmet ve Berk bir konuşma 
gerçekleştirmek istiyor ama bu konuşmanın gizli olmasını, kendilerinden başka 
kimsenin okuyamamasını istiyorlar.
İlk başta Ahmetin elinde açık mesaj (plain 
text) var ve bu mesajı şifrelemek (cipher text) istiyor. En basit algoritma olarak 
kaydırma şifrelemesini uygulamak istiyor. Diyelim ki şifrelenecek mesaj “ne 
yapıyorsun” olsun. Bu açık cümle “neyapıyorsun” şeklinde yazılmalı ki mesaja 
ulaşmak isteyen kötü kişi kelime boyutlarını tahmin edemesin.
Şifrelenecek mesaj = “neyapıyorsun”
Kaydırılacak miktar = 4 (bu anahtarımız)
Şifreli mesaj = “rıcdtkcsuvr” diyelim
Şifreli mesajı alan Berk açma algoritması ile ve anahtar ile şifreyi güvenli şekilde 
açar ve açık metni görmüş olur. Fark ettiyseniz şifreleme ve şifre çözme 
algoritması birbirinin simetriğidir ve adını buradan alır.
Simetrik şifrelemenin farklı yöntemleri vardır bunlardan başlıca gelenler AES, 
DES, 3DES, RC4`tür.
Simetrik şifrelemenin avantajları vardır bunlar:
 İletişim gizliliği sağlanır.
 Şifreleme ve şifre çözme işlemi hızlıdır.
 Verinin bütünlüğü sağlanır.
Ama dezavantajı ve zorlukları da vardır bunlar:
 Aynı anahtara sahip birisi tarafından kullanılabilir.
 Anahtar saklamak zordur.
 AES ALGORİTMASI 
AES algoritması byte tabanlı şifreleme uygulamasıdır. 1997 yılında NIST yeni bir 
şifreleme standartı geliştirmek istemiş çünkü DES artık yeterli gelmiyordur 
güvenlik açısından sıkıntılıdır. NIST tarafından bir yarışma düzenlenerek yeni 
şifreleme standartının Rijndael algoritmasının Gelişmiş Şifreleme Standardı 
(AES) olarak kullanılacağını ilan etmiştir. AES bir simetrik şifrelemedir yani tek 
anahtarla hem şifreleme hem şifre çözme işlemi yapılır. AES için tüm matrisler 
128 bit olmak zorunda ama uzunlukları 128, 192, 256 olabilir. Anahtar uzunluğu 
değişimi döngü sayısını da değiştirir.
AES algoritması 128 bitlik olanda 10 tur vardır. Bu turlarda 4 tane işlem var her 
bir turda matris bu 4 işlemden geçer.
1.SubBytes
• Byte´ların yer değiştirmesidir. Durum matrisinin her elemanı, değerleri 
önceden hesaplanarak oluşturulmuş S-kutusundaki değerlerle değiştirilir.
•
2.ShiftRows 
Satırların yer değiştirilmesi.
1.satıra dokunmuyoruz
2.satırı 1 pozisyon sola kaydırıyoruz.
3.satırı 2 pozisyon sola kaydırıyoruz.
4.satırı 3 pozisyon sola kaydırıyoruz.
3.MixColumn 
• Her bir sütunu bir matrisle çarparak yeni bir matris oluşturuyoruz.
4.AddRoundKey
Her döngünün sonunda anahtar eklenir.
Böylece mesaj şifrelenmiş olur. Bu işlemler 10 kere tekrar eder fakat son turda 
mix colums yapılmaz.
Şifreyi çözmek de bu işlemlerin tam tersini yaparak gerçekleştirilir.
