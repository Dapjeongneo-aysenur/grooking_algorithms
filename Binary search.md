# Binary search
Diyelim ki telefon defterinde bir kişiyi arıyorsunuz (ne kadar eski moda bir cümle!).📖 İsmi K harfiyle başlıyor. Baştan başlayıp K'lere kadar sayfaları çevirebilirsiniz. Ancak bunun yerine ortadaki bir sayfadan başlarsınız çünkü K'lerin rehberin ortalarında olacağını bilirsiniz

Ya da sözlükte O harfi ile başlayan bir kelime aradığınızı düşünelim. Yine ortalardan başlarsınız.

Şimdi Facebook'a giriş yaptığınızı varsayalım. Giriş yaparken, Facebook'un sitede bir hesabınız olduğunu doğrulaması gerekir. Bu yüzden, veritabanında kullanıcı adınızı araması gerekir. Kullanıcı adının karlmageddon olduğunu düşünelim. Facebook, A'lardan başlayarak kullanıcı adınızı arayabilir ama ortalarda bir yerden başlaması daha mantıklıdır.

Bu bir arama(search) problemidir. Ve tüm bu durumlarda problemi çözmek için aynı algoritma kullanılır: *binary search*.

Binary search, sıralanmış bir eleman listesi alan bir algoritmadır.(Neden sıralı olması gerektiğini daha sonra açıklayacağım) Eğer aradığınız eleman bu listede yer alıyorsa, binary search elemanın bulunduğu konumu döndürür. Eğer ki bu listede yoksa **null** döndürür.

Mesela:

![1 1](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/428054bb-75e3-41c7-a57e-e0d9cf885094)

Şimdi binary search'ün nasıl çalıştığını gösteren bir örnek yapalım. 1 ile 100 arasında bir sayı düşünelim.
![1 2](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/73cc8b68-ad49-47fa-b448-54f2362a133f)

Tuttuğum sayıyı en az denemede tahmine etmelisiniz. Her tahmininizde az, fazla ya da doğru olduğunu söyleyeceğim.
1, 2, 3, 4 … şeklinde tahmin ettiğini düşünelim. Önümüzde şöyle uzuun bir yol var:

![1 3](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/9788a857-173b-4208-b914-e4ca59197da1)
![1 4](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/45281d70-6079-4d85-9c7a-9488f6d4150a)

Bu *simple search* (belki de *stupid search* demeliyiz😅). Her tahminde sadece bir eleman eliyorsunuz ve eğer tuttuğum sayı 99 ise 99 kez tahmin etmeniz gerekiyor.🤯

### Aramak için daha iyi bir yol
İşte daha iyi bir yol. 50 ile başlayalım.
![1 5](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/891ceeb3-9291-45ca-8312-4d81e1375e32)

Az ama az önce sayıların yarısını eledik!😏 Şimdi 1-50 arasındaki tüm sayıların az olduğunu öğrendik. Sonraki tahminimiz 75...
![1 6](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/bd8f2b38-2d10-48da-a62a-1a270e52b0a2)

Fazla ama yine sayıların yarısını eledik! *Binary search'te ortadaki sayıyı tahmin edersiniz, böylece her seferinde kalan sayıların yarısını elemiş olursunuz.* Sonraki 63...(50 ile 75'in ortası)

![1 7](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/fd9cfc8d-b369-4c74-88fa-5ba9120557b0)

İşte binary search, az önce ilk algoritmanı öğrendin.🥳 Ve de her seferinde kaç tane sayı elediğin
![1 8](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/d9ccef8a-926d-4be3-b6dc-f74fcc139922)

Hangi sayıyı tutarsam tutayım, en fazla 7 tahminde bulabilirsin-çünkü her tahminde çok fazla sayı eliyorsun.😉

Sözlükten bir kelimeye baktığını düşün ve sözlükte 240,000 tane kelime olsun. *En kötü ihtimalle(worst case)* her bir arama kaç adımda tamamlanır?(Okumaya devam etmeden önce tahmin et😇)
![1 9](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/f0ceab3d-183f-4a9c-8d7f-53cb4091133d)

Eğer ki aradığın kelime sözlükteki son kelime ise, simple search ile 240,000 adımda tamamlanır. Binary search'te ise en son tek bir kelime kalana kadar her adımda kalan kelime sayısını yarıya indirilir.
![1 10](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/3f1acee0-a479-4dbc-9b2b-abf381029d97)

Yani binary search ile sadece 18 adımda tamamlanır-ne büyük fark!😱 Genellemek gerikirse, *n* elemanlı bir listede yapılacak bir arama(search) işleminde simple search ile n adımda tamamlanırken en kötü ihtimalle binary search ile log2 n adımda tamamlanır.🏁

|Logaritma|
|---------|
|Logaritmanın ne olduğunu hatırlamıyor olabilirsiniz, ancak muhtemelen üstellerin ne olduğunu biliyorsunuzdur. log10 100'un anlamı "Kaç tane 10'u birbiriyle çarparsak 100 eder?"dir.Ve cevap da 2(10*10)dir. Yani **log'lar üstellerin tersidir.✨**|
|![image](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/f588abde-87ee-423f-a788-3ee56e03d3bb) |
|Bu kitapta Big O gösterimiyle(az sonra açıklayacağım) çalışma süresinden bahsederken log ifadesi hep log2 anlamında kullanılacak. Bir elemanı simple search ile ararken en kötü ihtimalle tüm elemanlara bakman gerekir. Yani 8 sayılı bir listede en fazla 8 sayıya bakacaksın. Binary search ile ararken ise en kötü ihtimalle log n tane elemana bakman gerekir. 8  sayılı bir listede ise en çok log 8 == 3, (çünkü 2**3(2 üssü 3) == 8) tane elemana bakmalısın.|

>**Not:**
Bu kitapta logaritma hakkında çokça bahsedeceğim, o yüzden logaritmayı kavramalısınız. Eğer ki bilmiyorsanız Khan Academy'nin bunu açıklayan güzel bir videosu var. -> [videoya buradan ulaşabilirsiniz](https://tr.khanacademy.org/math/algebra2/exponential-and-logarithmic-functions/introduction-to-logarithms/v/logarithms)

>**Not:**
Binary search sadece listen sıralı ise çalışır. Mesela telefon defterindeki isimler alfebetik bir şekilde sıralıdır,bu yüzden de bir isim ararken binary search kullanabiliriz. Peki ya isimler sıralı olmasaydı?🤔

Hadi Python'da binary search'ün nasıl yazıldığına bakalım. Buradaki kodda array kullanıldı(Eğer ki array'in nasıl çalıştığını bilmiyorsan, endişelenme. Bir sonraki bölümde göreceğiz😉.Sadece bir dizi elemanı array adı verilen ardışık kutularda saklayabileceğinizi bilmen yeterli. Kutular 0'dan başlayarak numaralandırılır: ilk kutu #0 konumundadır, ikincisi #1, üçüncüsü #2 ve bu şekilde devam eder.).

**Binary search** fonksiyonu bir eleman ve sıralanmış bir array alır. Eğer alınan eleman array'in bir elemanıysa fonksiyon onun konumunu döndürür. Array'in hangi kısmında arama yapılacağına dikkat et, en başta bu tüüm array'dir.🙃
![1 12](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/e8c9a628-4cbb-4994-a30c-a47ce94482b7)

Her seferinde ortadaki elemanı kontrol ederiz:
```python
mid = (low + high) / 2   #mid, (low+high) çift olmasa bile Python otomatikman aşağı yuvarlıyor
guess = list[mid]
```
Eğer ki tahmin azsa, **low**'u aşağıdaki gibi güncelleriz:
```python
if guess < item:
 low = mid + 1
```
![1 13](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/62bf0bea-1803-4208-ba65-901c472752df)

Eğer fazlaysa da **high**'ı güncelleriz. İşte tüm kod:
```python
def binary_search(list, item):
 low = 0
 high = len(list)—1

 while low <= high:
   mid = (low + high)
   guess = list[mid]

   if guess == item:
   return mid

   if guess > item:
   high = mid - 1

   else:
   low = mid + 1

 return None

my_list = [1, 3, 5, 7, 9]

print binary_search(my_list, 3) # => 1
print binary_search(my_list, -1) # => None
```

### Egzersizler
**1.1** 128 ismin olduğu sıralı bir listen olsun, sen de binary search kullanarak bu listede arama yapıyorsun. Araman en fazla kaç adımda biter?
**1.2** Listenin boyunu iki katına çıkardığını düşünelim. Şimdi en fazla kaç adımda bitirirsin?

## Çalışma süresi
Ne zaman bir algoritmadan bahsetsem, onun çalışma süresinden bahsedeceğim. Genellikle en verimli algoritmayı seçersiniz.-ister zamanı ister hafızayı optimize ediyor olun.
Binary search'e geri dönelim. Bunu kullanarak ne kadar zamandan tasarruf ettik? İlk yaklaşım her bir numarayı tek tek kontrol etmekti. Eğer ki 100 sayılık bir listemiz varsa bu 100 tahmin demektir. 4 milyar sayılık ise 4 milyar tahmin demek.💀 Yani maksimum tahmin sayısı listenin boyutu ile aynıdır. Buna *doğrusal(lineer) zaman* denir.
Ama binary search farklı. Liste 100 parçadan oluşuyorsa, en fazla 7 tahmin gerekir. 4 milyar öğeden oluşuyorsa da, en fazla 32 tahmin gerekir. Etkileyici, değil mi? Binary search logaritmik zamanda çalışır (log time). İşte bugünkü tespitlerimizi özetleyen bir tablo.
![1 14](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/903bcd42-fabe-4971-bc4d-43ff75049abc)

# Big O gösterimi
Big O gösterimi, bir algoritmanın ne kadar hızlı olduğunu gösteren özel bir gösterimdir. Kime ne?🙄 Başkalarının algoritmalarını sık sık kullanıyoruz ve kullandığımız kodun ne kadar hızlı olduğunu bilmemiz gerekebilir. 
### Algoritma çalışma süreleri farklı oranlarda büyür
Bob NASA için bir arama algoritması yazıyor. Algoritması, bir roket Ay'a inmek üzereyken devreye girecek ve nereye ineceğini hesaplamaya yardımcı olacak. 

Bu, iki algoritmanın çalışma süresinin nasıl farklı oranlarda artabileceğine bir örnek. Bob simple search ile binary search arasında karar vermeye çalışıyor. Algoritmanın hem hızlı hem de doğru olması gerekiyor. Binary search hızlıdır ve Bob'un nereye ineceğini bulmak için sadece 10 saniyesi var - yoksa roket rotasından çıkacaktır. Öte yandan, simple search'ün yazılması daha kolaydır ve hataların ortaya çıkma olasılığı daha azdır vee Bob gerçekten de roketi indirecek kodda hata olmasını istemez!🧐 Daha dikkatli olmak için Bob her iki algoritmayı da 100 elemanlı bir liste ile zamanlamaya karar verir.

Bir öğeyi kontrol etmenin 1 milisaniye sürdüğünü düşünelim. Simple search ile Bob'un 100 öğeyi kontrol etmesi gerekir, bu nedenle aramanın çalışması 100 ms sürer. Öte yandan, binary search ile sadece 7 öğeyi kontrol etmesi gerekir (log2 100 kabaca 7'dir), bu nedenle aramanın çalışması 7 ms sürer. Ancak gerçekçi olmak gerekirse, listenin bir milyar elemanı olacaktır. O zamann, simple search ve binary search ne kadar sürer?🤔Okumaya devam etmeden önce her soru için bir cevabınız olduğundan emin olun.
![1 15](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/9226dc47-fc7a-4b81-b540-c71ad800bb89)

Bob 1 milyar elemanlı binary search çalıştırıyor ve 30 ms sürüyor (log2 1.000.000.000 kabaca 30'dur). "32 ms!" diye düşünüyor, Bob.🤔 "Binary search, simple search'ten yaklaşık 15 kat daha hızlıdır, çünkü simple search 100 elemanla 100 ms, binary search ise 7 ms sürer. Yani simple search 30 × 15 = 450 ms sürer, değil mi? Benim eşik değerim olan 10 saniyenin çok altında." 
Bob simple search'ü seçmeye karar verir. 
Bu doğru bir seçim mi?🙄

