## 1. Bölüm
**1.1->** 128 ismin olduğu sıralı bir listen olsun, sen de binary search kullanarak bu listede arama yapıyorsun. Araman en fazla kaç adımda biter? 1.2 Listenin boyunu iki katına çıkardığını düşünelim. Şimdi en fazla kaç adımda bitirirsin?

*Cevabı:* 7
**1.2->** Listenin boyunu iki katına çıkardığını düşünelim. Şimdi en fazla kaç adımda bitirirsin?

*Cevabı:* 8
**1.3->** Elinde bir isim var ve telefon defterinden telefon numarasını arıyorsun.

*Cevabı:* O(log*n*)
**1.4->** Elinde bir telefon numarası var ve telefon defterinden ismini arıyorsun.(İpucu: Tüm kitaba bakmak zorundasın!🤫)

*Cevabı:*O(*n*)
**1.5->** Telefon defterinden herkesin telefon numarasına bakmak istiyorsun.

*Cevabı:*O(*n*)
**1.6->** Sadece A'ların telefon numarasına bakmak istiyorsun.

*Cevabı:*O(*n*) "26 ögeden sadece birine bakıyorum, o yüzden O(*n*/26) olmalı." diyebilirsin. Şimdi sana basit bir kural söyleyeceğim; eklenen, çıkarılan, çarpılan ve bölünen sayıları görmezden gel. Bak bu gösterimlerin hiç biri doğru bir Big O gösterimi değil:O(*n* + 26), O(*n* - 26), O(*n* * 26), O(*n* / 26) ve hepsinin asıl gösterimi O(*n*)! Nedenini merak ediyorsan 4. bölümdeki "Big O gösterimini gözden geçirme" kısmına bak ve sabitler kısmına dikkat et.(Bu soruda 26 sabitti.)
