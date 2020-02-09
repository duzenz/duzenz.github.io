---
title: "Geçici Değişken Kullanmadan Değişken Değerlerini Yer Değiştirme"
read_time: true
tags:
	- değişken yer değiştirme
	- geçici değişken
	- swap
---

Bu yazımda daha önceden bilmediğim görünce bunu da kullanabilirmişiz dediğim bir yapıdan bahsedeceğim.
Kodlama yaparken bazen (özellikle sıralama algoritmalarında) iki tane değişkenin değerini birbirleriyle yer değiştirmek gerekir. 
Bunu yaparken klasik olarak öğretilen yol geçici bir değişken tutmaktır ve aşağıdaki kodu uygulamaktır.

```java
public class SwapWithTemp {
	public static void main(String[] args) {
		int x = 10, y = 20, temp;
		System.out.println(&quot;x : &quot; + x);
		System.out.println(&quot;y : &quot; + y);
		temp = x;
		x = y;
		y = temp;
		System.out.println(&quot;x : &quot; + x);
		System.out.println(&quot;y : &quot; + y);
	}
}
```

#### Çıktı
> x : 10
> y : 20
> x : 20
> y : 10


Yeni öğrendiğim yolda ise br temp değişkeni kullanılmıyor ve yer değiştirme işlemi aritmetik işlemlerle yapılıyor. 
Bunun için uygulayacağınız kod ise:

```java
public class SwapWithoutTemp {
	public static void main(String[] args) {
		int x = 10, y = 20;
		System.out.println(&quot;x : &quot; + x);
		System.out.println(&quot;y : &quot; + y);
		x = x + y;
		y = x - y;
		x = x - y;
		System.out.println(&quot;x : &quot; + x);
		System.out.println(&quot;y : &quot; + y);
	}
}
```

#### Çıktı
> x : 10
> y : 20
> x : 20
> y : 10


Bu iki yöntem arasındaki temel farka gelirsek birisi bir değişken daha fazla kullanıyor ve hafızanızda daha fazla yer kaplıyor. 
Diğer yöntem de ise fazladan bir değişken yok ama aritmetik işlemler var bu da hızınızı azaltıyor bir miktar. 
Hangi algoritmayı kullanacağınız sizin gereksinimlerinize kalmış.
