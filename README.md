# Veri Setinin Özeti
Hedef: Yıllara göre, farklı yaş gruplarındaki kadın ve erkeklerin memnuniyet oranlarını analiz etmek ve bu grupları kümelere ayırmak.
Veri Seti: Her satır, bir yaş grubu, cinsiyet ve memnuniyet durumu için bir yılın yüzdelik memnuniyet bilgisini içeriyor.
# Problem:
Hedef, gruplar arasındaki benzerlikleri ve farklılıkları anlamak için bir hiyerarşik kümeleme modeli oluşturmaktır. Bu sayede hangi grupların memnuniyet açısından benzerlik gösterdiği tespit edilebilir.

# Kullanılan Adımlar:
# Veri Temizleme ve Dönüşüm:
Yaş (Yas): 18-24 → 0, 25+ → 1 (numerik hale getirildi).
Cinsiyet (Cinsiyet): Kadın → 0, Erkek → 1 (numerik hale getirildi).
Memnuniyet (Memnuniyet):

Memnun → 1
Ne Memnun Ne Memnun Değil → 0
Memnun Değil → -1 (ordinal bir yapıya çevrildi).
Amaç, modelin çalışması için kategorik değişkenleri sayısal forma çevirmek.

# Özellikler (Features):
Yil: Zamanın etkisini gözlemlemek.
Yas: Yaş gruplarının memnuniyet farklılıklarını incelemek.
Cinsiyet: Kadın ve erkek arasındaki farklılıkları göz önüne almak.
Yuzde: Memnuniyet yüzdesini temsil eden temel hedef özellik.
# Veri Standartlaştırma:

Özelliklerin ölçek farkından dolayı model performansını etkilememesi için veriler Standartlaştırılmış (ortalama 0, standart sapma 1 olacak şekilde yeniden ölçeklendi).
# Hiyerarşik Kümeleme:

# Kullanılan yöntem: ***Ward's Linkage Method.
Amaç: Gruplar arasında minimum varyansı optimize etmek.
Dendrogram ile grupların birleştirme süreci görselleştirildi.
# Hedef:
Gruplar arasında memnuniyet yüzdeleri açısından benzerlik veya farklılıkları tespit etmek.
Veri kümeleri arasındaki ilişkiyi görselleştirmek ve analiz için sezgisel bir başlangıç sağlamak.
# Sonuç:
Dendrogram çıktısı, hangi grupların benzer olduğu ve kaç kümeye ayrılabileceği hakkında fikir verir.
Örneğin, yaş veya cinsiyet grupları arasında farklar olup olmadığı analiz edilebilir.
# Veri Yükleme ve Hazırlık
Veriler metin formatında oluşturularak data.csv dosyasına kaydedildi ve ardından pandas kütüphanesi kullanılarak bu dosya okundu.

# Veri Temizleme ve Düzenleme
Yas ve Cinsiyet sütunlarındaki kategorik değerler, sayısal değerlere dönüştürüldü (örneğin, 18-24 -> 0, 25+ -> 1).
Memnuniyet sütunundaki kategorik değerler de sayısal değerlere dönüştürüldü (Memnun -> 1, NeMemnunNeMemnunDegil -> 0, MemnunDegil -> -1).

# Verilerin Standartlaştırılması
StandardScaler kullanılarak, özelliklerin (özellikle Yil, Yas, Cinsiyet, Yuzde) ortalamasının 0 ve standart sapmasının 1 olacak şekilde ölçeklendirilmesi gerçekleştirildi.

# Hiyerarşik Kümeleme
scipy.cluster.hierarchy kütüphanesi kullanılarak hiyerarşik kümeleme (ward yöntemi) yapıldı. linkage fonksiyonu kullanılarak veriler kümeleme için hazırlandı.

# Dendrogram Görselleştirmesi
matplotlib ve seaborn kütüphaneleri kullanılarak dendrogram çizildi. Bu, verilerin hangi mesafelerde (uzaklıklarda) kümelendiğini gösteren bir ağaç diyagramıdır.

# Hedefler
Verilerin temizlenmesi ve uygun formata dönüştürülmesi.
Verilerin standartlaştırılması ve ölçeklendirilmesi.
Hiyerarşik kümeleme analizi ile verilerin nasıl gruplandığını görmek.
Dendrogram kullanarak bu kümeleri ve kümeleme işleminin mesafe (uzaklık) bazında nasıl gerçekleştiğini görselleştirmek.


# ***Ward's Linkage Method (Ward'ın Bağlantı Yöntemi)
Hiyerarşik kümeleme analizinde kullanılan bir bağlantı yöntemidir. Bu yöntem, kümeler arasındaki mesafeyi belirlerken, toplam iç varyansı (sınıf içi kareler toplamı) en küçük olacak şekilde kümeleri birleştirir.

# Nasıl Çalışır?
İki küme birleştirildiğinde, bu birleşimin neden olduğu toplam varyanstaki artış hesaplanır.
Amaç, toplam varyanstaki artışı minimum düzeyde tutarak kümeleri birleştirmektir.
Bu, gruplar arasında mümkün olduğunca homojen kümeler oluşturmayı sağlar.
# Neden Kullanılır?
Özellikle verilerdeki benzerlikleri en iyi şekilde yansıtmak için uygundur.
Kümeleme sırasında küçük, yoğun ve homojen gruplar oluşturarak, anlamlı kümeler elde etmeye yardımcı olur.
# Özellikleri:
Avantaj: Daha kompakt ve dengeli kümeler oluşturur.
Dezavantaj: Hesaplama maliyeti diğer yöntemlere göre daha yüksektir, çünkü her birleşim adımında varyans hesaplanması gerekir.
Bu yöntem, özellikle birbirine yakın ve yoğun kümelerin ayrıştırılmasında sıkça tercih edilir.


