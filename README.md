# file-gabungan
```phyton
from sklearn import datasets  # Mengimpor modul datasets dari scikit-learn
from sklearn.model_selection import train_test_split  # Mengimpor fungsi untuk membagi dataset menjadi data latih dan data uji
from sklearn import tree  # Mengimpor modul pohon keputusan
from sklearn.tree import DecisionTreeClassifier, plot_tree  # Mengimpor kelas untuk membuat dan memvisualisasikan pohon keputusan
import matplotlib.pyplot as plt  # Mengimpor pustaka matplotlib untuk visualisasi
```
```phyton
dir(datasets)  # Menampilkan daftar fungsi dan atribut yang tersedia dalam modul datasets
```
```phyton
data = datasets.load_digits()  # Memuat dataset 'digits' (gambar angka tulisan tangan dari 0 hingga 9)
data  # Menampilkan objek dataset
```
```phyton
dir(data)  # Menampilkan atribut yang tersedia dalam objek dataset 'digits'
```
```phyton
x = data.data    # Menyimpan fitur (representasi gambar dalam bentuk vektor piksel) ke dalam variabel x
y = data.target  # Menyimpan label (angka 0-9 yang sesuai) ke dalam variabel y
```
```phyton
x  # Menampilkan data fitur
y  # Menampilkan label target
```
```phyton
# Membagi dataset menjadi data latih dan data uji
# 80% data digunakan untuk pelatihan, 20% untuk pengujian
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.2)
```
```phyton
# Membuat model Decision Tree dengan kedalaman maksimum 3
# Batasan kedalaman ini bertujuan untuk menghindari overfitting
dtree =
DecisionTreeClassifier(max_depth=3)
```
```phyton
# Melatih model menggunakan data latih
dtree.fit(x_train, y_train)
```
```phyton
# Membuat area gambar berukuran besar agar pohon keputusan terlihat jelas
plt.figure(figsize=(30, 20))

# Menampilkan pohon keputusan
# Set parameter 'filled=True' untuk mewarnai node berdasarkan mayoritas kelas
plot_tree(dtree, filled=True)

# Menampilkan hasil visualisasi
plt.show()
```
