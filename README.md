<p align="center">
  <img width="220" height="220" src="https://i.imgur.com/vYE79I9.png">
</p>

[![Build Status](https://travis-ci.com/guanicoe/ESPBug_PIO.svg?branch=master)](https://travis-ci.com/guanicoe/ESPBug_PIO)


# Bu proje willmendil'in orijinal ESPBug projesinin Türkçe çeviri versiyonudur.

# ESPBug
ESPBug, ESP8266 tabanlı (NodeMCU gibi) kartlarda çalışan bir phishing programıdır. Bir sosyal mühendislik aracı olan ESPBug, yeni bir Wifi ağı oluşturarak kullanıcıların kimlik bilgilerini elde etmeyi hedefler.

# UYARI
Bu repo'da açık bir şekilde verilen tüm kaynak kodlar eğitimsel amaçlar içindir. Kimlik hırsızlığı bulunduğunuz yere göre yasa dışı olabilir. Bu araç ile yaptığınız hiçbir eylemden sorumlu olmadığımı belirtirim. Bu kod hiçbir garanti ve emel ile verilmemiştir. **Dikkatli kullanın be yani. Tamam mı?**

# Nasıl çalışır? & Nasıl yapılır?

[![Pocket board for phishing passwords - ESPBUG](https://i.imgur.com/PYyQzfI.jpg)](https://www.youtube.com/watch?v=X95rtPqSzw4 "Pocket board for phishing passwords - ESPBUG - Click to Watch!")

Aşağıda uygulama içerisinden alınan birkaç ekran görüntüsünü bulabilirsiniz. İlk ekran görüntüsü kurban tarafından görüntülenen ekrana aittir. **Peki siz şifrenizi girer miydiniz?**

![Imgur0](https://i.imgur.com/q5C7H7s.png)
![Imgur1](https://i.imgur.com/qYyqwnQl.jpg)

ESPBug'a bağlandığınız zaman, **espportal** sayfasına gidin (e.g. `http://espbug.com/espportal`). Bir user-pass prompt'u ile karşılaşacaksınız. Varsayılan kullanıcı adı şifre kombinasyonu `Kullanıcı adı: espbug` ve `Şifre: password` şeklindedir. Buradan sonra ana sayfaya yönlendirileceksiniz

![Imgur2](https://i.imgur.com/NgNZkYol.jpg)
![Imgur3](https://i.imgur.com/OgYxvRyl.jpg)

Saldırıyı başlatmak için ayarlara gidip bazı düzenlemeler yapmanız gerekir. İhtiyacınız olacak tüm ayarlar ve açıklamaları aşağıda verilmiştir

![Imgur4](https://i.imgur.com/lxz6Apwl.jpg)
![Imgur5](https://i.imgur.com/LeBXPztl.jpg)

 - Şapka rengi (seçimler: **Black Hat** veya **White Hat**): Bu seçenek size bir hırsız mı yoksa bir fedai mi olacağınız hakkında seçim hakkı tanır. **White Hat** opsiyonu kullanıcıyı yaşadığı şeyin ne olduğunu ve phishing saldırılarından nasıl korunabileceğini anlatan bir siteye yönlendirir. **Black Hat** opsiyonu kullanıcı kimlik bilgilerini girdiği anda kullanıcının bağlantısını keser.

 - Portalı etkinleştir (seçimler: **ON** veya **OFF**): Basitçe, portalı aktifleştirir. Her saldırıdan sonra tekrardan açılması gerekir.
 - SSID: Oluşturulacak Wifi ağının ismini belirleyin. Varsayılan olarak wifi adı **espbug**'dır. Bir phishing saldırısından sonra wifi adını otomatik olarak varsayılan ismine geri döndürür. Bu sayede oltaya takılan bilgilere erişebilirsiniz.
 - Password: Oluşturacağınız wifi ağının şifresidir. Varsayılan olarak şifre **espbug**'dır. Herhangi bir saldırı gerçekleştirirken bu kısmı boş bırakmak isteyebilirsiniz. Ve tekrardan, herhangi bir phishing saldırısından sonra parola kendini otomatik olarak varsayılana sıfırlar. **Bu ayarı kaynak kodundan değiştirebilirsiniz.**
 - Kanal (seçimler: **1** - **14**): 2.4GHz bandında kanal seçmenize olanak tanır.
 - Hidden (seçimler: **YES** veya **NO**) **Burası çokomelli!** Varsayılan olarak, Wifi ağı gizlidir. Yani **espbug**'a bağlanmak için **ssid ve şifre** bilgilerini manuel olarak girmelisiniz. Herhangi bir saldırıdan sonra wifi kendini otomatik olarak gizli moda alır. Phishing saldırılarından önce bu ayarı **NO**'ya getirmek isteyebilirsiniz.
 - IP: **espbug**'ın IP adresi. Varsayılan olarak `192.168.1.1`'e ayarlıdır. Ancak herhangi bir saldırı durumunda bu ayarı `8.8.8.8` olacak şekilde değiştirebilirsiniz. Bu, kullanıcının otomatik olarak login ekranına yönlendirilmesini sağlar.
 - Gateway: IP ile aynı, bu değerleri aynı tutun.
 - Subnet: Sadece ne yaptığınızı biliyorsanız bu ayarı değiştirin
 - Username: Web arayüzünün girişinde kullanılan kullanıcı adıdır. Varsayılan olarak **espbug**'dır.
 - Password: Web arayüzünün girişinde kullanılan şifredir. Varsayılan olarak **espbug**'dır.

# Kurulum

Programın yazımı ve kurulumu için "atom ve pateformIO" kullanılmıştır. Ancak kurulumu sizler de kendiniz gerçekleştirebilirsiniz. Kodun eski versiyonunu Arduino IDE ile compile edebilirsiniz. [https://github.com/willmendil/ESPBug](https://github.com/willmendil/ESPBug). 

Çevirmenin kurulum tavsiyesi:
`/src` klasörü içerisindeki espbug.ino dosyasını Arduino IDE'si ile açın. Sizden ilgili ino dosyası için yeni bir klasör açmanızı isteyecek. Bu klasörü oluşturup `/src` klasörü içerisinde kalan diğer her şeyi yeni klasöre kopyalayın ve IDE üzerinden ESP8266 üzerine upload edin.


# CREDITS / İlham kaynakları

Kodun çoğu farklı repo'lardan esinlenilmiştir. Burada onlara da değinmek istedim.
* [ESPortalV2] - https://github.com/exploitagency/ESPortalV2
* [github-ESPortal] - https://github.com/exploitagency/github-ESPortal
* [esp8266_deauther] - https://github.com/spacehuhn/esp8266_deauther


### Bilinen Buglar
- Beyaz şapka modunda DNS `8.8.8.8` iken  açıklama sayfası otomatik olarak kapanıyor. 
- Bağlı cihazların IP adresi bazen yanlış şeyler gösterebiliyor.

Lisans
----

  GNU GENERAL PUBLIC LICENSE


**Ücretsiz Yazılım, Her zaman her yerde!**


   [ESPortalV2]: <https://github.com/exploitagency/ESPortalV2>
   [github-ESPortal]: <https://github.com/exploitagency/github-ESPortal>
   [esp8266_deauther]: <https://github.com/spacehuhn/esp8266_deauther>
   [esp8266]: https://rcl.lt/files/c59c2f4d86f239f67a86-128x128
   [Arduino IDE]: https://www.arduino.cc/en/main/software
