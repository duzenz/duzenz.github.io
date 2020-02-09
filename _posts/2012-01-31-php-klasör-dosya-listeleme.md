---
title: "Php ile Bir Dizindeki Klasör ve Dosyaları Listelemek"
read_time: true
categories:
  - php
tags:
  - dosya listeleme
  - php
  - dizindeki dosyaları listele
---

Php ile bir klasördeki veya bunu altındaki herhangi bir klasördeki dizinleri ve dosyalrı listeleyen ve bunların toplam sayısını veren kod parçaçığı:

```php
$klasorSayisi = $dosyaSayisi = 0;
// . içinde bulunduğunuz klasör
// alt klasörlerde çalışmak için opendir('dosya_yolu')
if ($klasor = opendir('.')) {
    while (false !== ($girdi = readdir($klasor))) {
        if ($girdi != "." &amp;&amp; $girdi != "..") {
            if (is_dir($girdi)) { //Klasör mü kontrolü
                echo "Klasör => " . $girdi . "<br>";
                $klasorSayisi++;
            } else {
                echo "Dosya   => " . $girdi . "<br>";
                $dosyaSayisi++;
            }
        }
    }
    echo "Toplam Klasör Sayısı : " . $klasorSayisi . "\n";
    echo "Toplam Dosya Sayısı : " . $dosyaSayisi;
    closedir($klasor);
}
```