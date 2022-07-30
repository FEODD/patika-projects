## Proje
> ### 1- Bir listeyi düzleştiren (flatten) fonksiyon yazın. Elemanları birden çok katmanlı listelerden ([[3],2] gibi) oluşabileceği gibi, non-scalar verilerden de oluşabilir. Örnek olarak:
>
>input: [[1,'a',['cat'],2],[[[3]],'dog'],4,5]
>
>output: [1,'a','cat',2,3,'dog',4,5]
>
>### 2- Verilen listenin içindeki elemanları tersine döndüren bir fonksiyon yazın. Eğer listenin içindeki elemanlar da liste içeriyorsa onların elemanlarını da tersine döndürün. Örnek olarak:
>input: [[1, 2], [3, 4], [5, 6, 7]]
>
>output: [[[7, 6, 5], [4, 3], [2, 1]]


## Kod incelemesi#1
```python
def flatten(x):
    for i in x:
        if isinstance(i, list):
            flatten(i)
        else:
            l2.append(i)
```
>Fonksiyondaki "isinstance" kodu ile liste içerisindeki her elemanın bir liste mi yoksa eleman mı olduğuna bakılıyor eğer liste ise "if" komutu içerisindeki flatten ile 
>listeler düz hale getiriliyor ve eğer liste halinde değilse yeni bir listeye ekleniyor ve bastırılıyor

## Kod incelemesi#2
```python
l3= [[1, 2], [3, 4], [5, 6, 7]]
l3=l3[::-1]

for i in range(len(l3)):
  l3[i]=l3[i][::-1]
print(l3)
```
>İlk olarak liste içerisindeki elemanların türlerine bakmadan geriye doğru sıralanıyor. Sıralamadan sonra "for" komutu ile yeni listenin içerisindeki listeler kendi içlerinde
>sıralanıyorlar en sonunda ise liste bastırılıyor
