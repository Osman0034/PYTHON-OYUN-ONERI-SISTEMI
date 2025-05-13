# PYTHON-OYUN-ONERI-SISTEMI
TF-IDF Algoritmasını Kullanan Gelişmiş Python Projesi Oyun Öneri Sistemi

Proje Genel Bakışı Kullanıcının oynadığı veya belirttiği oyunlara göre benzer oyunları önermek için bir sistem geliştirildi. Öneriler, TF-IDF (Terim Sıklığı-Ters Belge Sıklığı) algoritmasıyla hesaplanan benzerlikleri kullanarak oyun açıklamaları, türler, etiketler ve ekran görüntüleri gibi metin tabanlı verilere dayanmaktadır. Daha kişiselleştirilmiş sonuçlar sağlamak için kullanıcı geri bildirimi (beğenme veya beğenmeme) de öneri sistemine dahil edilmiştir.

Kullanılan Teknolojiler ve Kütüphaneler Python: Proje için birincil programlama dili.

Tkinter: Grafiksel kullanıcı arayüzü (GUI) oluşturmak için kullanılır.

Pandas: Veri işleme ve CSV dosyalarını okumak için kullanılır.

İstekler: Steam API'sine ve diğer web servislerine HTTP istekleri yapmak için kullanılır.

BeautifulSoup: HTML temizleme ve web kazıma için kullanılır.

Scikit-learn: TF-IDF vektörleştirme ve benzerlik hesaplamaları için kullanılır.

İş Parçacığı ve ThreadPoolExecutor: Çoklu iş parçacığıyla API isteklerini ve hesaplamaları hızlandırmak için kullanılır.

Kodun Ana Bileşenleri a. Önbellek Yönetimi
load_cache ve save_cache fonksiyonları, API isteklerini azaltmak ve performansı artırmak için oyun bilgilerini bir JSON dosyasında depolar.

b. Steam API Entegrasyonu

Kullanıcının Steam ID'sine göre en son oynanan oyunları getirir.

son_oynanan_oyuna_oneri fonksiyonu kullanıcının yakın zamanda oynadığı oyunların AppID'lerini döndürür.

c. Oyun Bilgilerini Alma

bilgi_cek fonksiyonu bir oyunun açıklama metnini Steam mağazasından alır ve HTML etiketlerinden temizler.

Bu veriler oyunlar arasındaki benzerlikleri hesaplamak için kullanılır.

d. TF-IDF ile Benzerlik Hesaplaması

onerilen_oyun_mantigi fonksiyonu, kullanıcı tarafından belirtilen oyun ile diğer oyunlar arasındaki benzerlikleri hesaplar.

TF-IDF algoritması oyun açıklamalarını vektörleştirir ve benzerlik puanlarını hesaplamak için kosinüs benzerliği kullanılır.

e. Kullanıcı Geri Bildirimi

Kullanıcılar önerilen oyunları "Beğenildi" veya "Beğenilmedi" olarak işaretleyebilirler.

Bu geri bildirim girişleri bir CSV dosyasında saklanır ve öneri puanlarını etkiler.

f. Fiyat-Performans Önerisi

onerilen_fiyat_performans_mantigi fonksiyonu SteamDB'den oyun fiyat verilerini alır ve fiyat-performans analizi gerçekleştirir.

Kullanıcıya fiyat-performans oranı en iyi olan oyun önerilir.

g. Kullanıcı Arayüzü (GUI)

Tkinter kullanılarak grafiksel bir arayüz oluşturulmuştur.

Kullanıcılar öneriler almak için bir oyun adı veya Steam ID girebilirler.

Öneriler arayüzde listelenir ve kullanıcı geri bildirimleri toplanabilir.

Oyun Adına Göre İş Akışı Önerisi:
Kullanıcı bir oyun adı girer.

Sistem, TF-IDF algoritmasını kullanarak girdiye benzer oyunları analiz ediyor ve öneriler sunuyor.

Steam ID'sine göre öneri:

Kullanıcı Steam ID'sini girer.

Sistem son oynanan oyunları tespit edip benzer oyunları öneriyor.

Geri bildirim:

Kullanıcılar önerilen oyunları beğendikleri veya beğenmedikleri şeklinde işaretleyebiliyorlar.

Bu geri bildirim gelecekteki öneri sonuçlarını etkiler.

Fiyat-Performans Önerisi:

Sistem, öneriler arasından fiyat-performans oranı en iyi olan oyunu belirleyip kullanıcıya sunuyor.

Sonuç Bu proje, kullanıcıların oyun tercihlerini analiz ederek onlara en uygun oyunları önermeyi amaçlamaktadır. Kullanıcı geri bildirimi ve fiyat-performans analizi gibi özelliklerle, öneri sistemi daha da geliştirilmiştir. Sonuç olarak, kullanıcılar hem ilgi alanlarına hem de bütçelerine uyan oyunları bulabilirler.
