# 🚇 Sürücüsüz Metro Simülasyonu (Rota Optimizasyonu)

Bu proje, bir metro ağı içinde **en az aktarmalı** ve **en hızlı** rotayı bulmak için geliştirilmiş bir simülasyondur.  
BFS ve A* algoritmalarını kullanarak, iki istasyon arasındaki en uygun rotaları hesaplar.

---

## 🚀 Proje Amacı

Bu projede aşağıdaki hedeflere ulaşılması amaçlanmıştır:

- **Graf veri yapısını** kullanarak metro ağını modelleme  
- **BFS (Breadth-First Search)** algoritması ile **en az aktarmalı** rotayı bulma  
- **A* (A-Star) algoritması** ile **en hızlı** rotayı bulma  
- **Gerçek dünya problemlerini** algoritmik düşünce ile çözme  

---

## 🛠️ Kullanılan Teknolojiler ve Kütüphaneler

- **Python** (Temel dil)  
- `collections.deque` (BFS için kuyruk yapısı)  
- `heapq` (A* algoritması için öncelik kuyruğu)  

---

## 📌 Algoritmaların Çalışma Mantığı  

### 🔹 BFS Algoritması (En Az Aktarmalı Rota)

Breadth-First Search (BFS), bir graf içinde **en kısa yolu** bulmak için kullanılan bir algoritmadır.

- **Kuyruk (deque)** yapısı kullanılarak, **en az durak değiştirerek** hedef istasyona ulaşan rota belirlenir.  
- Her istasyonun komşuları keşfedilir ve **en kısa yol** bulunur.  

### 🔹 A* Algoritması (En Hızlı Rota)

A* (A-Star) algoritması, **en hızlı rotayı** bulmak için kullanılır.

- **`heapq` modülü** kullanılarak öncelik kuyruğu oluşturulur.  
- **Geçiş süresi** hesaplanarak, **en kısa sürede** hedefe ulaşan yol bulunur.  

---
## 📌 Örnek Kullanım ve Test Sonuçları 

![image](https://github.com/user-attachments/assets/c40e1cca-1021-4821-ae52-adc289550393)

---
## 🔧 Projeyi Geliştirme Fikirleri

- Daha büyük bir **metro ağı** eklemek  
- **Metro duraklarını ve rotaları** görselleştirmek  
- **Gerçek zamanlı trafik durumu** gibi ek faktörleri hesaba katmak  
