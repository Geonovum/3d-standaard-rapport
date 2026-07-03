# Objecttypen

Onderzoeksvraag: *Voor welke soorten objecten en daarmee samenhangende datasets zou deze standaard moeten gelden?*

We kijken naar twee use cases die vooral focussen op de SOLL situatie en antwoord geven op de vraag wat is er nodig aan standaarden om naar die SOLL situatie te komen.

De use cases zijn:

- DTaaS: Digital Twin as a Service. In DTaaS komen diverse use cases aan de orde zoals hittestress en overstroming van steden, waarbij een 3D stadsmodel nodig is om simulaties te kunnen doen. DTaaS maakt gebruik van 3D geo-objecten maar schrijft geen standaard voor. Voor een vergroot gebruik van Digital Twins is een 3D standaard aan te bevelen. Door Digital Twin als usecase te gebruiken versterken we ook de relatie tussen het ZoN Datafundament en het ZoN Digital Twin programma.
- Informatiemodel Geluid. Geluid is bij uitstek een fenomeen dat beïnvloed wordt door de 3D ruimte en men heeft 3D objecten nodig om binnen de geluidsmodellen te kunnen bepalen welk geluid hoe hard ergens aankomt, gegeven de locatie van de geluidsbron en de fysieke objecten die het geluid onderweg tegenkomt.


De NEN 3610 is een top-ontologie waarin verschillende ruimtelijke en reeele concepten samenkomen tot één gedeeld model van de fysieke leefomgeving. Onderstaand figuur toont de nen3610:2022. De figuur toont van deze NEN versie welke objecttypen er gedefinieerd zijn.
In het geval van dit onderzoek zal de focus liggen op zowel alle objecten onder reelobject als een aantal ruimtes onder virtuele ruimte. Dit zijn o.a. de ruimten die in de BGT (Functioneel gebied en Registratief gebied) en BAG (Juridische Ruimte) voorkomen.  

<figure>
<img width="600" alt="image" src="https://github.com/user-attachments/assets/268e76e4-31b3-4f14-94ed-2c7c45d127f0" />
    <figcaption>overzicht van objecttypen uit NEN3610:2022</figcaption>
</figure>



Als we deze objecttypen mappen op het IMBGT dan ontstaat het volgende beeld. Het hoofdobjecttype <strong>Constructie</strong> in NEN:22 komt grotendeels overeen met het abstracte hoofdobjecttype Bouwwerk in BGT. Hieronder vallen ook de kunstwerken zoals tunnels en overbruggingen.

<figure>
<img width="742" height="504" alt="image" src="https://github.com/user-attachments/assets/bf2cf476-cf83-453c-864d-8a381d2c4218" />
 <figcaption>overzicht van objecttypen uit IMBGT met NEN3610 klasses</figcaption>
</figure>

# IMGeo-objecten en geometrie
De BGT objecten zijn zoals beschreven in paragraaf 2.6 van de <mark>BGT Specificatie</mark> specifiek tweedimensionaal. Wel wordt de stap naar 3D al beschreven. Deze stap wordt verder toegelicht in pargaraf 2.5 van de <mark>IMGEO specificatie</mark>


| *Object*                                                    | *BGT classificatie*            | *Plus classificatie*                       | *Geometrie*            |*Ruimte*        |
|-------------------------------------------------------------|--------------------------------|--------------------------------------------|------------------------|----------------|
| *Transport*                                                 |                                |                                            |                        | 2D             |
| **Wegdeel** kruinlijn: lijn op talud: ja/nee                | *Functie:*                     |                                            |                        | 2D             |
|                                                             | OV-baan                        |                                            | 2D Vlak                   | 2D             |
|                                                             | overweg                        |                                            | 2D Vlak                   | 2D             |
|                                                             | spoorbaan                      |                                            | 2D Vlak                   | 2D             |
|                                                             | baan voor vliegverkeer         |                                            | 2D Vlak                   | 2D             |
|                                                             | rijbaan autosnelweg            | verbindingsweg                             | 2D Vlak                   | 2D             |
|                                                             |                                | calamiteitendoorsteek                      | 2D Vlak                   | 2D             |
|                                                             | rijbaan autoweg                | verbindingsweg                             | 2D Vlak                   | 2D             |
|                                                             |                                | calamiteitendoorsteek                      | 2D Vlak                   | 2D             |
|                                                             | rijbaan regionale weg          | verbindingsweg                             | 2D Vlak                   | 2D             |
|                                                             |                                | verkeersdrempel                            | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
|                                                             | rijbaan lokale weg             | verkeersdrempel                            | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        | 2D             |
|                                                             | fietspad                       |                                            | 2D Vlak                   | 2D             |
|                                                             | voetpad                        |                                            | 2D Vlak                   | 2D             |
|                                                             | voetpad op trap                |                                            | 2D Vlak                   | 2D             |
|                                                             | ruiterpad                      |                                            | 2D Vlak                   | 2D             |
|                                                             | parkeervlak                    |                                            | 2D Vlak                   | 2D             |
|                                                             | voetgangersgebied              |                                            | 2D Vlak                   | 2D             |
|                                                             | inrit                          |                                            | 2D Vlak                   | 2D             |
|                                                             | woonerf                        |                                            | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
|                                                             | *Fysiek voorkomen:*            |                                            |                        |              |
|                                                             | gesloten verharding            | asfalt                                     | 2D Vlak                   | 2D             |
|                                                             |                                | cementbeton                                | 2D Vlak                   | 2D             |
|                                                             | open verharding                | betonstraatstenen                          | 2D Vlak                   | 2D             |
|                                                             |                                | gebakken klinkers                          | 2D Vlak                   | 2D             |
|                                                             |                                | tegels                                     | 2D Vlak                   | 2D             |
|                                                             |                                | sierbestrating                             | 2D Vlak                   | 2D             |
|                                                             |                                | beton element                              | 2D Vlak                   | 2D             |
|                                                             | half verhard                   | grasklinkers                               | 2D Vlak                   | 2D             |
|                                                             |                                | schelpen                                   | 2D Vlak                   | 2D             |
|                                                             |                                | puin                                       | 2D Vlak                   | 2D             |
|                                                             |                                | grind                                      | 2D Vlak                   | 2D             |
|                                                             |                                | gravel                                     | 2D Vlak                   | 2D             |
|                                                             | onverhard                      | boomschors                                 | 2D Vlak                   | 2D             |
|                                                             |                                | zand                                       | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Ondersteunend wegdeel** kruinlijn: lijn op talud: ja/nee  | *Functie:*                     |                                            |                        |              |
|                                                             | verkeerseiland                 |                                            | 2D Vlak                   | 2D             |
|                                                             | berm                           |                                            | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
|                                                             | *Fysiek voorkomen:*            |                                            |                        |              |
|                                                             | gesloten verharding            | asfalt                                     | 2D Vlak                   | 2D             |
|                                                             |                                | cementbeton                                | 2D Vlak                   | 2D             |
|                                                             | open verharding                | betonstraatstenen                          | 2D Vlak                   | 2D             |
|                                                             |                                | gebakken klinkers                          | 2D Vlak                   | 2D             |
|                                                             |                                | tegels                                     | 2D Vlak                   | 2D             |
|                                                             |                                | sierbestrating                             | 2D Vlak                   | 2D             |
|                                                             |                                | beton element                              | 2D Vlak                   | 2D             |
|                                                             | half verhard                   | grasklinkers                               | 2D Vlak                   | 2D             |
|                                                             |                                | schelpen                                   | 2D Vlak                   | 2D             |
|                                                             |                                | puin                                       | 2D Vlak                   | 2D             |
|                                                             |                                | grind                                      | 2D Vlak                   | 2D             |
|                                                             |                                | gravel                                     | 2D Vlak                   | 2D             |
|                                                             | onverhard                      | boomschors                                 | 2D Vlak                   | 2D             |
|                                                             |                                | zand                                       | 2D Vlak                   | 2D             |
|                                                             | groenvoorziening               | bosplantsoen                               | 2D Vlak                   | 2D             |
|                                                             |                                | gras- en kruidachtigen                     | 2D Vlak                   | 2D             |
|                                                             |                                | planten                                    | 2D Vlak                   | 2D             |
|                                                             |                                | struikrozen                                | 2D Vlak                   | 2D             |
|                                                             |                                | heesters                                   | 2D Vlak                   | 2D             |
|                                                             |                                | bodembedekkers                             | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Spoor**                                                   | *Functie:*                     |                                            |                        |              |
|                                                             | trein                          |                                            | 1D Lijn                   | 2D             |
|                                                             | sneltram                       |                                            | 1D Lijn                   | 2D             |
|                                                             | tram                           |                                            | 1D Lijn                   | 2D             |
|                                                             | niet-bgt                       | (haven)kraan                               | 1D Lijn                   | 2D             |
|                                                             |                                |                                            |                        |             |
| *Terrein*                                                   |                                |                                            |                        |              |
| **Onbegroeid terreindeel** kruinlijn: lijn op talud: ja/nee | *Fysiek voorkomen:*            |                                            |                        |              |
|                                                             | erf                            |                                            | 2D Vlak                   | 2D             |
|                                                             | gesloten verharding            | asfalt                                     | 2D Vlak                   | 2D             |
|                                                             |                                | cementbeton                                | 2D Vlak                   | 2D             |
|                                                             |                                | kunststof                                  | 2D Vlak                   | 2D             |
|                                                             | open verharding                | betonstraatstenen                          | 2D Vlak                   | 2D             |
|                                                             |                                | gebakken klinkers                          | 2D Vlak                   | 2D             |
|                                                             |                                | tegels                                     | 2D Vlak                   | 2D             |
|                                                             |                                | sierbestrating                             | 2D Vlak                   | 2D             |
|                                                             |                                | beton element                              | 2D Vlak                   | 2D             |
|                                                             | half verhard                   | grasklinkers                               | 2D Vlak                   | 2D             |
|                                                             |                                | schelpen                                   | 2D Vlak                   | 2D             |
|                                                             |                                | puin                                       | 2D Vlak                   | 2D             |
|                                                             |                                | grind                                      | 2D Vlak                   | 2D             |
|                                                             |                                | gravel                                     | 2D Vlak                   | 2D             |
|                                                             | onverhard                      | boomschors                                 | 2D Vlak                   | 2D             |
|                                                             |                                | zand                                       | 2D Vlak                   | 2D             |
|                                                             | zand                           | strand en strandwal                        | 2D Vlak                   | 2D             |
|                                                             |                                | zandverstuiving                            | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Begroeid terreindeel** kruinlijn: lijn op talud: ja/nee   | *Fysiek voorkomen:*            |                                            |                        |              |
|                                                             | loofbos                        | griend en hakhout                          | 2D Vlak                   | 2D             |
|                                                             | gemengd bos                    |                                            | 2D Vlak                   | 2D             |
|                                                             | naaldbos                       |                                            | 2D Vlak                   | 2D             |
|                                                             | heide                          |                                            | 2D Vlak                   | 2D             |
|                                                             | struiken                       |                                            | 2D Vlak                   | 2D             |
|                                                             | houtwal                        |                                            | 2D Vlak                   | 2D             |
|                                                             | duin                           | open duinvegetatie                         | 2D Vlak                   | 2D             |
|                                                             |                                | gesloten duinvegetatie                     | 2D Vlak                   | 2D             |
|                                                             | grasland overig                |                                            | 2D Vlak                   | 2D             |
|                                                             | moeras                         |                                            | 2D Vlak                   | 2D             |
|                                                             | rietland                       |                                            | 2D Vlak                   | 2D             |
|                                                             | kwelder                        |                                            | 2D Vlak                   | 2D             |
|                                                             | fruitteelt                     | laagstam boomgaarden                       | 2D Vlak                   | 2D             |
|                                                             |                                | hoogstam boomgaarden                       | 2D Vlak                   | 2D             |
|                                                             |                                | wijngaarden                                | 2D Vlak                   | 2D             |
|                                                             |                                | klein fruit                                | 2D Vlak                   | 2D             |
|                                                             | boomteelt                      |                                            | 2D Vlak                   | 2D             |
|                                                             | bouwland                       | akkerbouw                                  | 2D Vlak                   | 2D             |
|                                                             |                                | braakliggend                               | 2D Vlak                   | 2D             |
|                                                             |                                | vollegrondsteelt                           | 2D Vlak                   | 2D             |
|                                                             |                                | bollenteelt                                | 2D Vlak                   | 2D             |
|                                                             | grasland agrarisch             |                                            | 2D Vlak                   | 2D             |
|                                                             | groenvoorziening               | bosplantsoen                               | 2D Vlak                   | 2D             |
|                                                             |                                | gras- en kruidachtigen                     | 2D Vlak                   | 2D             |
|                                                             |                                | planten                                    | 2D Vlak                   | 2D             |
|                                                             |                                | struikrozen                                | 2D Vlak                   | 2D             |
|                                                             |                                | heesters                                   | 2D Vlak                   | 2D             |
|                                                             |                                | bodembedekkers                             | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |             |
| *Water*                                                     |                                |                                            |                        |              |
| **Waterdeel**                                               | *Type:*                        |                                            |                        |             |
|                                                             | zee                            |                                            | 2D Vlak                   | 2D             |
|                                                             | waterloop                      | rivier                                     | 2D Vlak                   | 2D             |
|                                                             |                                | sloot                                      | 2D Vlak                   | 2D             |
|                                                             |                                | kanaal                                     | 2D Vlak                   | 2D             |
|                                                             |                                | beek                                       | 2D Vlak                   | 2D             |
|                                                             |                                | gracht                                     | 2D Vlak                   | 2D             |
|                                                             |                                | bron                                       | 2D Vlak                   | 2D             |
|                                                             | watervlakte                    | haven                                      | 2D Vlak                   | 2D             |
|                                                             |                                | meer, plas, ven, vijver                    | 2D Vlak                   | 2D             |
|                                                             | greppel, droge sloot           |                                            | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Ondersteunend waterdeel**                                 | oever, slootkant               |                                            | 2D Vlak                   | 2D             |
|                                                             | slik                           |                                            | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
| *Bouwwerk*                                                  |                                |                                            |                        |              |
| **Pand**                                                    | Grondvlaksituatie van BAG-pand |                                            | 2D Multivlak              | 2D             |
|                                                             |                                |                                            |                        |              |
| **Overig bouwwerk**                                         | *Type:*                        |                                            |                        |              |
|                                                             | overkapping                    |                                            | 2D Multivlak              | 2D             |
|                                                             | open loods                     |                                            | 2D Vlak                   | 2D             |
|                                                             | opslagtank                     |                                            | 2D Vlak                   | 2D             |
|                                                             | bezinkbak                      |                                            | 2D Vlak                   | 2D             |
|                                                             | windturbine                    |                                            | 2D Vlak                   | 2D             |
|                                                             | lage trafo                     |                                            | 2D Vlak                   | 2D             |
|                                                             | bassin                         |                                            | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | bunker                                     | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | voedersilo                                 | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | schuur                                     | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Kunstwerk**                                               |                                |                                            |                        |              |
| **Overbruggingsdeel** overbruggingIsBeweegbaar: ja/nee      |                                | *Hoort bij type overbrugging:*             | 2D Vlak \*                | 2D             |
|                                                             |                                | brug                                       | 2D Vlak                   | 2D             |
|                                                             |                                | aquaduct                                   | 2D Vlak                   | 2D             |
|                                                             |                                | viaduct                                    | 2D Vlak                   | 2D             |
|                                                             |                                | ecoduct                                    | 2D Vlak                   | 2D             |
|                                                             |                                | fly-over                                   | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |             |
|                                                             |                                | *Type Overbruggingsdeel:*                  |                        |             |
|                                                             |                                | dek                                        | 2D Vlak                   | 2D             |
|                                                             |                                | landhoofd                                  | 2D Vlak                   | 2D             |
|                                                             |                                | pijler                                     | 2D Vlak                   | 2D             |
|                                                             |                                | sloof                                      | 2D Vlak                   | 2D             |
|                                                             |                                | pyloon                                     | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Tunneldeel**                                              | Tunneldeel                     |                                            | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Kunstwerkdeel**                                           | *Type:*                        |                                            |                        |              |
|                                                             | hoogspanningsmast              |                                            | 2D Multivlak of 0D Multipunt | 2D             |
|                                                             | gemaal                         |                                            | 2D Vlak                   | 2D             |
|                                                             | perron                         |                                            | 2D Vlak                   | 2D             |
|                                                             | sluis                          |                                            | 2D Vlak                   | 2D             |
|                                                             | strekdam                       |                                            | 2D Vlak                   | 2D             |
|                                                             | steiger                        |                                            | 2D Vlak                   | 2D             |
|                                                             | stuw                           |                                            | 1D Lijn of 2D Vlak           | 2D             |
|                                                             | niet-bgt                       | keermuur                                   | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | overkluizing                               | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | duiker                                     | 1D Lijn of 2D Vlak           | 2D             |
|                                                             | niet-bgt                       | faunavoorziening                           | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | vispassage                                 | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | bodemval                                   | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | coupure                                    | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | ponton                                     | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | voorde                                     | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Scheiding**                                               | *Type:*                        |                                            |                        |              |
|                                                             | muur                           |                                            | 1D Lijn of 2D Vlak           | 2D             |
|                                                             | Kademuur                       |                                            | 1D Lijn of 2D Vlak           | 2D             |
|                                                             | damwand                        |                                            | 1D Lijn                   | 2D             |
|                                                             | geluidsscherm                  |                                            | 1D Lijn                   | 2D             |
|                                                             | walbescherming                 |                                            | 1D Lijn                   | 2D             |
|                                                             | hek                            |                                            | 1D Lijn                   | 2D             |
|                                                             | niet-bgt                       | draadraster                                | 1D Lijn                   | 2D             |
|                                                             | niet-bgt                       | faunaraster                                | 1D Lijn                   | 2D             |
|                                                             |                                |                                            |                        |             |
| **Functioneel Gebied**                                      | *Type:*                        |                                            |                        |              |
|                                                             | kering                         |                                            | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | bedrijvigheid                              | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | natuur en landschap                        | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | landbouw                                   | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | bewoning                                   | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | infrastructuur verkeer en vervoer          | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | infrastructuur waterstaatswerken           | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | waterbergingsgebied                        | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | maatschappelijke en/of publieksvoorziening | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | recreatie                                  | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | begraafplaats                              | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | functioneel beheer                         | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | functioneel beheer: hondenuitlaatplaats    | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | recreatie: speeltuin                       | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | recreatie: park                            | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | recreatie: sportterrein                    | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | recreatie: camping                         | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | recreatie: bungalowpark                    | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | recreatie: volkstuin                       | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | bushalte                                   | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | carpoolplaats                              | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | benzinestation                             | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | verzorgingsplaats                          | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Overige Scheiding**                                       | niet-bgt                       | Type zoals Scheiding                       | 1D Lijn of 2D Vlak           | 2D             |
|                                                             |                                |                                            |                        |              |
| **Bak**                                                     |                                | *Type:*                                    |                        |              |
|                                                             | niet-bgt                       | afval apart plaats                         | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | afvalbak                                   | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | drinkbak                                   | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | bloembak                                   | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | zand- / zoutbak                            | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | container                                  | 0D Punt                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Bord**                                                    |                                | *Type:*                                    |                        |             |
|                                                             | niet-bgt                       | informatiebord                             | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | plaatsnaambord                             | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | straatnaambord                             | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | verkeersbord                               | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | scheepvaartbord                            | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | verklikker transportleiding                | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | reclamebord                                | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | wegwijzer                                  | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | waarschuwingshek                           | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | dynamische snelheidsindicator              | 0D Punt                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Gebouwinstallatie**                                       |                                | *Type:*                                    |                        |             |
|                                                             | niet-bgt                       | bordes                                     | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | luifel                                     | 2D Vlak                   | 2D             |
|                                                             | niet-bgt                       | toegangstrap                               | 2D Vlak                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Installatie**                                             |                                | *Type:*                                    |                        |              |
|                                                             | niet-bgt                       | pomp                                       | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | zonnepaneel                                | 0D Punt                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Kast**                                                    |                                | *Type:*                                    |                        |             |
|                                                             | niet-bgt                       | CAI-kast                                   | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | elektrakast                                | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | gaskast                                    | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | telecom kast                               | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | rioolkast                                  | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | openbare verlichtingkast                   | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | Verkeersregelinstal-latiekast              | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | telkast                                    | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | GMS kast                                   | 0D Punt                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Mast**                                                    |                                | *Type:*                                    |                        |              |
|                                                             | niet-bgt                       | bovenleidingmast                           | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | laagspanningsmast                          | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | straalzender                               | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | zendmast                                   | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | radarmast                                  | 0D Punt                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Paal**                                                    |                                | *Type:*                                    |                        |              |
|                                                             | niet-bgt                       | lichtmast                                  | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | telpaal                                    | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | portaal                                    | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | verkeersregelinstallatiepaal               | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | verkeersbordpaal                           | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | poller                                     | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | haltepaal                                  | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | vlaggenmast                                | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | afsluitpaal                                | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | praatpaal                                  | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | hectometerpaal                             | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | dijkpaal                                   | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | drukknoppaal                               | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | grensmarkering                             | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | sirene                                     | 0D Punt                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Put**                                                     |                                | *Type:*                                    |                        |              |
|                                                             | niet-bgt                       | benzine- / olieput                         | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | brandkraan / -put                          | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | drainageput                                | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | gasput                                     | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | inspectie- / rioolput                      | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | kolk                                       | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | waterleidingput                            | 0D Punt                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Sensor**                                                  |                                | *Type:*                                    |                        |              |
|                                                             | niet-bgt                       | camera                                     | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | debietmeter                                | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | hoogtedetectieapparaat                     | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | detectielus                                | 1D Lijn                   | 2D             |
|                                                             | niet-bgt                       | weerstation                                | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | flitser                                    | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | waterstandmeter                            | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | windmeter                                  | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | lichtcel                                   | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | GMS sensor                                 | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | radar detector                             | 0D Punt                   | 2D             |
|                                                             |                                |                                            |                        |             |
| **Straatmeubilair**                                         |                                | *Type:*                                    |                        |              |
|                                                             | niet-bgt                       | abri                                       | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | bolder                                     | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | brievenbus                                 | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | fietsenrek                                 | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | kunstobject                                | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | openbaar toilet                            | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | slagboom                                   | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | speelvoorziening                           | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | telefooncel                                | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | bank                                       | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | picknicktafel                              | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | fontein                                    | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | lichtpunt                                  | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | parkeerbeugel                              | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | betaalautomaat                             | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | reclamezuil                                | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | fietsenkluis                               | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | herdenkingsmonument                        | 0D Punt                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Waterinrichtings-element**                                |                                | *Type:*                                    |                        |              |
|                                                             | niet-bgt                       | remmingswerk                               | 1D Lijn                   | 2D             |
|                                                             | niet-bgt                       | betonning                                  | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | geleidewerk                                | 1D Lijn                   | 2D             |
|                                                             | niet-bgt                       | vuilvang                                   | 1D Lijn                   | 2D             |
|                                                             | niet-bgt                       | meerpaal                                   | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | hoogtemerk                                 | 0D Punt                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Weginrichtings-element**                                  |                                | *Type:*                                    |                        |             |
|                                                             | niet-bgt                       | molgoot                                    | 1D Lijn                   | 2D             |
|                                                             | niet-bgt                       | lijnafwatering                             | 1D Lijn                   | 2D             |
|                                                             | niet-bgt                       | wegmarkering                               | 0D Punt, 1D Lijn of 2D Vlak     | 2D             |
|                                                             | niet-bgt                       | wildrooster                                | 0D Punt, 1D Lijn of 2D Vlak     | 2D             |
|                                                             | niet-bgt                       | rooster                                    | 0D Punt, 1D Lijn of 2D Vlak     | 2D             |
|                                                             | niet-bgt                       | geleideconstructie                         | 0D Punt, 1D Lijn of 2D Vlak     | 2D             |
|                                                             | niet-bgt                       | balustrade                                 | 1D Lijn                   | 2D             |
|                                                             | niet-bgt                       | boomspiegel                                | 0D Punt of 2D Vlak           | 2D             |
|                                                             | niet-bgt                       | verblindingswering                         | 1D Lijn                   | 2D             |
|                                                             |                                |                                            |                        |              |
| **Vegetatieobject**                                         |                                | *Type:*                                    |                        |              |
|                                                             | niet-bgt                       | boom                                       | 0D Punt                   | 2D             |
|                                                             | niet-bgt                       | haag                                       | 1D Lijn of 2D Vlak           | 2D             |
|                                                             |                                |                                            |                        |              |
| **RegistratiefGebied**                                      |                                |                                            |                        |              |
| **Buurt**                                                   | niet-bgt                       |                                            | 2D Multivlak              | 2D             |
| **OpenbareRuimte**                                          | niet-bgt                       |                                            | 2D Multivlak              | 2D             |
| **Stadsdeel**                                               | niet-bgt                       |                                            | 2D Multivlak              | 2D             |
| **Waterschap**                                              | niet-bgt                       |                                            | 2D Multivlak              | 2D             |
| **Wijk**                                                    | niet-bgt                       |                                            | 2D Multivlak              |2D             |


Moenteel bevinden alle BGT objecten zich in een 2D ruimte. In een 3D standaard voor bovenstaande objecten wordt de ruimte waarin deze objecten zich bevinden 3D. De geometrie van deze objecten kan daarmee toenemen in dimensie, maar dit is niet altijd noodzakelijk of wenselijk. Wellicht is een 2D vlakgeometrie (LOD 0) voor onbegroeide terreindelen in 3D voldoende. Dit is onderwerp voor vervolgonderzoek.

![alt text](./media/image.png)

Vegetation LOD definitions by Ortega-Córdova [p. 29 in Ortega-Córdova (2018)] (CC-BY license; some images are based on ESRI library models) and by Zhang et al. (p. 204 in Zhang et al. (2022))!

![alt text](./media/image-1.png)
<mark>Urban Vegetation Modeling 3D Levels of Detail</mark>

 Het gebruik van dezelfde 3D-representatie binnen de basisregistraties zorgt ervoor dat men egevens onderling kan vergelijken en combineren. Het bevordert de interoperabiliteit en voorkomt verschillen in interpretatie van geometrieën. 
 
<aside class="note" title="Ontwikkel een 3D representatiestandaard">
  <p><strong>AANBEVELING:</strong> OOntwikkel een 3D-representatiestandaard die aansluit bij nu al aanwezige 2D-representatie van de basisregistraties. Door een gezamenlijke standaard te hanteren, kunnen 3D-gegevens in de toekomst eenvoudiger worden gecombineerd, vergeleken en uitgewisseld. Dit bevordert de interoperabiliteit tussen datasets en voorkomt verschillen in de interpretatie en modellering van objecten.</p>
</aside>
