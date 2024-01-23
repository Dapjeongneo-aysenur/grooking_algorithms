# Binary search
Diyelim ki telefon defterinde bir kişiyi arıyorsunuz (ne kadar eski moda bir cümle!).📖 İsmi K harfiyle başlıyor. Baştan başlayıp K'lere kadar sayfaları çevirebilirsiniz. Ancak bunun yerine ortadaki bir sayfadan başlarsınız çünkü K'lerin rehberin ortalarında olacağını bilirsiniz.

Ya da sözlükte O harfi ile başlayan bir kelime aradığınızı düşünelim, yine ortalardan başlarsınız.

Şimdi Facebook'a giriş yaptığınızı düşünelim. Giriş yaparken, Facebook'un sitede bir hesabınız olduğunu doğrulaması gerekir. Bu yüzden, veri tabanında kullanıcı adınızı araması gerekir. Kullanıcı adının karlmageddon olduğunu düşünelim. Facebook, A'lardan başlayarak kullanıcı adınızı arayabilir ama ortalarda bir yerden başlaması daha mantıklıdır.

Bunlar birer arama(search) problemidir ve tüm bu durumlarda problemi çözmek için aynı algoritma kullanılır: *binary search*.

Binary search, sıralanmış bir eleman listesi alan bir algoritmadır.(Neden sıralı olması gerektiğini daha sonra açıklayacağım) Eğer aradığınız eleman bu listede yer alıyorsa, binary search elemanın bulunduğu konumu döndürür. Eğer ki bu listede yoksa **null** döndürür.

Mesela:
![1 1](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/428054bb-75e3-41c7-a57e-e0d9cf885094)

Şimdi binary search'ün nasıl çalıştığını gösteren bir örnek yapalım. 1 ile 100 arasında bir sayı düşünelim.
![1 2](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/73cc8b68-ad49-47fa-b448-54f2362a133f)

Tuttuğum sayıyı en az denemede tahmin etmelisiniz. Her tahmininizde az, fazla ya da doğru olduğunu söyleyeceğim.
1, 2, 3, 4 … şeklinde tahmin ettiğini düşünelim. Önümüzde şöyle uzuun bir yol var:
![1 3](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/9788a857-173b-4208-b914-e4ca59197da1)
![1 4](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/45281d70-6079-4d85-9c7a-9488f6d4150a)

Bu *simple search* (belki de *stupid search* demeliyiz😅). Her tahminde sadece bir eleman eliyorsunuz ve eğer tuttuğum sayı 99 ise 99 kez tahmin etmeniz gerekiyor.🤯

### Aramak için daha iyi bir yol
İşte daha iyi bir yol. 50 ile başlayalım.
![1 5](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/891ceeb3-9291-45ca-8312-4d81e1375e32)

Az önce sayıların yarısını eledik!😏 Şimdi 1-50 arasındaki tüm sayıların az olduğunu öğrendik. Sonraki tahminimiz 75...
![1 6](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/bd8f2b38-2d10-48da-a62a-1a270e52b0a2)

Fazla ama yine sayıların yarısını eledik! *Binary search'te ortadaki sayıyı tahmin edersiniz, böylece her seferinde kalan sayıların yarısını elemiş olursunuz.* Sonraki 63...(50 ile 75'in ortası)
![1 7](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/fd9cfc8d-b369-4c74-88fa-5ba9120557b0)

İşte binary search, az önce ilk algoritmanı öğrendin.🥳 Ve de her seferinde kaç tane sayı elediğini.
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

Hayır! Görünüşe göre Bob hata yapıyor, hem de büyük bir hata. Simple search'ün 1 milyar elemandaki çalışma süresi 1 milyar ms, yani 11 gündür!😵‍💫 Sorun şu ki, binary search ve simple search için çalışma süreleri *aynı oranda artmıyor*. 
![1 16](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/06221023-f46e-4e00-97c9-40bdb81ac1f4)

Eleman sayısı arttıkça binary search'ün tamamlanması biraz daha fazla sürer ama simple search'te *çook* daha fazla sürer. Yani listedeki eleman sayısı arttıkça binary search, simple search'ten *çok* daha fazla sürmeye başlar. Bob binary search'ün simple search'ten 15 kat hızlı olduğunu düşündü, ancak bu doğru değil. Eğer ki listede 1 milyar eleman varsa 33 milyon kat hızlı olur. Bu yüzden bir algoritmanın çalışma hızını bilmek yeterli değil-listenin boyu arttıkça çalışma hızının nasıl arttığını da bilmeliyiz. İşte burada işin içine Big O gösterimi giriyor.

Big O gösterimi bir algoritmanın ne kadar hızlı olduğunu söyler. Mesela listenin boyu *n* olsun. Simple search tüm elemanları kontrol edeceği için *n* adım sürecek. Çalışma süresi Big O gösterimi ile O(*n*)'dir. Peki saniyeler nerede?🙄Açıkçası yok-Big O saniyedeki hızını belirtmez. Big O *gösterimi adım sayısını karşılaştımanı sağlar.* Algoritmanın ne kadar hızlı büyüyeceğini gösterir.
![1 17](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/c3cbddbb-422d-4112-822e-a6633aebd6c8)

İşte başka bir örnek. Binary search *n* elemanlı bir listeyi log *n* adımda tamamlar. Big O ile gösterimi nasıl mı, O(log *n*) şeklinde. Genellikle Big O gösterimi şu şekilde yazılır.
![1 18](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/eb9ac47c-753c-4f2a-b084-0994e1af6cc8)

Bu bir algoritmanın kaç adımda tamamlanacağını gösterir. Buna Big O gösterimi denmesinin sebebi adım sayısının önüne "büyük bir O" koyduğumuz için. (şaka gibi ama gerçek!🙃)

Hadi bir kaç örneğe bakalım, bakalım çalışma sürelerini bulabilecek misin?🧐

### Farklı Big O çalışma sürelerini görselleştirmek                                

İşte evde bir kaç parça kağıt ve kalemle takip edebileceğin pratik bir örnek.📝 16 kutudan oluşan bir ızgara çizdiğinizi düşünelim.
![image](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/7ce84bad-649a-4346-beec-74c0b5446074)

#### 1. algoritma
16 kutu çizmenin bir yolu teker teker çizmek. Big O'nu yapılan adımları saydığını hatırla. Bu örnekte de her kutu birer adım ve 16 kutu çizmelisin. Bu şekilde kaç adım sürer?
![image](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/b8159c62-973f-42f5-9e32-aac58dff1006)

16 adımda 16 kutu çizilmiş olur. Peki bu algoritmanın çalışma süresi ne olur?🤔

#### 2. algoritma
Tek tek çizmek yerine katlamaya ne dersin!
![image](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/b91755b9-457d-40a7-a006-91551f2dee6d)

Bu sefer, kağıdı katlamamız bir adım oluyor ve her adımda 2 kutu yapıyorsun! Hadi kağıdı katlayalımm!🥳
![image](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/4d88a4a1-d4d5-4d76-bebf-4491ad500176)

4 kez katladıktan sonra kağıdını aç vee artık harika bir ızgaran var! Her katlamada kutuların sayısı iki katına çıktı ve 4 adımda 16 kutu yapmış oldun!
![image](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/d7be63f9-b8e5-4307-b520-e1e95aa73844)

Her katlamada kutu sayın iki katına çıkıyor, böylece 4 adımda 16 kutun oluyor. Peki bu algoritmanın çalışma süresi ne olur? Devam etmeden iki algoritmanın da çalışma süresini bulmuş oll.🤭

*Cevaplar:* 1. algoritmayla O(*n*) seferde, 2. algoritmada ise O(log *n*) seferde tamamlanır.

### Big O en kötü durumun çalışma süresini gösterir
Telefon defterinde birini ararken simple search kullandığını düşünelim. Simple search'ün çalışmasının O(*n*) kadar zaman sürdüğünü biliyorsun. bu da en kötü durum demek çünkü telefon defterindeki herkese bakmak zorundasın. Adit'i aradığını ve telefon defterindeki ilk kişi o olsun. Yani tüm defteri okumadan-hatta ilk seferde- aradığın kişiyi buluyorsun. Peki algoritma hala O(*n*) kadar sürer mi, yoksa ilk seferde bulduğun için O(1) kadar mı olur?🤔

Simple search hala O(*n*) kadar sürer. Az önce aradığını hemen bulmuş olabilirsin-ki bu en iyi durum(best case) ama unutma ki Big O gösterimi *en kötü durumu* temel alır. Bu yüzden de *en kötü ihtimalle* kitaptaki her şeye en az bir kez bakmış olursun, bu da O(*n*) eder. Yani bu bir güvencedir ve simple search O(*n*)'den kısa süremez.

> **Not:** En kötü durumdaki çalışma süresinin yanında ortalama çalışma süresine bakmak da önemlidir. Bunu da 4. bölümde yapacağız.😉

### En yaygın Big O süreleri
İşte sık sık karşılaşacağın 5 Big O süreleri(hızlıdan yavaşa doğru sıralandı):
1. O(log *n*), log time olarak da bilinir. Örnek: Binary search.
2. O(*n*), linear time olarak da bilinir. Örnek: Simple search.
3. O(*n* * log *n*). Örnek: Hızlı bir algoritma olan quicksort gibi(4. bölümde).
4. O(*n2*(n kare)). Örnek: Yavaş bir algoritma olan selection sort gibi(2. bölümde).
5. O(*n!*). Örnek: Çook yavaş bir algoritma, "Gezgin satıcı"daki gibi (az sonra bahsedeceğiz!).

Yine 16 kutulu bir ızgara çizelim ve bu 5 algoritmadan birini seçiyorsun. Eğer ki ilk algoritmayı kullanırsan O(log *n*) kadar sürecek ve saniyede 10 adım tamamlayacaksın. Bu da 4 adım(log 16 = 4) 16 kutu çizeceğin ve 0.4 saniyede biteceği anlamına geliyor. Peki ya 1,024 kutu çizmen gerekirse? Bu da log 1,024 = 10 adımdan 1 saniyede biter. Bunlar ilk algoritmayı kullandığımızda alacağımız sonuçlardı.

İkinci algoritma daha yavaş, O(*n*) kadar sürüyor. 16 adımda 16 kutu, 1,024 adımda da 1.024 kutu çizebiliyor. Peki bu saniyede ne kadar eder?

İşte hızlıdan yavaşa doğru bir ızgara çizmenin ne kadar süreceği:
![image](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/0c97f86f-5957-46d7-8143-3f508f089b04)

Daha bir sürü çalışma süresinden bahsedebiliriz ama bunlar en yaygın 5'i.

Aslında bu bir basitleştirme işlemi çünkü Big O'yu adım sayısına bu kadar iyi geçiremezsiniz ama şimdilik yeterli. Bir kaç algoritma daha öğrendikten sonra 4. ünitede Big O gösteriminden tekrar bahsedeceğiz ama şimdilik bilmemiz gerekenler şunlar:

- Algoritma hızı saniyeyle ölçülmez ama adım sayısına göre büyür.
- Bunun yerine girdinin boyu artarken çalışma süresinin ne kadar hızlı arttığından bahsediyoruz.
- Algoritmanın çalışma hızı Big O gösterimiyle ifade edilir.
- O(log *n*), O(*n*)'den daha hızlıdır ve girdinin boyu artarken daha da hızlanır.

### Egzersizler
Aşağıdaki durumların çalışma süresini Big O cinsinden ifade edin.

**1.3** Elinde bir isim var ve telefon defterinden telefon numarasını arıyorsun.

**1.4** Elinde bir telefon numarası var ve telefon defterinden ismini arıyorsun.(İpucu: Tüm kitaba bakmak zorundasın!🤫)

**1.5** Telefon defterinden herkesin telefon numarasına bakmak istiyorsun.

**1.6** Sadece A'ların telefon numarasına bakmak istiyorsun.(Bu zor olanı! 4. bölümde bundan bahsedeceğiz. Cevaba bakmayı unutma, şaşırabilirsin!😏)

### Gezgin satıcı 
Son bölümü okuduktan sonra "Asla O(*n*!) süren bir algoritma kullanmam!" demiş olabilirsin. İzin ver yanlış olduğunu göstereyim. Bu örnekte çalışma süresi çook kötü olan bir algoritma kullanacağız. Bu bilgisayar bilimlerinde çok ünlü bir problem çünkü korkutucu bir şekilde büyüyor ve bilim insanları bile bunun hızlandırılamayacağını düşünüyor. İşte *gezgin satıcı* problemi...
![image](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/15a28c0b-f50d-4a4c-8682-ac767bd80b22)

Bir satış elemanı var ve 5 şehre gitmesi gerekiyor.
![image](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/2c226256-5024-4446-a319-41f79ba1ea51)

Adı Opus olan bu satış elemanı bu 5 şehri en kısa yolu kullanarak dolaşmak istiyor. En kısa yolu bulmanın bir yolu olabilecek tüm sıraları incelemek.
![image](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/82b7bcd8-040e-4fc1-a5f6-4afd851544c7)

Tüm uzaklıkları inceleyip en kısasını seçiyor. 5 şehir için 120 farklı yol var, bu yüzden de 120 adımda tamamlayabilir. 6 şehir olduğunda 720, 7 şehre çıktığında ise 5,040 adım sürüyor.🤯
![image](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/4b8f0103-38d5-4e21-be88-a5edb47f919c)

Genel olarak *n* eleman için *n!* tane adımda tamamlanıyor, bu yüzden de bu O(*n!*)-*factorial time(faktöriyel süre)- oluyor. Bu da çok küçük sayılar dışında yapılacak bir sürü adım demek. Hatta 100'den fazla şehri işin içine kattığımızda çözmek imkansız oluyor.-Güneş çözümden önce yok olacaktır.💥

Bu korkunç bir algoritma ve Opus farklı bir şey kullanmalı, değil mi? Ama ne yazık ki yapamaz. Bu bilgisayar bilimlerindeki çözülememiş problemlerden biri. Bunun için bilinen daha hızlı bir algoritma yok ve bilim insanları bunun çözülmesinin *imkansız* olduğunu söylüyor. Bu konuda yapabileceğimiz en iyi şey yaklaşık bir sonuç bulmak, bunu da 10. bölümde yapacağız.

> Eğer ki ileri seviye biriysen, binary search trees konusuna bakabilirsin! Son bölümünde bunların kısa bir açıklaması var.

### Özet
- Binary search, simple search'ten daha hızlıdır.
- O(log *n*), O(*n*)'den daha hızlıdır ve eleman sayısı arttıkça daha da hızlanır.
- Algoritma hızı saniyeyle ölçülmez.
- Algoritmanın süresi *büyümesine* bakılarak ölçülür.
- Algoritma süresi Big O gösterimi ile ifade edilir.
