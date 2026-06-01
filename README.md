Akıllı Müşteri Yönetim ve Analiz Sistemi - Telco Senaryosu

Bu dosya, 446737.ipynb adlı Python notebook dosyasını açıklamak için hazırlanmıştır. Proje, bir telekomünikasyon şirketindeki müşterileri analiz eden kullanıcı girişli basit bir Python uygulamasıdır.

Program kullanıcıdan müşteri bilgilerini alır. Alınan bilgilere göre müşterinin fatura durumu, müşteri tipi, churn riski ve kampanya önerisi hesaplanır. Sonuçlar ekrana müşteri analiz raporu şeklinde yazdırılır.

Proje Dosyası

Proje paketinde asıl çalışan proje dosyası phytonDSP.ipynb adlı notebook dosyasıdır. Son teslim paketinde ayrıca bu açıklama metnini içeren README.md dosyası da bulunur. 446737.ipynb dosyası Google Colab üzerinde çalıştırılabilir.

Kullanılan Kütüphaneler

Projede Python'un standart kütüphaneleri kullanılmıştır. Ekstra kütüphane kurulumu gerekmez.

random kütüphanesi rastgele müşteri numarası üretmek için kullanılır.

math kütüphanesi fatura sonucunu yukarı yuvarlamak için kullanılır.

datetime modülünden date yapısı programın çalıştırıldığı günün tarihini almak için kullanılır.

Programın Amacı

Programın amacı, kullanıcıdan alınan müşteri bilgilerini değerlendirerek basit bir müşteri analiz raporu oluşturmaktır.

Program şu işlemleri yapar:

Kullanıcıdan müşteri adı soyadı alır.

Kullanıcıdan aylık fatura tutarını alır.

Kullanıcıdan müşterinin kaç aydır abone olduğunu alır.

Kullanıcıdan müşterinin aktif olup olmadığını alır.

Kullanıcıdan müşterinin aldığı hizmetleri alır.

Girilen hizmetleri liste haline getirir.

Müşteri için rastgele bir müşteri numarası oluşturur.

Müşteri bilgilerini Python sözlüğü içinde saklar.

Fatura tutarına göre indirimli fatura hesaplar.

Churn riskini belirler.

Müşteri tipini VIP Müşteri veya Standart Müşteri olarak belirler.

Müşteriye uygun kampanya önerisi oluşturur.

Sonuçları anlaşılır bir rapor olarak ekrana yazdırır.

Kullanıcıdan Alınan Bilgiler

Program çalıştırıldığında kullanıcıdan beş bilgi ister.

İlk olarak müşteri ad soyad bilgisi alınır. Bu bilgi müşterinin adını ve soyadını belirtir.

İkinci olarak aylık fatura tutarı alınır. Bu değer sayısal olarak girilmelidir.

Üçüncü olarak sadakat ayı alınır. Bu değer müşterinin kaç aydır abone olduğunu gösterir ve tam sayı olarak girilmelidir.

Dördüncü olarak müşterinin aktif olup olmadığı sorulur. Kullanıcı bu alana Evet veya Hayır yazabilir.

Beşinci olarak müşterinin aldığı hizmetler istenir. Hizmetler virgülle ayrılarak girilir. Örneğin İnternet, TV, Mobil şeklinde yazılabilir.

Verilerin Düzenlenmesi

Program, aktiflik bilgisini küçük harfe çevirerek kontrol eder. Kullanıcı Evet, EVET veya evet yazsa bile bu değer evet olarak algılanır ve müşteri aktif kabul edilir.

Hizmet bilgileri virgüle göre ayrılır. Her hizmetin başındaki ve sonundaki boşluklar temizlenir. Boş hizmet bilgileri listeye eklenmez. Böylece çıktı daha düzenli olur.

Müşteri Numarası

Program her müşteri için rastgele bir müşteri numarası oluşturur. Müşteri numarası TELCO ifadesiyle başlar ve yanında dört basamaklı rastgele bir sayı bulunur. Örneğin TELCO-4821 şeklinde bir müşteri numarası oluşabilir.

Müşteri Bilgilerinin Saklanması

Müşteri bilgileri Python sözlüğü içinde saklanır. Bu sözlükte müşteri numarası, müşteri adı soyadı, aylık fatura tutarı, sadakat ayı, aktiflik durumu ve alınan hizmetler bulunur.

Sözlük kullanılması, müşteriye ait bilgilerin düzenli ve kolay erişilebilir şekilde tutulmasını sağlar.

Fatura Hesaplama

Programda fatura hesaplama işlemi fatura_hesapla adlı fonksiyonla yapılır.

Eğer müşterinin aylık faturası 500 TL'den büyükse yüzde 10 indirim uygulanır. Daha sonra sonuç yukarı yuvarlanır.

Eğer müşterinin aylık faturası 500 TL veya daha düşükse indirim uygulanmaz. Sadece fatura tutarı yukarı yuvarlanır.

Örneğin aylık fatura 650 TL ise yüzde 10 indirim uygulanır ve indirimli fatura 585 TL olur.

Churn Riski Hesaplama

Churn riski, müşterinin şirketten ayrılma ihtimalini ifade eder.

Programda churn riski churn_riski_hesapla adlı fonksiyonla belirlenir.

Müşteri aktif değilse riskli kabul edilir.

Müşteri 6 aydan az süredir aboneyse ve aylık faturası 500 TL'den yüksekse riskli kabul edilir.

Müşteri 1 veya daha az hizmet alıyorsa ve aylık faturası 300 TL'den yüksekse riskli kabul edilir.

Bu şartlardan biri sağlanıyorsa churn riski var sonucu oluşur. Hiçbiri sağlanmıyorsa churn riski yok sonucu oluşur.

Kampanya Önerisi

Programda kampanya önerisi kampanya_oner adlı fonksiyonla oluşturulur.

Eğer müşteride churn riski varsa indirim, müşteri araması ve özel sadakat kampanyası önerilir.

Eğer churn riski yoksa ancak müşterinin aylık faturası 500 TL'den yüksekse VIP müşteri kampanyası önerilir.

Diğer müşteriler için standart memnuniyet kampanyası önerilir.

Müşteri Tipi

Program müşteriyi VIP Müşteri veya Standart Müşteri olarak sınıflandırır.

Müşterinin aylık faturası 500 TL'den yüksekse müşteri VIP Müşteri kabul edilir.

Müşteri 24 aydan uzun süredir aboneyse yine VIP Müşteri kabul edilir.

Bu iki şarttan hiçbiri yoksa müşteri Standart Müşteri kabul edilir.

Fatura Tarihi

Program çalıştırıldığı günün tarihini otomatik olarak alır. Bu tarih müşteri bilgilerine fatura tarihi olarak eklenir.

Çıktının Düzenlenmesi

Program, teknik değerleri kullanıcı için daha anlaşılır hale getirir.

Müşteri aktifse Aktif müşteri yazdırılır. Müşteri aktif değilse Pasif müşteri yazdırılır.

Churn riski varsa Risk var yazdırılır. Churn riski yoksa Risk yok yazdırılır.

Hizmet listesi köşeli parantezli Python listesi şeklinde değil, virgülle ayrılmış normal metin şeklinde gösterilir.

Eğer hizmet bilgisi girilmemişse Hizmet bilgisi girilmedi yazdırılır.

Tekil Hizmet Listesi

Program, hizmetler içinde tekrar eden değerleri temizlemek için set yapısını kullanır. Daha sonra bu hizmetleri sıralar ve ekrana tekil hizmet listesi olarak yazdırır.

Örneğin kullanıcı İnternet, TV, İnternet, Mobil yazarsa tekil hizmet listesinde İnternet yalnızca bir kez görünür.

Sonuç Raporu

Program çalıştırıldığında Müşteri Analiz Raporu başlıklı bir çıktı oluşturur.

Bu raporda müşteri numarası, müşteri adı soyadı, müşteri tipi, fatura tarihi, normal fatura, indirimli fatura, sadakat süresi, aktiflik durumu, alınan hizmetler, tekil hizmet listesi, churn risk durumu ve kampanya önerisi gösterilir.

Kısa Yorum Bölümü

Raporun sonunda Kısa Yorum bölümü bulunur.

Eğer müşteride churn riski varsa program bu müşteri için ayrılma riski tespit edildiğini ve özel indirim veya sadakat kampanyası uygulanabileceğini söyler.

Eğer müşteride churn riski yoksa program yüksek bir ayrılma riski tespit edilmediğini ve müşteri memnuniyetini artıracak standart kampanyaların uygulanabileceğini söyler.

Kritik Soru Cevapları Bölümü

Programın sonunda Kritik Soru Cevapları bölümü bulunur.

Bu bölümde müşteri bilgilerinin neden sözlükte tutulduğu açıklanır. Sözlük yapısının ad, fatura, sadakat süresi ve hizmetleri düzenli şekilde saklamayı sağladığı belirtilir.

Ayrıca churn riskinin nasıl hesaplandığı açıklanır. Müşteri pasifse, sadakati düşükse veya az hizmet almasına rağmen faturası yüksekse riskli kabul edildiği belirtilir.

Çalıştırma Adımları

Google Colab açılır.

Dosya menüsünden Not defteri yükle seçeneği seçilir.

446737.ipynb dosyası yüklenir.

Kod hücresi çalıştırılır.

Programın istediği müşteri bilgileri girilir.

Program müşteri analiz raporunu ekrana yazdırır.

Dikkat Edilmesi Gerekenler

Aylık fatura tutarı sayısal değer olarak girilmelidir. Örneğin 650 yazılabilir.

Sadakat ayı tam sayı olarak girilmelidir. Örneğin 12 yazılabilir.

Bu alanlara metin girilirse program hata verebilir çünkü kod bu alanlarda sayısal değer bekler.

Aktiflik durumu için Evet yazılırsa müşteri aktif kabul edilir. Evet dışında girilen değerler program tarafından aktif değil olarak değerlendirilir.

Projenin Genel Değerlendirmesi

Bu proje, Python ile hazırlanmış kullanıcı girişli ve kural tabanlı bir müşteri analiz uygulamasıdır. Gerçek bir makine öğrenmesi modeli kullanılmamıştır. Analizler kod içinde belirlenen kurallara göre yapılır.

Proje; input kullanımı, veri tipi dönüşümü, liste, sözlük, döngü, koşul ifadeleri, fonksiyon kullanımı, set yapısı ve ekrana düzenli çıktı yazdırma gibi temel Python konularını içerir.
