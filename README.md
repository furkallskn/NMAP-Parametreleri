# NMAP-Parametreleri-ve-Adimlar




NETDISCOVER
-----------------------

netdiscover -i (bağlı olduğun ağ interface) -r (iprange) -c (kaç tane arp paketi)



NMAP
-----------------------

Hedef sorgusu
-------------
nmap 10.0.2.5 >>> Bu kodun çıktısı bu makinenin açık olan portlarını gösterir. top 1000 portu gösterir. <br>
nmap 10.0.2.0/24 >>> Bu kod 10.0.2.0' dan 10.0.2.255'e tarama gerçekleştirir. top 1000 portu gösterir. <br>
nano ip-list >>> birden fazla range'i tek bir dosyaya yazdıktan sonra. <br>
nmap -iL ip-list >>> dosya icindeki listedeki ipleri tarar. <br>
nmap 192.168.1.0/24 --exclude 192.168.1.200 >>> exclude parametresine girilen değer hariç hepsini tara.


Port sorgusu
------------
nmap -p (port belirtilir.) 192.168.1.0/24 --open ( açık olan portları göster ) <br>
nmap -p- 192.168.1.100 --open >>> bu kod hedef ip'de bütün portları tarar ve açık olanları gösterir.


Tarama Tipleri
--------------
-sS yani synscan yapar. ( SYN+ACK dönüşü geldiğinde seçili port taraması sonlanır ve açık olarak kabul edilir.) <br>
-sT TCPsycan yapar. (3'lü handshake'i tamamlayarak arama yapar.) <br>
-sP Pingsycan yapar netdiscover yerine kullanılabilir. <br>
-sU UDPsycan (udp port araması yapar.) <br>
-sN Nullscan 


Ek parametreler
---------------
-O (işletim sistemi ve versiyonu) <br> 
-sV (portların versiyon taramasını yapar.) <br>
-A (hem işletim sistemi, hem versiyon taraması) <br>
-oN dosya (ekrana yazdırılan çıktıyı birebir dosyaya yazdırır) <br>
-T1,T2,T3,T4,T5 (Zamanlama parametreleridir.En güvenli ve yavaşı T1,En riskli ve hızlı T5) <br>
-Pn (direkt port taraması yapar ve pingleme yapmaz.) <br>
-n  (dns çözümlemesi yapmadan tarama yapar.) <br>
-vv (Tarama yapılırken yapılan işlemleri gösterir. <br>
-sC (karşı tarafın zaafiyetine uygun kendi içinde bulunan scriptlerden kullanabileceği script olup olmadığını kontrol eder.)



Zaafiyet Taraması
-----------------
nmap (ip) --script-smb-vuln-* -p 445 (port=445 üzerinde zaafiyet taraması yapar.)



Firewall Bypass
---------------
nmap (ip) -f (paketleri parçalayarak nmap taraması olduğunun anlaşılmasının önüne geçilebilir.f,ff) <br>
nmap (ip) -D (localip) (gürültü çıkarır karşı tarafa sizin ip adresinizi unutturmaya yönelik önlem) <br>
nmap --script-firewall-bypass (ip)  (Birden fazla metodu kullanarak yakalanma riskinizi farkedilme riskinizi azaltir.)
