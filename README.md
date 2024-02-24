# Python-ile-Temel-Veri-Analizi

Python, veri analizi için oldukça güçlü bir araçtır ve birçok kütüphane ve araç içerir. Temel veri analizi yapmak için genellikle pandas, NumPy, ve matplotlib gibi kütüphaneler kullanılır. Bu kütüphaneler, veri okuma, işleme, görselleştirme ve analiz için geniş bir işlevsellik sunar.

Python Kütüphaneleri:

Pandas: Veri analizi için en yaygın kullanılan kütüphanelerden biridir. Veriyi tablo formatında işlemek için kullanılır. Pandas, veri okuma, filtreleme, gruplama, birleştirme ve daha fazlasını yapmak için geniş bir işlevsellik sunar.

NumPy: Sayısal hesaplamalar için temel bir kütüphanedir. Çok boyutlu diziler ve matrisler üzerinde hızlı işlemler yapmak için kullanılır. Pandas gibi veri analizi için temel bir yapı taşıdır.

Matplotlib: Veriyi görselleştirmek için kullanılan bir çizim kütüphanesidir. Grafikler, histogramlar, çizgi grafikleri, dağılım grafikleri ve daha fazlasını oluşturmak için kullanılabilir.

Seaborn: Matplotlib'in üst katmanında yer alan bir grafik kütüphanesidir. İstatistiksel veri görselleştirmesi için daha yüksek düzeyde bir arayüz sunar ve daha çekici ve bilgilendirici grafikler oluşturmak için kullanılır.

Kütüphanelerin İmport Edilmesi 

Kütüphanelerin import edilmesi, Python'da dışarıdan hazır işlevselliklerin kullanılabilmesini sağlar. import ifadesi, bir Python dosyasına veya bir betiğe başka bir Python dosyasındaki kodu eklemenizi sağlar. Bu, kullanmak istediğiniz kütüphanelerin adını belirterek yapılır.

```python

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

Kütüphaneleri import etmek, Python programlama dilinde yazılım geliştirme sürecinin önemli bir parçasıdır ve çoğu zaman farklı projelerde tekrar tekrar kullanılan genel kod parçalarını içerir. Bu nedenle, bir projede kullanılacak kütüphaneleri başlangıçta import etmek, kodunuzu daha düzenli ve yönetilebilir hale getirir.


Veri Analizi Adımları:

Veri Toplama ve Okuma: İlk adım, veriyi toplamak ve uygun bir formatta okumaktır. Pandas kullanarak CSV, Excel, JSON, SQL vb. formatlardaki verileri okuyabilirsiniz.

Veri Temizleme ve Düzenleme: Veriyi inceleyerek eksik veya hatalı değerleri tespit edin ve bunları düzeltin veya çıkarın. Gereksiz sütunları veya satırları kaldırarak veriyi temizleyin ve düzenleyin.

Keşifsel Veri Analizi (EDA): Veriyi daha iyi anlamak için keşifsel veri analizi yapın. Özet istatistikler, grafikler ve görselleştirmeler kullanarak verinin dağılımını, ilişkilerini ve trendlerini inceleyin.

İstatistiksel Analiz ve Modelleme: Veriyi istatistiksel analiz ve modelleme teknikleriyle daha derinlemesine inceleyin. Bu adım, regresyon analizi, sınıflandırma, kümeleme ve hipotez testleri gibi teknikleri içerebilir.

Sonuçların Yorumlanması ve Raporlama: Elde edilen sonuçları yorumlayın ve bulgularınızı raporlayın. Analiz sonuçlarına dayanarak kararlar alın veya önerilerde bulunun.


İlk adım veriyi okumak ve içeriğini anlamak için veriyi yüklemektir. Genellikle CSV, Excel, JSON veya SQL veritabanlarından veri okuma işlemleri yapılır.
``` python
import pandas as pd

# CSV dosyasından veriyi oku
df = pd.read_csv('veri.csv')

# İlk 5 satırı göster
print(df.head())
```
Çeşitli veri formatlarından veri okumak için Pandas'ın sunduğu okuma işlevlerini ve bu işlevlere geçirilebilecek farklı parametreleri açıklayalım .

CSV Dosyaları Okuma:

CSV dosyalarından veri okumak için pd.read_csv() işlevi kullanılır. Bu işlevin bazı önemli parametreleri şunlardır:
filepath_or_buffer: Okunacak CSV dosyasının dosya yolu veya URL'si.
sep: Sütunları ayırmak için kullanılan ayraç.
header: Başlık satırının hangi satırda olduğunu belirtir.
usecols: Okunacak sütunların listesi.
dtype: Sütunların veri tiplerini belirler.

``` python
import pandas as pd

# CSV dosyasından veriyi oku
df = pd.read_csv('veri.csv', sep=';', header=0, usecols=['column1', 'column2'], dtype={'column1': int})
```

Excel Dosyaları Okuma:

Excel dosyalarından veri okumak için pd.read_excel() işlevi kullanılır. Bu işlevin bazı önemli parametreleri şunlardır:
io: Okunacak Excel dosyasının dosya yolu veya URL'si.
sheet_name: Okunacak çalışma sayfasının adı veya indeksi.
header: Başlık satırının hangi satırda olduğunu belirtir.
usecols: Okunacak sütunların listesi.
dtype: Sütunların veri tiplerini belirler.

``` python
import pandas as pd

# Excel dosyasından veriyi oku
df = pd.read_excel('veri.xlsx', sheet_name='Sheet1', header=0, usecols=['column1', 'column2'], dtype={'column1': int})
```

SQL Veritabanlarından Sorgu Sonuçlarını Okuma:
SQL veritabanlarından sorgu sonuçlarını okumak için pd.read_sql() işlevi kullanılır. Bu işlevin bazı önemli parametreleri şunlardır:
sql: Çalıştırılacak SQL sorgusu.
con: Veritabanı bağlantısı.
params: SQL sorgusu için parametreler.

``` python
import pandas as pd
import sqlite3

# SQLite veritabanı bağlantısını oluştur
conn = sqlite3.connect('veritabani.db')

# SQL sorgusu çalıştır ve sonucu DataFrame'e yükle
df = pd.read_sql('SELECT * FROM table_name', conn)
```

Veri Keşfi ve Ön İşleme

Veri keşfi, veri setini anlamak ve içeriğini incelemek için yapılan işlemleri içerirken, ön işleme ise verinin temizlenmesi, düzenlenmesi ve hazırlanması işlemlerini içerir. 

Veri Keşfi:
Özet İstatistiklerin İncelenmesi: Veri setinin temel istatistiklerine bakarak verinin dağılımı, merkezi eğilim ve yayılımını anlayabiliriz. Bu, describe() işlevi ile yapılabilir.

Eksik Değerlerin İncelenmesi: Veri setindeki eksik değerleri bulmak ve bunların ne kadar olduğunu anlamak önemlidir. Eksik değerler, isnull() ve sum() işlevleriyle tespit edilebilir.

Tekil Değerlerin ve Frekanslarının İncelenmesi: Kategorik değişkenlerdeki benzersiz değerleri ve her bir değerin frekansını incelemek, verinin içeriğini anlamamıza yardımcı olur. Bu, value_counts() işleviyle yapılabilir.

```python
import pandas as pd

# Veriyi oku
df = pd.read_csv('veri.csv')

# Özet istatistikler
print(df.describe())

# Eksik değerlerin sayısı
print(df.isnull().sum())

# Tekil değerlerin ve frekanslarının incelenmesi
print(df['kategorik_degisken'].value_counts())
```

Veri Temizleme ve Düzenleme:
Eksik Değerlerin İşlenmesi: Eksik değerler, uygun bir stratejiyle doldurulabilir veya eksik olan satırlar veya sütunlar çıkarılabilir. fillna() veya dropna() işlevleri kullanılabilir.

Aykırı Değerlerin İncelenmesi ve İşlenmesi: Aykırı değerler, veri setinin analizini etkileyebilir. Bu nedenle, aykırı değerlerin tespit edilmesi ve işlenmesi önemlidir. Aykırı değerlerin tespiti için istatistiksel yöntemler veya görselleştirmeler kullanılabilir.

Veri Türlerinin Dönüştürülmesi: Veri setindeki değişkenlerin doğru veri türlerine dönüştürülmesi önemlidir. Örneğin, tarih verileri datetime veri türüne dönüştürülebilir.

``` python

# Eksik değerleri ortalama ile doldurma
df['numeric_column'].fillna(df['numeric_column'].mean(), inplace=True)

# Aykırı değerleri belirli bir aralıkta sınırlama
df['numeric_column'] = np.where(df['numeric_column'] < lower_bound, lower_bound, df['numeric_column'])
df['numeric_column'] = np.where(df['numeric_column'] > upper_bound, upper_bound, df['numeric_column'])

# Tarih sütununu datetime veri türüne dönüştürme
df['date_column'] = pd.to_datetime(df['date_column'])
```

Veri Görsellestirme

Verinin dağılımını, ilişkilerini ve trendlerini görselleştirmek, veriyi daha iyi anlamak için önemlidir. matplotlib veya seaborn gibi kütüphaneler kullanarak grafikler oluşturulabilir.

Histogram:
Verinin dağılımını görselleştirmek için kullanılır. Örneğin, bir özellik veya değişkenin frekans dağılımını görmek için kullanılabilir.

``` python
import matplotlib.pyplot as plt

# Örnek veri
data = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4, 5, 5, 6]

# Histogram çizimi
plt.hist(data, bins=6, color='skyblue', edgecolor='black')
plt.xlabel('Değerler')
plt.ylabel('Frekans')
plt.title('Histogram')
plt.show()
```

Bar Grafiği:
Kategorik verilerin görselleştirilmesi için kullanılır. Her kategori için bir çubuk gösterilir.

``` python
# Örnek veri
categories = ['A', 'B', 'C', 'D']
values = [10, 20, 15, 25]

# Bar grafiği çizimi
plt.bar(categories, values, color='lightgreen')
plt.xlabel('Kategoriler')
plt.ylabel('Değerler')
plt.title('Bar Grafiği')
plt.show()
```

Pie Grafiği:
Verinin oransal dağılımını göstermek için kullanılır. Her kategori için bir dilim çizilir.

``` python
# Örnek veri
sizes = [25, 30, 20, 25]
labels = ['A', 'B', 'C', 'D']

# Pie grafiği çizimi
plt.pie(sizes, labels=labels, autopct='%1.1f%%', colors=['lightblue', 'lightgreen', 'lightcoral', 'lightskyblue'])
plt.title('Pie Grafiği')
plt.show()
```

Scatter Plot (Nokta Grafiği):
İki değişken arasındaki ilişkiyi görselleştirmek için kullanılır.

```python
# Örnek veri
x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]

# Nokta grafiği çizimi
plt.scatter(x, y, color='orange')
plt.xlabel('X Değerleri')
plt.ylabel('Y Değerleri')
plt.title('Nokta Grafiği')
plt.show()
```

Box Plot (Kutu Grafiği):
Değişkenlerin dağılımını ve merkezi eğilimini görselleştirmek için kullanılır.

``` python
# Örnek veri
data = [10, 15, 20, 25, 30, 35, 40]

# Kutu grafiği çizimi
plt.boxplot(data)
plt.ylabel('Değerler')
plt.title('Kutu Grafiği')
plt.show()
```

Korelasyon matrisi, veri setindeki değişkenler arasındaki ilişkiyi görselleştirmek ve analiz etmek için kullanılan bir araçtır. Bu matris, her değişken çifti için Pearson korelasyon katsayısını içerir. Pearson korelasyon katsayısı, değişkenler arasındaki doğrusal ilişkinin gücünü ve yönünü ölçer. Değerler -1 ile 1 arasında olabilir:

1'e yaklaşan bir korelasyon katsayısı, pozitif yönlü mükemmel bir doğrusal ilişkiyi temsil eder.

-1'e yaklaşan bir korelasyon katsayısı, negatif yönlü mükemmel bir doğrusal ilişkiyi temsil eder.

0'a yaklaşan bir korelasyon katsayısı, değişkenler arasında doğrusal bir ilişki olmadığını gösterir.

Korelasyon matrisi, genellikle ısı haritası olarak görselleştirilir. Bu, her değişken çifti için korelasyon katsayısının renk tonu ile gösterildiği bir matristir. Koyu renkler yüksek korelasyonu, açık renkler düşük korelasyonu temsil eder.

``` python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Veriyi oku
df = pd.read_csv('veri.csv')

# Korelasyon matrisini hesapla
corr_matrix = df.corr()

# Korelasyon matrisini görselleştir
plt.figure(figsize=(10, 8))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm', fmt=".2f", annot_kws={"size": 10})
plt.title('Korelasyon Matrisi')
plt.show()
```

Bu kod, seaborn kütüphanesini kullanarak bir ısı haritası oluşturur. annot=True parametresi, korelasyon katsayılarının matris üzerine yazılmasını sağlar. cmap='coolwarm' parametresi, renk haritasını belirler. fmt=".2f" parametresi, katsayıların ondalık sayı formatını belirler.
