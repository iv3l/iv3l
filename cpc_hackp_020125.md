=================================================
!!! FR !!!
Ouvrir le fichier PCAP dans Wireshark
Clic droit sur un paquet : Suivre le flux TCP

On peut voir dans le flux que flag.zip a été transféré vers 172.20.20.133:20200.

Utiliser le filtre Wireshark :
  ip.addr == 172.20.20.133 && tcp.port == 20200  

Clic droit à nouveau, suivre le flux.
Sauvegarder les données binaires dans un fichier ZIP à l'aide d'une application de conversion hexdump comme xxd :
$ echo -n "504b0304140000000800a231825065235c39420000004700000008001c00666c61672e7478745554090003bfc8855ebfc8855e75780b000104e803000004e80300000dc9c11180300804c0bfd5840408bc33630356e00568c2b177ddef9eeb5a8fe6ee06ce8e5684f0845997192aad44ecaedc7f8e1acc4e3ec1a8eda164d48c28c77b7c504b01021e03140000000800a231825065235c394200000047000000080018000000000001000000a48100000000666c61672e7478745554050003bfc8855e75780b000104e803000004e8030000504b050600000000010001004e000000840000000000" | xxd -r -p > flag.zip  

Vérifier le type du fichier :
$ file flag.zip  
  flag.zip: Zip archive data, at least v2.0 to extract, compression method=deflate  

Extraire le fichier ZIP :
$ unzip flag.zip  
  Archive:  flag.zip  
    inflating: flag.txt  

Afficher le contenu du fichier flag.txt :
$ cat flag.txt  
  FCSC{6ec28b4e2b0f1bd9eb88257d650f558afec4e23f3449197b4bfc9d61810811e3}  
==================================================
!!!  ENG !!!
Open PCAP File in Wireshark
Right Click on packet: Follow TCP Stream
We can see in stream that flag.zip was transferred to 172.20.20.133:20200
Use wireshark filter: ip.addr == 172.20.20.133 && tcp.port == 20200
Right Click again follow stream
Save the binary to a zip using a hexdump app. xxd :
$ echo -n "504b0304140000000800a231825065235c39420000004700000008001c00666c61672e7478745554090003bfc8855ebfc8855e75780b000104e803000004e80300000dc9c11180300804c0bfd5840408bc33630356e00568c2b177ddef9eeb5a8fe6ee06ce8e5684f0845997192aad44ecaedc7f8e1acc4e3ec1a8eda164d48c28c77b7c504b01021e03140000000800a231825065235c394200000047000000080018000000000001000000a48100000000666c61672e7478745554050003bfc8855e75780b000104e803000004e8030000504b050600000000010001004e000000840000000000" | xxd -r -p > flag.zip

$ file flag zip
	flag.zip: Zip archive data, at least v2.0 to extract, compression method=deflate
$ unzip flag.zip
	Archive:  flag.zip
		inflating: flag.txt

$ cat flag.txt
	FCSC{6ec28b4e2b0f1bd9eb88257d650f558afec4e23f3449197b4bfc9d61810811e3}
