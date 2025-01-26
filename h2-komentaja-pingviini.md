# Tehtävä x) Command line basics revisited
**_NOTE:_** Lista hieman kattavampi omia muistiinpanoja varten.

- Kansioiden välillä siirtyminen ja tarkastelu
  - Komentokehotteessa / Terminaalissa työskennellään aina jossain hakemistossa.
  - Komennolla 'pwd' näytetään kyseinen hakemisto hakemistopolkuineen.
  - Komennolla 'ls' näytetään kyseisen hakemiston sisältämät kansiot(hakemistot) ja tiedostot.
  - Komennolla 'cd *hakemiston-nimi-tähän*/' voidaan siirtyä hakemistossa sijaitsevaan alikansioon.
  - Komennolla 'cd ..' siirrytään hakemistossa ylöspäin
  - Komennolla 'less esimerkki.txt' voidaan tarkastella tekstitiedostoa "less" -tilassa. 'space' näyttää seuraavan sivun, 'b' edellisen sivun ja 'q':lla poistutaan.

- Tiedostojen muokkaus
  - Uuden kansion luominen: 'mkdir *uusi_kansio*'
  - Kansion uudelleen nimeäminen tai siirtäminen tapahtuu komennolla 'mv'. Esimerkiksi 'mv *vanhanimi* *uusinimi*'.
  - Kopioiminen tapahtuu komennolla 'cp'.
  - Kansion poistaminen komennolla 'rmdir', tiedoston poistaminen komennolla 'rm'.

- SSH Remote Control
  - Etähallintakomentorivin voi avata turvallisella tavalla komennolla 'ssh esim@esimerkki.com'.
    - Terminaalissa kirjoittettu tieto lähetetään etäkoneelle, josta vastaus lähetetään takaisin.
    - komennolla 'w' voidaan nähdä koneella työskentelevät muut käyttäjät.
    - komennolla 'exit' poistutaan komentorivistä
    - Esimerkki hakemiston kopioimisesta etäkoneen kansioon: 'scp -r *kansio* esim@esimerkki.com:public_html/'

- Help
  - Komennolla 'man' näytetään manuaalisivu komennolle
    - manuaalisivu näytetään 'less' -tilassa.
  - Useille komennoille saadaan help -listaus (esimerkiksi 'ls --help', 'wget -h')
 
 - History and Guessing
    - Tabulaattoria (Tab) kahdesti painamalla, näytetään mitä voit kirjoittaa seuraavaksi. Esimerkiksi 'cd D' näyttää vaihtoehdot "Desktops", "Documents" ja "Downloads".
    - Tabulaattori täydentää komentoja, jotka eivät ole epäselviä ('cd Docu' > 'cd Documents').
    - Nuolinäppäimillä voidaan selata komento historiaa, nuolinäppäin ylös näyttää edellisen komennon.
    - Kaikkien käytettyjen komentojen historian saa näkyviin komennolla 'history'.

- Tärkeitä kansioita
  - / > Root hakemisto
  - /home/ > sisältää home -hakemistot kaikille käyttäjille.
  - /home/ap/ > kotihakemisto käyttäjälle 'ap'. Ainoa hakemisto, johon käyttäjä 'ap' voi pysyvästi tallentaa dataa.
  - /etc/ > sisältää kaikki järjestelmän laajuiset asetukset.
  - /media/ > irroitettavat tallennusvälineet (esimerkiksi /media/usb/).
  - /var/log/ > sisältää kaikki järjestelmän laajuiset lokitiedostot.
 
- Pakettien hallinta
  - Pakettien hallinta on turvallinen tapa asentaa sovelluksia.
  - sudo apt-get update > päivittää pakettivaraston tiedot järjestelmässä.
    - sudo on lyhenne sanoista 'superuser do' ja tarkoittaa tässä yhteydessä, että komento ajetaan ylläpitäjän (root) oikeuksin.
  - Sovelluksen haku avainsanoilla: apt-cache search *esimerkki*
  - Sovelluksen asennus: sudo apt-get -y install *esimerkki*
    - yhdellä komennolla voidaan asentaa useita sovelluksia. Esim. 'sudo apt-get -y install vlc curl tmux'.
  - Sovelluksen (ja sen järjestelmän laajuiset asetukset) poistaminen: sudo apt-get purge *esimerkki*

# Tehtävä a) Micro

## Asennus
![image](https://github.com/user-attachments/assets/94234498-d7d5-4ef1-b9eb-55f282d9745f)

## Micron käyttö

![image](https://github.com/user-attachments/assets/9926bded-4973-4e45-a6be-d400e484f85a)

![image](https://github.com/user-attachments/assets/81f5d06c-3ace-4982-a732-4ce977d7fc5e)

# Tehtävä b) Apt

### sudo apt-get install cowsay
![image](https://github.com/user-attachments/assets/e8c0b588-97a2-41c2-86cd-fe710f8f0aa7)

### sudo apt-get install sl
![image](https://github.com/user-attachments/assets/7a416a29-98cf-4a56-8def-3cdce8e912de)

### sudo apt-get install figlet
![image](https://github.com/user-attachments/assets/58bc5d3b-ca96-48ef-be7e-865236a20a03)

### Komennolla 'sudo apt-get -y install cowsay sl figlet', voidaan asentaa kaikki ohjelmat kerralla.

# Tehtävä c) FHS

### '/', '/home/', '/home/ap/', '/etc/'
![image](https://github.com/user-attachments/assets/f763a257-16aa-4f13-8462-efde977a847a)

### '/media/', '/var/log/'
![image](https://github.com/user-attachments/assets/86f39f69-52b6-4296-8f97-40becda6ae96)

# Tehtävä d) Grep

- Grep-komento on työkalu, jolla voidaan etsiä tekstiä Terminalista (ilmoitetusta tiedostosta).
- Esimerkiksi: 'grep *haettavateksti* *ilmoitettutiedosto*'

![image](https://github.com/user-attachments/assets/dec743d6-c4db-4b0a-bae7-3cd9f8aeedd3)


# Tehtävä e) Pipe
- 'cat kala.txt' näyttää tiedoston kala.txt sisällön. '|' -operaattori yhdistää komennot.
- 'wc' tulee sanoista "word count" > laskee rivien, sanojen ja tekstin määrän. '-w' tarkentaa, että halutaan ainoastaan sanojen lkm.
![image](https://github.com/user-attachments/assets/a8031174-bbe8-47c2-b564-28e02406b3b3)

# Tehtävä f) Rauta

- H/W path - Laitteiston sijainti
- Device - Laitteen tunniste
- Class - Laitteen tyyppi
- Description - Kuvaus

![image](https://github.com/user-attachments/assets/2fe77ea3-829b-4e09-ac04-ef3f070b2ede)


## Lähteet

Ispmanager.com. 11.7.2024. 8 Fun Linux Utilities. Luettavissa: https://dev.to/ispmanager/8-fun-linux-utilities-48i0. Luettu 26.1.2025.

Karvinen, T. 3.2.2020. Command Line Basics Revisited. Luettavissa: https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited. Luettu 25.1.2025.

Ubunlog. s.a. Grep-komento: tehokas työkalu tekstin etsimiseen Terminalista. Luettavissa: https://fi.ubunlog.com/grep-komento/. Luettu 26.1.2025.






