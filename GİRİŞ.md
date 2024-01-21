# Giriş
*Algoritma*, bir görevi yerine getirmeye yönelik bir dizi talimattır. Aslında her kod parçası bir algoritma olarak adlandırılabilir, ancak konumuz bu değil. Bu kitaptaki algoritmaları hızlı oldukları ya da ilginç problemleri çözdükleri için seçtim. İşte bazı önemli noktalar:  
- İlk bölümde binary search'ten ve bir algoritmanın kodunu nasıl hızlandırabileceğinden bahsediyoruz. Mesela gereken adım sayısını 4 milyardan 32 ye düşürüyoruz!😲
- Bir GPS cihazı, hedefinize giden en kısa rotayı hesaplamak için grafik algoritmaları (6, 7 ve 8. bölümlerde bahsedeceğiz) kullanır.🚘
- Dinamik programlama(9. bölümde konuşacağız) ile dama oynayan bir yapay zeka algoritması kullanabilirsiniz.♟️
Tüm durumlarda algoritmayı açıklayıp örnekler vereceğim. Sonrasında da algoritmanın çalışma süresini Big O üzerinden değerlendireceğim. Son olarak, aynı algoritma ile başka ne tür problemlerin çözülebileceğini açıklayacağım.

### Performans hakkında neler öğreneceksiniz?
İyi haber şu ki, bu kitaptaki her algoritmanın bir uygulaması muhtemelen favori programlama dilinizde mevcuttur, bu nedenle her algoritmayı kendiniz yazmak zorunda değilsiniz! Ancak, kıyaslamaları anlamadığınız sürece bu uygulamalar bir işe yaramaz. Bu kitapta, farklı algoritmalar arasındaki kıyaslamaları öğreneceksiniz: Merge sort mu yoksa quicksort mu kullanmalısınız? Array mi yoksa liste mi kullanmalısınız? Sadece farklı bir veri yapısı kullanmak bile büyük bir fark yaratabilir.
### Problem çözme hakkında neler öğreneceksiniz?
Şimdiye kadar aklınıza gelmemiş olabilecek sorunları çözme tekniklerini öğreneceksiniz. 
- Video oyunları yapmayı seviyorsanız, grafik algoritmaları kullanarak kullanıcıyı takip eden bir yapay zeka sistemi yazabilirsiniz.
- k-nearest neighbors kullanarak bir öneri sistemi oluşturmayı öğreneceksiniz.
- Bazı problemler zamanında çözülemez! Bu kitabın NP-complete problemlerden bahseden bölümü, bu problemleri nasıl tanımlayacağınızı ve size yaklaşık bir cevap veren bir algoritmayı nasıl bulacağınızı gösterir.
Daha genel olarak, bu kitabın sonunda, yaygın olarak kullanılan algoritmalardan bazılarını bileceksiniz. Daha sonra yeni bilgilerinizi yapay zeka, veritabanları ve benzeri alanlara yönelik daha spesifik algoritmalar hakkında bilgi edinmek için kullanabilirsiniz. Ya da iş yerinde daha büyük zorlukların üstesinden gelebilirsiniz.

| What you need to know |
| ----------- |
| Bu kitaba başlamadan önce temel cebir bilgisine sahip olmanız gerekir. Hadi şu fonksiyona bir bakalım: f(x) = x × 2. f(5) kaçtır? Eğer 10 cevabını verdiyseniz, Hazırsın.
Ayrıca, bir programlama dili ile aşinaysanız, bu bölümdeki(ve bu kitaptaki) içerikleri daha kolay anlarsınız. Bu kitaptaki tüm örnekler Python ile yazıldı. Hiçbir programlama dilini bilmiyorsan ve öğrenmek istiyorsan Python öğren-Yeni başlayanlar için harikadır. Eğer ki Ruby gibi başka bir dil biliyorsan da sorun yaşamazsın.|
