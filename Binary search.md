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

|**Not**|
|-------|
|Bu kitapta logaritma hakkında çokça bahsedeceğim, o yüzden logaritmayı kavramalısınız. Eğer ki bilmiyorsanız Khan Academy'nin bunu açıklayan güzel bir videosu var.[videoya buradan ulaşabilirsiniz](https://tr.khanacademy.org/math/algebra2/exponential-and-logarithmic-functions/introduction-to-logarithms/v/logarithms)|

|**Not**|
|-------|
|Binary search sadece listen sıralı ise çalışır. Mesela telefon defterindeki isimler alfebetik bir şekilde sıralıdır,bu yüzden de bir isim ararken binary search kullanabiliriz. Peki ya isimler sıralı olmasaydı?🤔|

Hadi Python'da binary search'ün nasıl yazıldığına bakalım. Buradaki kodda array kullanıldı(Eğer ki array'in nasıl çalıştığını bilmiyorsan, endişelenme. Bir sonraki bölümde göreceğiz😉.Sadece bir dizi elemanı array adı verilen ardışık kutularda saklayabileceğinizi bilmen yeterli. Kutular 0'dan başlayarak numaralandırılır: ilk kutu #0 konumundadır, ikincisi #1, üçüncüsü #2 ve bu şekilde devam eder.)

**Binary search** fonksiyonu bir eleman ve sıralanmış bir array alır. Eğer alınan eleman array'in bir elemanıysa fonksiyon onun konumunu döndürür. Array'in hangi kısmında arama yapılacağına dikkat et, en başta bu tüüm array'dir.🙃
![1 12](https://github.com/Dapjeongneo-aysenur/grooking_algorithms/assets/94196503/e8c9a628-4cbb-4994-a30c-a47ce94482b7)

Her seferinde ortadaki elemanı kontrol edersin:
