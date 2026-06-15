# Bakalářská práce
Systém pro automatizaci kurníku s detekcí snesených vajec

## Zadání
1. Prostudujte možnosti automatizace uzavírání kurníku, možné metody detekce snesených vajec a dostupné možnosti komunikace a připojení zařízení do IoT sítě (např. NB-IoT, WiFi, LoraWAN).
2. Navrhněte systém pro automatické otevírání a uzavírání dvířek kurníku s možností rozšíření o jednotky se senzory ve snáškových hnízdech (min. 5 hnízd). Prostudujte možnosti napájení z akumulátoru nebo
   fotovoltaického panelu. Proveďte analýzu možnosti přenosu dat do cloudu a jejich zobrazení uživateli včetně historie snášek a možnosti vzdáleného ovládání, například skrze aplikaci.
3. Na základě analýzy navrhněte způsob vzdálené uživatelské interakce pro zobrazení stavu dvířek, manuální ovládání a počítání snesených vajec.
4. Navrhněte schéma zařízení, které bude obsahovat mikrokontrolér, komunikační modul, senzory, řízení dvířek, napájecí/nabíjecí obvody. Dbejte na nízký příkon celého zařízení. Proveďte návrh desky plošných
   spojů.
5. Zkonstruujte hardwarovou realizaci navrženého systému. Osaďte a zprovozněte řídicí elektroniku. Vytvořte ovládací firmware. Realizujte přenos dat ze zařízení k uživateli včetně ovládacího rozhraní a
   možnosti zobrazení historie.
6. Ověřte funkčnost systému experimentálním měřením a vyhodnoťte spolehlivost detekce a ovládání.
7. Zveřejněte veškeré výrobní podklady na vhodné platformě (např. GitHub).

V rámci semestrálního projektu řešte body 1. – 4.  
Pozn. Předpokládá se, že student má možnost otestovat zařízení v reálném nasazení.

## Koncept
Celý systém bude umístěn pod stříškou, směrem na jih, na vnější straně kurníku. Tudíž panel nikdy nezasněží, využiji co možná nejvíce sluneční energie a z velké části eliminuji vliv amoniaku ze slepičího trusu.

### Napájení
Solární panel bude společně s akumulátorem, jež bude umístěn v první krabičče (3D tisk), vystlané 3cm vrstvou extrudovaného polystyrenu (styroduru), celý systém zásobovat elektřinou. Krabička bude disponovat dírami s gumovými kabelovými průchodkami.

### Řízení
Řídicí jednotkou bude mikrokontroler STM32 se zabudovaným LoRaWAN modulem. Tento procesor dokáže přejít do tzv. režimu hlubokého spánku (Stand By) a tím ušetřit velké množství energie, když není potřeba, aby pracoval. Pro vývoj bude použita vývojová deska stejného typu jako bude čip na finální verzi. U čipu bude jako anténa sloužit 86mm (868 Hz) dlouhý měděný kabel (čtvrtvlnný monopól), směřující směrem vzhůru.

### DPS
Deska plošných spojů s veškerou elektronikou se bude nacházet v druhé krabičce (3D tisk) s anténní veží a 2 cm trubičkou pro lanko

### Konstrukce
Na stěnu kurníku budou pomocí vrutů přivrtány dřevěné hranolky, po jejichž bocích budou připevněny plechové drážky z hliníku, ve kterých budou jezdit plastová dvířka. Na vrchní hraně dvířek bude umístěno nerezové závěsné očko, kterým bude prostrčeno nerezové ocelové lanko, zajištěno lankovou spojkou. Tohle lanko povede do druhé krabičky (3D tisk), ve které bude špulka, kterou bude provlečeno a upevněno za pomocí lankové spojky. Špulka bude přes stavěcí šroub (červíka) přimontována ke hřídeli motorku.

## Prototyp
Solární panel: 12V  
Solární regulátor napájení: PWM 6V/12V  
Akumulátor: 6V olověný AGM bezúdržbový  
