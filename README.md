
Amaç:
Bu R betiğinin amacı, D adlı bir veri çerçevesinde veri temizleme ve dönüştürme işlemleri gerçekleştirmektir. Temel odak noktası, "P" değerlerinin "N" ile değiştirildiği CLASS sütunudur.

Adımlar:

Veri İnceleme:
İlk adım, CLASS sütunundaki değerlerin dağılımını table(CLASS) fonksiyonu kullanarak incelemeyi içerir.


# CLASS sütunundaki orijinal değerlerin dağılımını gösteriyoruz
table(CLASS)
Eksik Değerleri Görselleştirme:
DataExplorer paketi kullanılarak veri setindeki eksik değerlerin görselleştirilmesi gerçekleştirilir.


# DataExplorer paketini yükledik
library(DataExplorer)

# Eksik değerleri görselleştirmek için bir grafik oluşturuyoruz
plot_missing(D)
CLASS Sütunundaki Değerleri Değiştirme:
plyr paketi, "P" değerlerini CLASS sütununda "N" ile değiştirmek için kullanılır. Bu amaçla mapvalues ve gsub olmak üzere iki farklı yöntem kullanılır.
R

# plyr paketini yükledik
library(plyr)

# Gsub kullanarak
D$CLASS <- gsub("P", "N", D$CLASS)

# Güncellenmiş CLASS sütunundaki değerlerin dağılımını gösteriyoruz
table(D$CLASS)
Sonuç: table(CLASS)
CLASS
  N   Y 
156 844 

attach(D)
> table(CLASS)
CLASS
  N   P   Y 
103  53 844 
> library(DataExplorer)
> plot_missing(D)
> library(plyr)

> D$CLASS=gsub("P","N",D$CLASS)
> table(CLASS)
CLASS
  N   Y 
156 844 
