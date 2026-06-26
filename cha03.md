# Objecttypen

Deze bijlage laat zien welke objecttypen betrokken zijn bij dit onderzoek.
Uitgaande van NEN3610:2022, zie figuur hieronder. De figuur geeft van deze NEN versie aan welke reele en virtuele objecttypen er gedefinieerd zijn.
In het geval van dit onderzoek zal de focus liggen op de <strong>reele</strong> objecttypen, specifiek op die onder hoofdtype <strong>Constructie</strong>. Daaronder vallen de subobjecttypen <strong>Gebouw</strong> en <strong>Kunstwerk</strong>.


<img width="1808" height="1099" alt="image" src="https://github.com/user-attachments/assets/268e76e4-31b3-4f14-94ed-2c7c45d127f0" />


  
Figuur....: overzicht van objecttypen uit NEN3610:2022


In tabelvorm:

<table>
  <caption> Tabel met <strong>reele objecttypen uit NEN3610:22</strong> die betrokken zijn bij dit onderzoek</caption>
  <thead>
    <tr>
      <th> </th>
      <th> </th>
      <th> </th>
      <th> </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Geo­Object</strong></td>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td>Virtuele­Ruimte</td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td><strong>Reeel­Object</strong></td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td>Bodem</td>
      <td> </td>
    </tr>
      <tr>
      <td> </td>
      <td> </td>
      <td>Oppervlaktewater</td>
      <td> </td>
    </tr>
      <tr>
      <td> </td>
      <td> </td>
      <td>Begroeiing</td>
      <td> </td>
    </tr>
      <tr>
      <td> </td>
      <td> </td>
      <td><strong>Constructie</strong></td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
      <td><strong>Gebouw</strong></td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
      <td>Verharding</td>
    </tr>
      <tr>
      <td> </td>
      <td> </td>
      <td> </td>
      <td><strong>Kunstwerk</strong></td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
      <td>Leiding</td>
    </tr>
  </tbody>
</table>




Als we deze objecttypen mappen op het IMBGT dan ontstaat het volgende beeld. Het hoofdobjecttype <strong>Constructie</strong> in NEN:22 komt grotendeels overeen met het abstracte hoofdobjecttype Bouwwerk in BGT. Hieronder vallen ook de kunstwerken zoals tunnels en overbruggingen.

<img width="742" height="504" alt="image" src="https://github.com/user-attachments/assets/bf2cf476-cf83-453c-864d-8a381d2c4218" />


In tabelvorm:

# IMGeo-objecten en geometrie

| Object | BGT-classificatie | Plus-classificatie | Geometrie |
|--------|--------------------|--------------------|-----------|
| Pand | Grondvlaksituatie van BAG-pand | | Multivlak |
| Overig bouwwerk | *type* | | Multivlak |
|  | overkapping | | Multivlak |
|  | open loods | | Vlak |
|  | opslagtank | | Vlak |
|  | bezinkbak | | Vlak |
|  | windturbine | | Vlak |
|  | lage trafo | | Vlak |
|  | bassin | | Vlak |
|  | niet-bgt | bunker | Vlak |
|  | niet-bgt | voedersilo | Vlak |
|  | niet-bgt | schuur | Vlak |
| Overbruggingsdeel | overbruggingIsBeweegbaar: ja/nee | *Hoort bij type overbrugging* | Vlak |
|  |  |brug | Vlak |
|  |  |aquaduct | Vlak |
|  |  | viaduct| Vlak |
|  |  | ecoduct| Vlak |
|  |  |fly-over | Vlak |
|  |  | *Type Overbruggingsdeel* |  |
|  |  | dek | Vlak |
|  |  | landhoofd | Vlak |
|  |  | pijler | Vlak |
|  |  | sloof | Vlak |
|  |  | pyloon | Vlak |
| Tunneldeel | Tunneldeel | | Vlak |
| Kunstwerkdeel | *Type* | |  |
|  | hoogspanningsmast | | Multivlak of Multipunt |
|  | gemaal | | Vlak |
|  | perron | | Vlak |
|  | sluis | | Vlak |
|  | strekdam | | Vlak |
|  | steiger | | Vlak |
|  | stuw | | Lijn of Vlak |
|  | niet-bgt | keermuur | Vlak |
|  | niet-bgt | overkluizing | Vlak |
|  | niet-bgt | duiker | Lijn of Vlak |
|  | niet-bgt | faunavoorziening | Vlak |
|  | niet-bgt | vispassage | Vlak |
|  | niet-bgt | bodemval | Vlak |
|  | niet-bgt | coupure | Vlak |
|  | niet-bgt | ponton | Vlak |
|  | niet-bgt | voorde | Vlak |
| Scheiding | *Type* | |  |
|  | muur | | Lijn of Vlak |
|  | kademuur | | Lijn of Vlak |
|  | damwand | | Lijn |
|  | geluidsscherm | | Lijn |
|  | walbescherming | | Lijn |
|  | hek | | Lijn |
|  | niet-bgt | draadraster | Lijn |
|  | niet-bgt | faunaraster | Lijn |


Figuur...: overzicht van objecttypen uit IMBGT



