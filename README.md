# Göğüs Kanseri Tespiti Projesi

Bu proje, Wisconsin Üniversitesi Hastaneleri'nden alınan bir göğüs kanseri veri kümesi üzerinde K-means kümeleme algoritmasının uygulanmasını içerir. Proje, göğüs kanserinin teşhisinde K-means algoritmasını kullanarak veri kümelerinin analizini yapmayı amaçlar.

## Proje İçeriği

### Veri Kümesi

- **Veri Kümesi Kaynağı**: Wisconsin Üniversitesi Hastaneleri
- **Veri Kümesi Boyutu**: 569 örnek, 33 özellik
- **Özellikler**: Radius, texture, perimeter, area, smoothness, compactness, concavity, concave points, symmetry, fractal dimension ve bunların çeşitli alt özellikleri.

### Kütüphaneler

Projenin gerçekleştirilmesi için aşağıdaki Python kütüphaneleri kullanılmaktadır:

- `numpy`
- `pandas`
- `sklearn` (KMeans, LabelEncoder, StandardScaler, PCA, silhouette_score)
- `matplotlib`
- `seaborn`
- `yellowbrick`
- `warnings`

### Adımlar

1. **Veri Yükleme**:
    Veri kümesi `data.csv` dosyasından yüklenir ve veri kümesinin temel özellikleri incelenir.

2. **Veri Temizleme**:
    Gereksiz sütunlar (örneğin, 'Unnamed: 32', 'id') veri kümesinden çıkarılır. Eksik değerler kontrol edilir.

3. **Veri Ön İşleme**:
    Kategorik veri (`diagnosis`) sayısal verilere dönüştürülür. 
    - "B" (iyi huylu) sınıfı 0 ile,
    - "M" (kötü huylu) sınıfı ise 1 ile temsil edilir.

4. **Öznitelik Ölçekleme**:
    Özellikler `StandardScaler` kullanılarak standartlaştırılır.

5. **Boyut Azaltma**:
    Özelliklerin boyutunu azaltmak için PCA (Ana Bileşenler Analizi) uygulanır ve 3D uzayda veriler görselleştirilir.

6. **Kümeleme**:
    K-means algoritması kullanılarak veriler kümelere ayrılır. En uygun küme sayısını belirlemek için Elbow Yöntemi ve Silhouette Skoru hesaplanır.

7. **Sonuçlar**:
    - **Inertia** ve **Silhouette Skoru** grafiklerle görselleştirilir.
    - Elbow Yöntemi ile en uygun küme sayısı belirlenir.
    - Silhouette Skoru ile kümeleme kalitesi değerlendirilir.

