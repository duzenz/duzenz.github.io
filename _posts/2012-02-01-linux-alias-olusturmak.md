---
title: "Linux'ta Alias Oluşturmak"
read_time: true
categories:
  - bash
tags:
  - linux
  - alias
---

Linux terminal ekranında çalışırken sürekli bir karmaşa yaşamaya başladığınız dönemler olur. Yok şu siteye ping at yok şu uzak makineye bağlan. 
Bunların hepsini de elle yazmak zor olacağından genellikle alias oluşturma yöntemi kullanılır.

Örneğin google.com adresine ping atan bir kodumuz olsun. Terminalizini açın ve aşağıdaki kodu yazın.

```bash
test@test:~$ ping www.google.com
```

Bunu yazıp enter tuşuna bastığınızda google a ping atılır ve gelen sonuçlar ekrana yazdırılmaya başlanır. 
Ancak bunu her seferinde elle yazmak zahmetli bir iştir. Bunun için **pingAt** adında bir alias oluşturacağım ve bunu kullanarak ping atma işlemini yapacağım.

Aliasları **.bash_profile** adlı gizli dosya içinde tanımlayacağız.
Terminalizi tekrar açın. **gedit** programı yüklü olanlar için aşağıdaki gibi yapabilirler herhangi bir text editör ile dosyayı açıp içini dolduracağız sadece. 

```bash
test@test:~$ gedit .bash_profile
```

yazdıktan sonra açılan dosyanın içine 

```bash
alias pingAt='ping www.google.com'
``` 

satırını yapıştırın ve kaydedip terminal ekranına dönün. Ancak yazdığınız alias hala çalışmaz. 
Çalışması için terminalizin restart edilmesi gerekmekte ister kapatıp açın isterseniz aşağıdaki kodu terminal ekranına yapıştırın.

```bash
test@test:~$ source .bash_profile
``` 

Daha sonra da terminale 

```bash
test@test:~$ pingAt
``` 

yazıp entera bastığınızda önceden yazdığınız kodun çalıştığını göreceksiniz. 
İşleri hızlandırmak için iyi bir yöntem.