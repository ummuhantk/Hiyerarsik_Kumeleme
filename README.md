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
