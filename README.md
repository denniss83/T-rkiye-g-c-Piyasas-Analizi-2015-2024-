📊 Türkiye İşgücü Piyasası Analizi (2015–2024)

> ⚠️ **Uyarı**  
> Bu çalışma, Python programlama dili ve veri analizi becerilerini geliştirmek amacıyla hazırlanmıştır.  
> Kullanılan veriler açık kaynaklardan alınmış ve manuel olarak düzenlenmiştir.  
> Veri temizleme sürecinde olası hatalar veya eksiklikler analiz sonuçlarını etkileyebilir.  
> Bu nedenle grafik ve bulgular kesin ekonomik yorumlar için uygun değildir.


📌 Proje Amacı
Türkiye'de 2015–2024 yılları arasında işgücü, istihdam, işsizlik ve işgücüne dahil olmayan nüfusa ait veriler üzerinden çeşitli grafiksel ve sayısal analizler gerçekleştirilmiştir. Bu analizler ile yıllara göre eğilimler, oranlar, değişim hızları ve değişkenler arası ilişkiler incelenmiştir.

1️⃣ Verilerin Yüklenmesi ve Hazırlanması
Excel dosyasından ilgili tablolar okundu.

Yıllar ayrı sütunlardaydı, bu nedenle melt() işlemiyle uzun formata çevrildi.

Her veri için ayrı DataFrame’ler oluşturuldu:

İşgücü (Bin)

İstihdam (Bin)

İşgücüne Dahil Olmayan (Bin)

İşsiz Sayısı (Bin) (Hesaplandı: İşgücü - İstihdam)

İşsizlik Oranı (%) (Gerçek oranlar filtrelendi)

2️⃣ Temel Zaman Serisi Görselleştirmeleri
Yıllara Göre İşgücü, İstihdam ve İşsiz Sayısı (Bin) çizildi.

Her kategori farklı renkle gösterildi ve lineplot ile trend çizgisi verildi.

Ek olarak fill_between() ile tahmini güven aralığı gösterimi eklendi.

3️⃣ İşsizlik Oranı ile İşsiz Sayısı İlişkisi
Çift eksenli grafik kullanılarak:

Sol eksende: İşsiz Sayısı (Bin)

Sağ eksende: İşsizlik Oranı (%)

Aynı yıllara ait iki değişken karşılaştırıldı.

4️⃣ İşsiz Sayısı (Bin) Hesaplama ve Fark Grafiği
İşsiz sayısı, İşgücü – İstihdam formülü ile hesaplandı.

Gözlemlenen değerler ile hesaplanan değerler karşılaştırıldı.

Hatalı ya da sapma içeren değerler bar grafiği ile gösterildi.

5️⃣ Korelasyon Analizi
İşsizlik Oranı (%) ile İşsiz Sayısı (Bin) arasında scatter/regresyon çizimi yapıldı.

sns.regplot() ile ilişki çizildi.

Pearson korelasyon katsayısı hesaplandı:
r ≈ 0.00 → zayıf ilişki (muhtemelen veri uyumsuzluğu nedeniyle)

6️⃣ Yıllık Değişim Oranları
Her kategori için yıllık yüzde değişim hesaplandı.

barplot ile pozitif/negatif yıllık değişimler görselleştirildi.

Özellikle pandeminin etkisi görüldü (2020–2021).

✅ Sonuç ve Değerlendirme
İşgücü ve istihdam yıllar içinde genel olarak artış göstermektedir.

İşsiz sayısı ve işsizlik oranı arasında beklenen güçlü korelasyon görülmemiştir. Bu durum, veride hata veya farklı veri kaynaklarının karışıklığına işaret edebilir.

2020 yılında belirgin sapmalar mevcuttur (muhtemelen COVID-19 etkisi).

İşgücüne dahil olmayan nüfusun da ayrıca ele alınması önerilir.

🧠 Hazırlayan
Deniz Atabey
Bu proje, Python ve pandas kütüphanesi kullanılarak Google Colab üzerinde hazırlanmıştır. Veri kaynakları TUIK'ten alınmıştır.
