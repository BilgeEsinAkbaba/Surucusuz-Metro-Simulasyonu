# 🚇 Sürücüsüz Metro Simülasyonu (Rota Optimizasyonu)

Bu proje, bir metro ağında iki istasyon arasındaki **en hızlı** ve **en az aktarmalı** rotayı bulan bir simülasyon geliştirmeyi amaçlamaktadır. Proje, **graf veri yapısını** kullanarak metro ağını modellemekte ve **BFS** (Breadth-First Search) ile **A\*** algoritmalarını kullanarak rota optimizasyonu yapmaktadır.

---

## 🛠️ Kullanılan Teknolojiler ve Kütüphaneler

- **Python**: Projenin temel programlama dili.
- `collections.defaultdict`: Graf yapısını modellemek için kullanılan bir veri yapısı.
- `collections.deque`: BFS algoritmasında kuyruk yapısını oluşturmak için kullanılan bir veri yapısı.
- `heapq`: A\* algoritmasında öncelik kuyruğu oluşturmak için kullanılan bir modül.
- `typing`: Python'da tür ipuçları (type hints) kullanarak kodun okunabilirliğini artırmak için kullanılan bir modül.

---

## 📌 Algoritmaların Çalışma Mantığı

### 🔹 BFS Algoritması (en_az_aktarma_bul)
BFS (Breadth-First Search) algoritması, bir graf üzerinde genişleme yaparak en kısa yolu bulmayı amaçlar. Bu projede, BFS algoritması kullanılarak iki istasyon arasındaki **en az aktarmalı** rota bulunmaktadır.

- **Kuyruk Yapısı**: BFS algoritması, kuyruk (queue) yapısını kullanarak graf üzerinde genişleme yapar. Kuyruk, ziyaret edilecek istasyonları ve bu istasyonlara ulaşmak için izlenen rotayı tutar.
- **Ziyaret Edilen İstasyonlar**: Algoritma, ziyaret edilen istasyonları takip ederek aynı istasyona tekrar gitmeyi engeller.
- **Komşu İstasyonlar**: Her bir istasyonun komşuları keşfedilir ve kuyruğa eklenir.
- **En Kısa Rota**: Hedef istasyona ulaşıldığında, izlenen rota **en az aktarmalı rota** olarak döndürülür.

### 🔹 A* Algoritması (en_hizli_rota_bul)
A\* algoritması, bir graf üzerinde en kısa yolu bulmak için kullanılan bir arama algoritmasıdır. Bu projede, A\* algoritması kullanılarak iki istasyon arasındaki **en hızlı** rota bulunmaktadır.

- **Öncelik Kuyruğu**: A\* algoritması, öncelik kuyruğu (priority queue) kullanarak en umut verici yolları önceliklendirir. Kuyruk, toplam süre ve **heuristic** değerine göre sıralanır.
- **Heuristic Fonksiyonu**: Heuristic fonksiyonu, bir istasyondan hedef istasyona olan tahmini maliyeti hesaplar. Bu projede basit bir heuristic fonksiyonu kullanılmıştır.
- **Toplam Süre**: Her bir komşu istasyona ulaşmak için gereken süre hesaplanır ve aktarma yapılıyorsa ekstra süre eklenir.
- **En Hızlı Rota**: Hedef istasyona ulaşıldığında, izlenen rota ve toplam süre döndürülür.

---

## 🤔 Neden Bu Algoritmaları Kullandık?

- **BFS Algoritması**: En az aktarmalı rotayı bulmak için BFS algoritması kullanıldı çünkü BFS, graf üzerinde genişleme yaparak en kısa yolu (en az aktarmalı yolu) garanti eder.
- **A\* Algoritması**: En hızlı rotayı bulmak için A\* algoritması kullanıldı çünkü A\*, heuristic fonksiyonu sayesinde en umut verici yolları önceliklendirerek en hızlı rotayı bulmayı sağlar.

---

## 🧪 Örnek Kullanım ve Test Sonuçları

Proje, aşağıdaki test senaryoları ile test edilmiştir:

### **Senaryo 1: AŞTİ'den OSB'ye**

- **En az aktarmalı rota**:  
  AŞTİ (Mavi Hat) → Kızılay (Mavi Hat) → Kızılay (Kırmızı Hat) → Ulus (Kırmızı Hat) → Demetevler (Kırmızı Hat) → OSB (Kırmızı Hat)
  
- **En hızlı rota**:  
  AŞTİ (Mavi Hat) → Kızılay (Mavi Hat) → Kızılay (Kırmızı Hat) → Ulus (Kırmızı Hat) → Demetevler (Kırmızı Hat) → OSB (Kırmızı Hat)
  **Toplam süre**: 27 dakika

### **Senaryo 2: Batıkent'ten Keçiören'e**

- **En az aktarmalı rota**:  
  Batıkent (Turuncu Hat) → Demetevler (Turuncu Hat) → Gar (Turuncu Hat) → Keçiören (Turuncu Hat)

- **En hızlı rota**:  
  Batıkent (Turuncu Hat) → Demetevler (Turuncu Hat) → Gar (Turuncu Hat) → Keçiören (Turuncu Hat)  
  **Toplam süre**: 21 dakika

### **Senaryo 3: Keçiören'den AŞTİ'ye**

- **En az aktarmalı rota**:  
  Keçiören (Turuncu Hat) → Gar (Turuncu Hat) → Gar (Mavi Hat) → Sıhhiye (Mavi Hat) → Kızılay (Mavi Hat) → AŞTİ (Mavi Hat)

- **En hızlı rota**:  
  Keçiören (Turuncu Hat) → Gar (Turuncu Hat) → Gar (Mavi Hat) → Sıhhiye (Mavi Hat) → Kızılay (Mavi Hat) → AŞTİ (Mavi Hat)  
  **Toplam süre**: 21 dakika

![image](https://github.com/user-attachments/assets/b5ca21e7-2d4b-4edc-8cf2-aee8482b8854)

---

## 💡 Projeyi Geliştirme Fikirleri

- **Daha Büyük Bir Graf Kullanmak**: Projeyi daha büyük bir metro ağı üzerinde test ederek algoritmaların performansını artırabilirsiniz.
- **Görselleştirme Eklemek**: Metro ağını ve bulunan rotaları görselleştirmek için `matplotlib` veya `networkx` gibi kütüphaneler kullanabilirsiniz.
- **Farklı Özellikler Eklemek**: Örneğin, istasyonlar arasındaki mesafeleri ekleyerek daha gerçekçi bir rota optimizasyonu yapabilirsiniz.

---
## 📚 Faydalı Kaynaklar

- [Python BFS Implementation](https://realpython.com/pathfinding-python-astar/)
- [BFS Algorithm Visualization](https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/)
- [A* Pathfinding Algorithm](https://www.redblobgames.com/pathfinding/a-star/introduction.html)
- [A* Search Algorithm in Python](https://www.geeksforgeeks.org/a-search-algorithm/)
- [Python Collections Module](https://docs.python.org/3/library/collections.html)
- [Python Heapq Module](https://docs.python.org/3/library/heapq.html)

