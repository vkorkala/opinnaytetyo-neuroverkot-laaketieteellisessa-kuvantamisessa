# Neuroverkot lääketieteellisen kuvantamisen tukena

Opinnäytetyö – Vilja Korkala, 2026

## Yleiskuvaus

Opinnäytetyössä tarkasteltiin neuroverkkojen hyödyntämistä lääketieteellisessä kuvantamisessa sekä niiden käyttöön liittyviä mahdollisuuksia ja rajoitteita.

Työ toteutettiin narratiivisena kirjallisuuskatsauksena, jossa tarkasteltiin neuroverkkojen käyttöä eri kuvantamismodaliteeteissa ja tehtävissä. Erityisesti tarkasteltiin luokittelua, löydösten paikantamista, segmentointia, kuvan rekonstruktiota sekä mallien suorituskyvyn arviointia, validointia ja yleistettävyyttä.

Kirjallisuuskatsausta täydentämään toteutettiin rajattu kokeellinen esimerkki rintakehän röntgenkuvien (CXR) luokittelusta.

## Tutkimuskysymykset

1. Millaisissa kuvantamistehtävissä neuroverkkoja hyödynnetään tällä hetkellä?
2. Mitkä tekijät rajoittavat niiden yleistettävyyttä kliinisessä ympäristössä?
3. Millaisiin käyttötarkoituksiin neuroverkot soveltuvat nykyisellään parhaiten radiologin työn tueksi?

## Kokeellinen esimerkki

Kokeellisessa osuudessa käytettiin Kaggle-palvelussa julkaistua
**Chest X-Ray Images (Pneumonia)** -aineistoa.

Aineistossa kuvat jakautuvat kahteen luokkaan:

- `NORMAL`
- `PNEUMONIA`

Koulutusjoukosta muodostettiin rajattu ja luokittain tasapainotettu otos, jossa käytettiin enintään 1000 kuvaa kumpaakin luokkaa kohden. Validointi- ja testijoukot käytettiin alkuperäisessä muodossaan.

Mallina käytettiin ImageNet-aineistolla valmiiksi opetettua **ResNet18-konvoluutioneuroverkkoa**, jota hienosäädettiin binääriluokitukseen.

Kokeellinen osuus toteutettiin Google Colab -ympäristössä.

## Teknologiat

- Python
- PyTorch
- torchvision
- timm
- scikit-learn
- matplotlib
- Google Colab

## Arviointi

Mallin suorituskykyä arvioitiin seuraavilla mittareilla:

- AUC
- sensitiivisyys
- spesifisyys
- ROC-käyrä
- sekaannusmatriisi

Luokittelukynnyksenä käytettiin arvoa 0,5.

## Tulokset

Yhdessä edustavassa testiajossa hienosäädetty ResNet18 saavutti seuraavat tulokset:

| Mittari | Tulos |
|---|---:|
| AUC | 0,96 |
| Sensitiivisyys | 0,97 |
| Spesifisyys | 0,75 |

Tulokset osoittivat hyvää erotuskykyä, mutta samalla spesifisyys jäi selvästi sensitiivisyyttä matalammaksi. Työssä korostettiin, että kokeellinen osuus oli rajattu ja havainnollistava, eikä tuloksia voida yleistää kliiniseen käyttöön.

## Keskeiset havainnot

Kirjallisuuskatsauksen perusteella neuroverkkojen käyttö lääketieteellisessä kuvantamisessa painottuu erityisesti rajattuihin tehtäviin, kuten:

- kuvien luokitteluun
- löydösten paikantamiseen
- segmentointiin
- kuvan rekonstruktioon ja laadun parantamiseen

Keskeisiä kliinisen käytön haasteita ovat muun muassa aineiston laatu, validointi, mallien yleistettävyys sekä erilaisiin aineistoihin ja käyttöympäristöihin liittyvät vinoumat.

Työn perusteella neuroverkkoja voidaan hyödyntää erityisesti rajatuissa radiologian tehtävissä, joissa niiden tuottama tieto voi tukea ammattilaisen työtä. Luotettava kliininen käyttö edellyttää kuitenkin huolellista validointia, edustavia aineistoja ja tarkoituksenmukaista integrointia kliiniseen työnkulkuun.

## Mitä projektissa opin

Opinnäytetyön aikana perehdyin neuroverkkojen käyttöön lääketieteellisessä kuvantamisessa sekä koneoppimismallien suorituskyvyn arviointiin.

Käytännön toteutuksessa sain kokemusta muun muassa:

- kuvadatan käsittelystä ja esikäsittelystä
- siirto-oppimiseen perustuvasta mallin hienosäädöstä
- neuroverkon kouluttamisesta PyTorchilla
- mallin suorituskyvyn arvioinnista
- tulosten visualisoinnista ja tulkinnasta
- koneoppimiskokeen rajoitteiden arvioinnista

## Työn rajoitteet

Kokeellinen osuus oli pieni ja havainnollistava. Mallia arvioitiin yhden aineiston testijoukolla, eikä ulkoista validointia tehty. Lisäksi validointijoukko oli hyvin pieni, ja kokeeseen liittyi satunnaisuutta esimerkiksi koulutusdatan otannassa ja augmentoinnissa.

Näiden rajoitteiden vuoksi yksittäisiä tuloksia ei tule pitää osoituksena kliinisestä suorituskyvystä.

## Tekoälyn käyttö työssä

Opinnäytetyössä hyödynnettiin tekoälyä rajatusti työn tukena. ChatGPT:tä käytettiin muun muassa aiheen ja rakenteen ideointiin, tekstin jäsentelyyn ja kielenhuoltoon. Microsoft Copilotia hyödynnettiin kokeellisen osuuden ohjelmointityössä virheiden paikantamiseen ja virheenkorjaukseen.

Vastuu työn sisällöstä ja sen paikkansapitävyydestä oli tekijällä.

## Huomio

Koko opinnäytetyö ei ole julkisesti saatavilla.

Tämä repository sisältää opinnäytetyön tiivistetyn esittelyn sekä kokeellisen osuuden teknisiä tietoja.
