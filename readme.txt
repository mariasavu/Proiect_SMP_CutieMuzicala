	Cutie muzicala

	Un termen destul de interpretabil la nivelul limbii romane. O prima abordare pe care a primit-o acest termen, se
implementa cu ajutorul unei placi arduino insotita de un foto senzor si bineinteles un buzzer. 
	Ideea de muzica nu e interpretabila, asta inseamna ca buzzer ul era un element cheie in orice implementare a proiectului
caci vorba aia, "ce e muzica fara sonor?". Placuta arduino, sau fake-ul chinezesc care indeplinste aceeasi functie, este de asemenea, 
indispensabila. 
 	Trebuie sa recunosc ca ideea de a folosi hartie perforata si un foto senzor pentru a citi o nota si apoi sa o redau cu ajutorul buzzerului,
   mi s-a parut un pic departe de definita pe care o aveam eu in cap. 
 	"Cutie muzicala" = cutie care produce muzica, de aici a inceput si cautarea mea pe net. Am gasit mai multe idei de proiecte, dar  ce mi a 
   captat atentia in special au fost urmatoarele : Implementarea unui pian de jucarie:
   https://create.arduino.cc/projecthub/executeli/unravel-preset-piano-easy-arduino-even-a-ghoul-can-make-it-17c472?ref=tag&ref_id=piano&offset=2
   implementarea unei cutii care atunci cand este deschisa, canta o melodie, iar atunci cand se inchide cutia se opreste. 
   https://create.arduino.cc/projecthub/slagestee/rickroll-box-3c2245?ref=similar&ref_id=353976&offset=1, asa a pornit varianta pe care am implementat-o eu
  
	Un fel de saorma cu de toate: scoate sunet? Da, Poti sa canti tu ceva la ea? Da, Tace cand o inchizi? Da.
  Se pare ca raspunde la nevoile esentiale ale unui uitilizator de cutie muzicala.

	Desrierea componentelor

	Acum ca am terminat cu intrdocerea si am divulgat si sursele de inspiratie, pot sa trec sa explic exact ce am facut. Creatia mea se numeste Muzica la cutie.
	Componentele sunt urmatoarele: 
	*Placuta Fake Arduino (care reprezinta creierul cutiei mele)
	*Un buzzer (despre care am stabilit ca este componenta principala)
	*5 butoane de tip push buttons 4 pentru note si unul care reda o melodie inregistrata 
	* 5 rezistente de 1k ohm pentru conectarea butoanelor 
	* o rezistenta de 10k ohm pt fotorezistor
	*fire, bieninteles
	*un rezistor foto senzor care implementeaza functionalitatea cea mai draguta a cutiei. 
		
	* o baterie care imi alimenteaza mie saorma la farfurie 

	Descrierea algoritmului folosit

	Implenentarea este destul de usor de inteles, nu are o dificultate crescuta. La incpeut are loc definirea fiecarei note pentru a putea implementa 
	orice cantec se cere la dedicatii, urmeza definirea pinilor si setarea lor in void setup(). In void loop() se intampla urmatoarele:
	Pentru fiecare buton am implementat o anumita nota, iar butonul 5, seteaza variabila flag2 cu valoarea true.
	 Poate va intrebati de ce este necesar acest lucru?
 	Simplu, pentru a putea folosi varianta de freestyle a cutiei, sa alegi tu notele pe care vrei sa le auzi, trebuia sa opresc piesa care canta in mod automat cand se deschide cutia.
	O sa incep sa explic care e faza cu flag1, sa o iau in ordine, ce diferentiaza cutia inchisa de cutia deschisa este gradul de luminozitate, logic.
	Senzorul meu indica o valoare mai mare pentru cand este lumina si scade progresiv cand se intuneca. Un rationament destul de simplu de implementat. Pragul de threshold este dat de mine
	in urma mai multor verificari in raport cu pragul de deschidere de la care vreau sa inceapa melodia. 
	Buun, flag1 este, asadar, variabila care imi indica mie ca s-a deschis cutia si trebuie sa inceapa piesa.
	Revenind la flag2, pentru a putea utiliza modul de "pian de jucarie" al cutiei, sau cum i-am mai zis eu "modul freestyle". Am decis sa las piesa sa cante o singura data, dupa 
	flag2 se face fals, oprindu-se astfel piesa  de introducere, permitand utilizatorului sa-si incerce dexteritatea la butoane. 
	Daca totusi se doreste ascultarea piese introductive, atunci se poate apasa pe butonul 5 si piesa va porni (pentru ca prima conditie de cutie deschisa este deja ideplinita, flag1 = true).	
	Pentru melodie se definesc notele in succesiunea lor, apoi se ofera si durata fiecarei note. Astfel se creaza si piesa introductiva.

	Concluzii
	Cred ca acest proiect este unul simplut, cu o implementare modesta, la care se pot aduce imbunatatiri precum, utilizarea API urilor care imi permit redarea unor piese intregi,
	nu doar cele "handmade". Poate chiar si printr-o cutie mai frumoasa se poate imbunatatii. Mie mi s-a parut o combinatie interesanta de idei si am invatat destul de multe
	lucruri noi lucrand la acest proiect.
	
