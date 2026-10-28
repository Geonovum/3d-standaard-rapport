# 3D-visualisatiestandaard

## Aanleiding en doel

Voor het gestandaardiseerd ontsluiten en visualiseren van 3D-data op het web zijn twee goedgekeurde internationale standaarden beschikbaar: **3D Tiles** en **i3S**. Beide standaarden maken het mogelijk om 3D-data efficiënt te streamen en te visualiseren in onder meer 3D-viewers en digitale tweelingen.

Om te voorkomen dat landelijke, regionale en lokale 3D-voorzieningen zich ontwikkelen tot afzonderlijke, onvoldoende interoperabele oplossingen, is onderzocht welke van deze standaarden in Nederland de voorkeur verdient. Daarbij zijn de beschikbare implementaties, voor- en nadelen, functionele mogelijkheden, ondersteunde datatypen en de gevolgen van de keuze beoordeeld.

Het uitgangspunt is interoperabiliteit van landelijke 3D-bestanden, zodat 3D-viewers en digitale tweelingen op gestandaardiseerde wijze uit dezelfde bron kunnen putten.

## Afweging tussen 3D Tiles en i3S

Uit de inventarisatie en de beoordeling van de twee standaarden blijkt dat **3D Tiles beter scoort op de niet-functionele criteria**. De standaard wordt breed toegepast, kent een ruim aanbod aan software-implementaties en libraries en wordt ondersteund door verschillende open-sourceprojecten. Dit draagt bij aan interoperabiliteit en beperkt de afhankelijkheid van één softwareleverancier.

i3S biedt eveneens uitgebreide mogelijkheden en wordt met name gebruikt binnen het Esri-ecosysteem. De standaard kent onder meer mogelijkheden voor building layers en bepaalde datatypen. Daar staat tegenover dat i3S minder breed wordt toegepast buiten ArcGIS, dat minder libraries beschikbaar zijn en dat de interoperabiliteit beperkter is.

Bij de functionele criteria en de ondersteunde soorten data zijn de verschillen tussen beide standaarden kleiner. Beide ondersteunen onder meer puntenwolken, verschillende detailniveaus en de visualisatie van 3D-modellen. Ook voor lokale coördinaatreferentiesystemen, ondergrondvisualisatie en semantische informatie is geen overtuigend onderscheid gevonden dat een uitzondering op de keuze voor 3D Tiles rechtvaardigt.

Voor de visualisatie van gestructureerde BIM-/gebouwmodellen bestaat nog enige nuance. i3S kent hiervoor het concept *Building Scene Layers*. Ook 3D Tiles kan worden ingezet voor de visualisatie van BIM-modellen, als generiek 3D-streamingformaat waarbij BIM-semantiek in metadata-extensies kan worden opgenomen. In de praktijk zijn beide standaarden afhankelijk van conversie vanuit BIM-formaten zoals IFC. Daarbij kan vereenvoudiging van geometrie nodig zijn. Er is geen breed gedragen onderbouwing gevonden om hiervoor een uitzondering op de keuze voor 3D Tiles op te nemen.

## Impact van de keuze

3D Tiles wordt al op grotere schaal toegepast voor de publicatie van 3D-data binnen de publieke sector. Voorbeelden zijn de 3D Basisvoorziening van het Kadaster, de 3D BAG en verschillende regionale en lokale 3D-voorzieningen. Ook voor BRO-data is begonnen met publicatie in 3D Tiles.

Een keuze voor i3S zou betekenen dat bestaande voorzieningen en publicaties naar deze standaard zouden moeten overstappen. De verwachte impact daarvan is groter dan bij de keuze voor 3D Tiles.

Het toestaan van beide standaarden kan bovendien betekenen dat aanbieders datasets in twee formaten moeten opslaan en beschikbaar stellen, wat extra kosten met zich meebrengt.

Een aandachtspunt bij 3D Tiles is dat de standaard ruimte laat voor verschillende interpretaties en veel vrijheidsgraden kent. Daardoor werkt een toepassing niet altijd in iedere client op dezelfde manier. Er is daarom behoefte aan richtlijnen voor de inrichting van tilesets, onder meer voor de toepassing van detailniveaus (*Levels of Detail*, LOD's). Een Nederlands profiel kan hierbij ondersteuning bieden. Geonovum heeft hiervoor al een handreiking, waaruit geput kan worden voor een Nederlands profiel.

## Aanbeveling

Op basis van de inventarisatie, de vergelijking van beide standaarden en de reviewronde wordt aanbevolen om 3D Tiles als Nederlandse standaard voor het streamen en visualiseren van 3D-data op het web te hanteren. Er is onvoldoende aanleiding om specifieke functionele uitzonderingen voor i3S op te nemen.

De aanbevolen afspraak luidt:

De standaard in Nederland voor het streamen en visualiseren van 3D data op het web is 3D Tiles. Omdat de 3D visualisatie standaarden nog significant worden doorontwikkeld, wordt deze afspraak elk jaar herijkt.

De conclusies zijn gebaseerd op de stand van zaken in juli 2026. Omdat zowel de standaarden als de bijbehorende software-implementaties zich in hoog tempo ontwikkelen, is periodieke herbeoordeling noodzakelijk.

## Details

Voor verdere details en een uitwerking van de 3D visualisatie sessie, zie [3D visualisatie standaard compleet overzicht](./3dvis/3D-visualisatie-standaard-compleet-verslag.pdf).
