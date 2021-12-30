# Marine research (Marin forskning)

String for use in Tableau against FOR_data_sted_total

The string is set up so that one can either get results for **all marine research**, or a subset covering **maritime research**. 
Unlike the other satsningsområder, these two are not two independent parts - the maritime string finds a SUBSET of the marine string results. 
Thus to get only the marine research which is not maritime, one must minus the maritime subset and look at what remains. 
This maritime subset is an *estimate* only - splitting off this research using a string is difficult.

*NOTE 1: A number of terms are included twice in different parts of the string - once for article title, and another time for book title - remember to edit both if making changes. NOTE 2: The string for marine should also contain all terms for maritime - don't add to maritime without adding to marine*

As we are searching in the titles only, the terms used are broad. Search terms will always be searched for in truncated form, 
unless a space is included at the beginning/end (e.g. "fish" will find "fisher", "fishing", "codfish"), this works also for journal/anthology/book titles 
("ocean research" finds "marine and ocean research").

After consultation with NG/ÅM:
* fisheries and aquaculture, fish, crustaceans and aquatic toxicology kept general, not limited to marine (some FW may be included)
* Offshore oil and gas, offshore wind included, mostly maritime
* Technical research about e.g. cleaning technology for oil spills = ok
* Omega 3s health research included

## Description provided in reports

Tematiske områder som er inkludert i den bibliometriske kartleggingen 2020 (Bibliometrigruppen, Universitetsbiblioteket i samråd med marin dekan Nils Gunnar Kvamstø, marin direktør Amund Måge og seniorrådgiver Kari Nordvik):

* All forskning knyttet til havets og kystens miljø eller prosesser, for eksempel:
  *	marine habitater
  *	marine organismer
  *	fysisk og kjemisk oseanografi (e.g. strømmer, air-sea interaksjoner)
  *	marin geologi
  *	klima og havet 
  *	menneskets påvirkning på havet og marine organismer (e.g. forurensning)
*	Havbruk, fiskeriforskning og forskning på andre typer marin ressursbruk
*	Mat fra havet (e.g. sjømat, omega 3) og tilknytning til helse
*	Polar forskning koblet til det marine eller is (e.g. isbreer i polare områder)
*	Marine cryosphere (e.g. havis, ice floes)
*	Sjørett og havrett
*	Historie knyttet til havet (e.g. kystsamfunn, handelshistorie, fiskeri)
*	Blåøkonomi («blue growth»)
*	SDG 14

Under kartleggingen inkluderte den maritime delen av Marin forskning: 
* Marin og maritim teknologi, infrastruktur og ingeniørfag, for eksempel:
  * ROV, sjøfart
  * design av skip og marine strukturer (e.g. oppdrettsanlegg)
  * offshore vindkraft
  * offshore teknologi, infrastruktur, sikkerhet og arbeidsmiljø
  * fiskeri teknologi, sikkerhet, arbeid, lagring og prosessering

## Marin forskning

The general structure of the string is in sections of grouped search terms: 

* NPI fagfelt for marine technology (there isn't one for marine generally)
* Marine journals 
* Marine geographic areas/seas - Individual seas (worldwide) and currents around Norway used as search terms. Some were dropped if already covered by a term (e.g. "havet" in Norwegian will cover "Atlanterhavet", "ishavet" etc.). Source: most of the list on https://en.wikipedia.org/wiki/List_of_seas
* Marine environments/habitats - taken from SDG14
* Polar terms and areas - Restricted in combination with ice, the sea or oil - i.e. polar research about glaciers, ice caps, icebergs, oil drilling etc.
* Marine activities, law and technologies (applied)
* Marine organisms and species
* Research from the Sars Centre - included in its entirity after specification from NG/ÅM. The Sars Centre does not have very many publications, but this may nevertheless give a slight unfair advantage when comparing with other institutions, from a methodological standpoint. 

**Other notes**

`" ship"` is used due to e.g. leadership. 

Microplastics are included theoretically (i.e. marine pollution), but in Cristin many results were freshwater. 
However its exclusion does not mean that the topic is not covered - as the search string is so general, any research mentioning microplastics and oceans/marine/any seas will be included anyway! (even just saying "marine" is enough to be included).

```Ceylon =
IF CONTAINS([scientific_field_npi],	 "Marin og maritim teknologi"	)
		
OR CONTAINS(LOWER([journal]),	"sarsia"	)
OR CONTAINS(LOWER([journal]),	"pacific science"	)
OR CONTAINS(LOWER([journal]),	"marin"	)
OR CONTAINS(LOWER([journal]),	"ocean"	)
OR CONTAINS(LOWER([journal]),	"coastal"	)
OR (CONTAINS(LOWER([journal]),"aqua") AND NOT CONTAINS(LOWER([journal]),"aquatic insect"))		
OR CONTAINS(LOWER([journal]),	"estuar"	)
OR CONTAINS(LOWER([journal]),	"sea res"	)
OR CONTAINS(LOWER([journal]),	"fjord"	)
OR CONTAINS(LOWER([journal]),	"reef"	)
OR CONTAINS(LOWER([journal]),	"naupilus"	)
OR CONTAINS(LOWER([journal]),	"crustacea"	)
OR CONTAINS(LOWER([journal]),	"icthyol"	)
OR CONTAINS(LOWER([journal]),	"fish"	)
OR CONTAINS(LOWER([journal]),	"coral"	)
OR CONTAINS(LOWER([journal]),	"phycolog"	)
OR CONTAINS(LOWER([journal]),	"algae"	)
OR CONTAINS(LOWER([journal]),	"algal"	)
OR CONTAINS(LOWER([journal]),	"plankto"	)
OR CONTAINS(LOWER([journal]),	"nautilus"	)
		
OR CONTAINS(LOWER([journal]),	"sea tech"	)
OR CONTAINS(LOWER([journal]),	"nautilus"	)
OR CONTAINS(LOWER([journal]),	"wave"	)
OR CONTAINS(LOWER([journal]),	" ship"	)
OR CONTAINS(LOWER([journal]),	"ships"	)
OR CONTAINS(LOWER([journal]),	"offshore"	)
OR CONTAINS(LOWER([journal]),	"maritim"	)
THEN 'marin'		
		
		
ELSEIF		
CONTAINS(LOWER([result_title]),	"atlantic "	)
OR (CONTAINS(LOWER([result_title])," pacific") AND NOT CONTAINS(LOWER([result_title]),"pacificat"))		
OR CONTAINS(LOWER([result_title]),	"mediterranean sea"	)
OR CONTAINS(LOWER([result_title]),	"barents sea"	)
OR CONTAINS(LOWER([result_title]),	"greenland sea"	)
OR CONTAINS(LOWER([result_title]),	"north sea"	)
OR CONTAINS(LOWER([result_title]),	"norwegian sea"	)
OR CONTAINS(LOWER([result_title]),	"nordic seas"	)
OR CONTAINS(LOWER([result_title]),	"skager"	)
OR CONTAINS(LOWER([result_title]),	"arctic sea"	)
OR CONTAINS(LOWER([result_title]),	"ishav"	)
OR CONTAINS(LOWER([result_title]),	"chukchi sea"	)
OR CONTAINS(LOWER([result_title]),	"east Siberian sea"	)
OR CONTAINS(LOWER([result_title]),	"laptev sea"	)
OR CONTAINS(LOWER([result_title]),	"kara sea"	)
OR CONTAINS(LOWER([result_title]),	"labroador sea"	)
OR CONTAINS(LOWER([result_title]),	"Greenland sea"	)
OR CONTAINS(LOWER([result_title]),	"Beaufort sea"	)
OR CONTAINS(LOWER([result_title]),	"Sea of Okhotsk"	)
OR CONTAINS(LOWER([result_title]),	"weddell sea"	)
OR CONTAINS(LOWER([result_title]),	"ross sea"	)
OR CONTAINS(LOWER([result_title]),	"hudson bay"	)
OR CONTAINS(LOWER([result_title]),	"drake passage"	)
OR CONTAINS(LOWER([result_title]),	"bering strait"	)
OR CONTAINS(LOWER([result_title]),	"davis strait"	)
OR CONTAINS(LOWER([result_title]),	"nares strait"	)
OR CONTAINS(LOWER([result_title]),	"jan mayen"	)
OR CONTAINS(LOWER([result_title]),	"scotland ridge"	)
OR CONTAINS(LOWER([result_title]),	"greenland basin"	)
OR CONTAINS(LOWER([result_title]),	"international water"	)
OR CONTAINS(LOWER([result_title]),	"gulf stream"	)
OR CONTAINS(LOWER([result_title]),	"gulf of mexico"	)
OR CONTAINS(LOWER([result_title]),	"arctic water"	)
OR CONTAINS(LOWER([result_title]),	"polar water"	)
OR CONTAINS(LOWER([result_title]),	"arctic current"	)
OR CONTAINS(LOWER([result_title]),	"polar current"	)
THEN 'marin'		
		
ELSEIF		
CONTAINS(LOWER([result_title]),	"marin"	)
OR CONTAINS(LOWER([result_title]),	"havet"	)
OR CONTAINS(LOWER([result_title]),	"sjøområd"	)
OR CONTAINS(LOWER([result_title]),	"kyst "	)
OR CONTAINS(LOWER([result_title]),"ocean") AND NOT CONTAINS(LOWER([result_title]),"oceania")		
OR CONTAINS(LOWER([result_title]),	"seas "	)
OR CONTAINS(LOWER([result_title])," sea ") AND NOT CONTAINS(LOWER([result_title]),"sea scrolls")		
OR CONTAINS(LOWER([result_title]),	"coastal"	)
OR CONTAINS(LOWER([result_title]),	"seawater"	)
OR CONTAINS(LOWER([result_title]),	"deep sea"	)
OR CONTAINS(LOWER([result_title]),	"deep-sea"	)
OR CONTAINS(LOWER([result_title]),	"hydrothermal vent"	)
OR CONTAINS(LOWER([result_title]),	"vent field"	)
OR CONTAINS(LOWER([result_title]),	"chemosynthe"	)
OR CONTAINS(LOWER([result_title]),	"abyssal"	)
OR CONTAINS(LOWER([result_title]),	"seamount"	)
OR CONTAINS(LOWER([result_title]),	"seabed"	)
OR CONTAINS(LOWER([result_title]),	"seafloor"	)
OR CONTAINS(LOWER([result_title]),	"shelf"	)
OR CONTAINS(LOWER([result_title]),	"pelagic"	)
OR CONTAINS(LOWER([result_title]),	"benth"	)
OR CONTAINS(LOWER([result_title]),	"subtidal"	)
OR CONTAINS(LOWER([result_title]),	"intertidal"	)
OR CONTAINS(LOWER([result_title]),	"coastal"	)
OR CONTAINS(LOWER([result_title]),	"estuar"	)
OR CONTAINS(LOWER([result_title]),	"seashore"	)
OR CONTAINS(LOWER([result_title]),	"beach"	)
OR CONTAINS(LOWER([result_title]),	"fjord"	)
OR CONTAINS(LOWER([result_title]),	"reef"	)
OR CONTAINS(LOWER([result_title]),	"saltmarsh"	)
OR CONTAINS(LOWER([result_title]),	"salt marsh"	)
OR CONTAINS(LOWER([result_title]),	"mangrove"	)
OR CONTAINS(LOWER([result_title]),	"soft bottom"	)
THEN 'marin'		
		
ELSEIF		
CONTAINS(LOWER([result_title]),	"sea ice"	)
OR CONTAINS(LOWER([result_title]),	"sea-ice"	)
OR CONTAINS(LOWER([result_title]),	"ice floe"	)
OR CONTAINS(LOWER([result_title]),	"pack ice"	)
OR CONTAINS(LOWER([result_title]),	"polynya"	)
OR CONTAINS(LOWER([result_title]),	"ice stream"	)
OR CONTAINS(LOWER([result_title]),	"ice shelves"	)
OR CONTAINS(LOWER([result_title]),	"ice shelf"	)
OR CONTAINS(LOWER([result_title]),	" nilas "	)
OR CONTAINS(LOWER([result_title]),	"ice chart"	)
OR CONTAINS(LOWER([result_title]),	"iceberg"	)
OR CONTAINS(LOWER([result_title]),	"slush"	)
OR CONTAINS(LOWER([result_title]),	"pancake ice"	)
OR CONTAINS(LOWER([result_title]),	"ice ridge"	)
OR CONTAINS(LOWER([result_title]),	"havis"	)
OR CONTAINS(LOWER([result_title]),	"sjøis"	)
OR CONTAINS(LOWER([result_title]),	"isberg"	)
OR CONTAINS(LOWER([result_title]),	"sea level"	)
OR CONTAINS(LOWER([result_title]),	"sea-level"	)
OR CONTAINS(LOWER([result_title]),	"sea surface"	)
OR CONTAINS(LOWER([result_title]),	"sea-surface"	)
OR CONTAINS([result_title],	" SST "	)
OR CONTAINS(LOWER([result_title]),	"air-sea"	)
OR CONTAINS(LOWER([result_title]),	"air sea"	)
THEN 'marin'		
		
ELSEIF ((		
CONTAINS(LOWER([result_title]),	"arctic"	)
OR CONTAINS(LOWER([result_title]),	"arktisk"	)
OR CONTAINS(LOWER([result_title]),	"north pole"	)
OR CONTAINS(LOWER([result_title]),	"polar "	)
OR CONTAINS(LOWER([result_title]),	"high north"	)
OR CONTAINS(LOWER([result_title]),	"high-north"	)
OR CONTAINS(LOWER([result_title]),	"svalbard"	)
OR CONTAINS(LOWER([result_title]),	"spitsbergen"	)
OR CONTAINS(LOWER([result_title]),	"bjornoy"	)
OR CONTAINS(LOWER([result_title]),	"bjørnøy"	)
OR CONTAINS(LOWER([result_title]),	"jan mayan"	)
OR CONTAINS(LOWER([result_title]),	"greenland"	)
OR CONTAINS(LOWER([result_title]),	"north alaska"	)
OR CONTAINS(LOWER([result_title]),	"northern quebec"	)
OR CONTAINS(LOWER([result_title]),	"axel heiberg"	)
OR CONTAINS(LOWER([result_title]),	"north slope"	)
OR CONTAINS(LOWER([result_title]),	"prudhoe"	)
OR CONTAINS(LOWER([result_title]),	"barrow"	)
OR CONTAINS(LOWER([result_title]),	"zemlya"	)
OR CONTAINS(LOWER([result_title]),	"yermak"	)
OR CONTAINS(LOWER([result_title]),	"franz josef"	)
OR CONTAINS(LOWER([result_title]),	"northwest territories"	)
OR CONTAINS(LOWER([result_title]),	"high latitude"	)
OR CONTAINS(LOWER([result_title]),	"high-latitude"	)
OR CONTAINS(LOWER([result_title]),	"south pole"	)
)		
AND (		
CONTAINS(LOWER([result_title]),	"glacier"	)
OR CONTAINS(LOWER([result_title]),	"isbre"	)
OR CONTAINS(LOWER([result_title]),	"breen"	)
OR CONTAINS(LOWER([result_title]),	"breer"	)
OR CONTAINS(LOWER([result_title]),	"ice cap"	)
OR CONTAINS(LOWER([result_title]),	"ice field"	)
OR CONTAINS(LOWER([result_title]),	"icefield"	)
OR CONTAINS(LOWER([result_title]),	"ice sheet"	)
OR CONTAINS(LOWER([result_title]),	"ice cover"	)
OR CONTAINS(LOWER([result_title]),	"ice retreat"	)
OR CONTAINS(LOWER([result_title]),	"ice extent"	)
OR CONTAINS(LOWER([result_title]),	"ice thickness"	)
OR CONTAINS(LOWER([result_title]), " oil ") AND NOT CONTAINS(LOWER([result_title]), "oil sands") 		
OR CONTAINS(LOWER([result_title]),	"petroleum"	)
))		
THEN 'marin'		
		
ELSEIF		
CONTAINS(LOWER([result_title]),	"havforsk"	)
OR (CONTAINS(LOWER([result_title]),"forvalt") AND CONTAINS(LOWER([result_title]),"hav"))		
OR CONTAINS(LOWER([result_title]),	"havrett"	)
OR CONTAINS(LOWER([result_title]),	"sjørett"	)
		
OR CONTAINS(LOWER([result_title]),	"aquacult"	)
OR CONTAINS(LOWER([result_title]),	"maricult"	)
OR CONTAINS(LOWER([result_title]),	"havbruk"	)
OR CONTAINS(LOWER([result_title]),	"akvakultur"	)
OR CONTAINS(LOWER([result_title]),	"settefisk"	)
OR CONTAINS(LOWER([result_title]),	"lakseoppdrett"	)
OR CONTAINS(LOWER([result_title]),	"oppdrettsanlegg"	)
		
OR CONTAINS(LOWER([result_title]),	" dha "	)
OR CONTAINS(LOWER([result_title]),	"docosahexaenoic acid"	)
OR CONTAINS(LOWER([result_title]),	" epa "	)
OR CONTAINS(LOWER([result_title]),	"eicosapentaenoic acid"	)
OR CONTAINS(LOWER([result_title]),	"chain n-3 PUFA"	)
OR CONTAINS(LOWER([result_title]),	"omega 3"	)
OR CONTAINS(LOWER([result_title]),	"omega-3"	)
		
OR CONTAINS(LOWER([result_title]),	"havteknologi"	)
OR CONTAINS(LOWER([result_title]),	" rov "	)
OR CONTAINS(LOWER([result_title]),	" auv "	)
OR CONTAINS(LOWER([result_title]),	"underwater vehicle"	)
OR (CONTAINS(LOWER([result_title]),"underwater") AND CONTAINS(LOWER([result_title]),"robot"))		
OR CONTAINS(LOWER([result_title]),	"maritim"	)
OR CONTAINS(LOWER([result_title]),	"shipping"	)
OR CONTAINS(LOWER([result_title]),	" ship"	)
OR CONTAINS(LOWER([result_title]),	"ship routing"	)
OR CONTAINS(LOWER([result_title]),	"sjøfart"	)
OR CONTAINS(LOWER([result_title]),	"fiskefartø"	)
OR CONTAINS(LOWER([result_title]),	"sjømann"	)
OR CONTAINS(LOWER([result_title]),	"surface vessel"	)
OR CONTAINS(LOWER([result_title]),	"offshore"	)
OR CONTAINS(LOWER([result_title]),	"deep water"	)
OR CONTAINS(LOWER([result_title]),	"deep-water"	)
OR CONTAINS(LOWER([result_title]),	"deepwater"	)
OR CONTAINS(LOWER([result_title]),	"subsea "	)
OR CONTAINS(LOWER([result_title]),	"submersible"	)
OR CONTAINS(LOWER([result_title]),	"moonpool"	)
OR CONTAINS(LOWER([result_title]),	"mooring"	)
OR CONTAINS(LOWER([result_title]),	"moored"	)
OR CONTAINS(LOWER([result_title]),	"trawl"	)
OR CONTAINS(LOWER([result_title]),	"codend"	)
OR CONTAINS(LOWER([result_title]),	"lifeboat"	)
OR CONTAINS(LOWER([result_title]),	"sailboat"	)
OR CONTAINS(LOWER([result_title]),	"seaport"	)
		
OR CONTAINS(LOWER([result_title]),	"seafood"	)
OR CONTAINS(LOWER([result_title]),	"sjømat"	)
OR CONTAINS(LOWER([result_title]),	"seal fur"	)
OR CONTAINS(LOWER([result_title]),	"seal skin"	)
OR CONTAINS(LOWER([result_title]),	"seal products"	)
OR CONTAINS(LOWER([result_title]),	"hvalfangst"	)
OR CONTAINS(LOWER([result_title]),	"whaling"	)
		
OR CONTAINS(LOWER([result_title]),	"oil spill"	)
OR CONTAINS(LOWER([result_title]),	"blue growth"	)
then "marin"		
		
ELSEIF ((		
CONTAINS(LOWER([result_title]),	"vessel"	)
OR CONTAINS(LOWER([result_title]),	"hull "	)
)		
AND (		
CONTAINS(LOWER([result_title]),	"disabled"	)
OR CONTAINS(LOWER([result_title]),	"design"	)
OR CONTAINS(LOWER([result_title]),	"naval"	)
OR CONTAINS(LOWER([result_title]),	"fleet"	)
OR CONTAINS(LOWER([result_title]),	"harbour"	)
OR CONTAINS(LOWER([result_title]),	"navigat"	)
OR CONTAINS(LOWER([result_title]),	"route"	)
OR CONTAINS(LOWER([result_title]),	"roll"	)
))		
THEN 'marin'		
		
ELSEIF (		
CONTAINS(LOWER([result_title]),	"fouling"	)
AND (		
CONTAINS(LOWER([result_title]),	"net"	)
OR CONTAINS(LOWER([result_title]),	"vessel"	)
OR CONTAINS(LOWER([result_title]),	"aquaculture"	)
))		
THEN 'marin'		
		
ELSEIF (		
CONTAINS(LOWER([result_title]),	"floating"	)
AND (		
CONTAINS(LOWER([result_title]),	"storage"	)
OR CONTAINS(LOWER([result_title]),	"bodies"	)
OR CONTAINS(LOWER([result_title]),	"structure"	)
OR CONTAINS(LOWER([result_title]),	"turbine"	)
OR CONTAINS(LOWER([result_title]),	"drift"	)
))		
THEN 'marin'		
		
ELSEIF (		
CONTAINS(LOWER([result_title]),	"wave"	)
AND (		
CONTAINS(LOWER([result_title]),	"wind"	)
OR CONTAINS(LOWER([result_title]),	" ice"	)
OR CONTAINS(LOWER([result_title]),	"water"	)
OR CONTAINS(LOWER([result_title]),	"current"	)
OR CONTAINS(LOWER([result_title]),	"extreme"	)
OR CONTAINS(LOWER([result_title]),	"drift"	)
OR CONTAINS(LOWER([result_title]),	"rogue"	)
OR CONTAINS(LOWER([result_title]),	" forces"	)
OR CONTAINS(LOWER([result_title]),	" load"	)
OR CONTAINS(LOWER([result_title]),	"breaking"	)
OR CONTAINS(LOWER([result_title]),	"cylinder"	)
OR CONTAINS(LOWER([result_title]),	"monopile"	)
OR CONTAINS(LOWER([result_title]),	"platform"	)
OR CONTAINS(LOWER([result_title]),	"structure"	)
OR CONTAINS(LOWER([result_title]),	"anchor"	)
OR CONTAINS(LOWER([result_title]),	"vessel"	)
OR CONTAINS(LOWER([result_title]),	"fish farm"	)
OR CONTAINS(LOWER([result_title]),	"aquacult"	)
OR CONTAINS(LOWER([result_title]),	"pontoon"	)
OR CONTAINS(LOWER([result_title]),	"bridge"	)
OR CONTAINS(LOWER([result_title]),	"turbine"	)
OR CONTAINS(LOWER([result_title]),	"pipe"	)
OR CONTAINS(LOWER([result_title]),	"converter"	)
OR CONTAINS(LOWER([result_title]),	"combined energy"	)
OR CONTAINS(LOWER([result_title]),	"energy system"	)
))		
THEN 'marin'		
		
ELSEIF		
CONTAINS(LOWER([result_title]),	"dolphin"	)
OR CONTAINS(LOWER([result_title]),	"whale"	)
OR CONTAINS(LOWER([result_title]),	"porpoise"	)
OR CONTAINS(LOWER([result_title]),	"shark"	)
OR CONTAINS(LOWER([result_title]),	"seabird"	)
OR CONTAINS(LOWER([result_title]),	"penguin"	)
OR CONTAINS(LOWER([result_title]),	"polar bear"	)
THEN 'marin'		
		
		
ELSEIF(		
CONTAINS(LOWER([result_title]),	"seal"	)
AND (		
CONTAINS(LOWER([result_title]),	"harbour"	)
OR CONTAINS(LOWER([result_title]),	"harbor"	)
OR CONTAINS(LOWER([result_title]),	"hooded"	)
OR CONTAINS(LOWER([result_title]),	"harp"	)
OR CONTAINS(LOWER([result_title]),	"grey"	)
OR CONTAINS(LOWER([result_title]),	"elephant"	)
OR CONTAINS(LOWER([result_title]),	"leopard"	)
OR CONTAINS(LOWER([result_title]),	"weddell"	)
OR CONTAINS(LOWER([result_title]),	"ringed"	)
OR CONTAINS(LOWER([result_title]),	"true"	)
OR CONTAINS(LOWER([result_title]),	"eared"	)
OR CONTAINS(LOWER([result_title]),	"monk"	)
OR CONTAINS(LOWER([result_title]),	"population"	)
OR CONTAINS(LOWER([result_title]),	"colon"	)
OR CONTAINS(LOWER([result_title]),	"ban "	)
))		
THEN 'marin'		
		
ELSEIF		
CONTAINS(LOWER([result_title]),	"fish"	)
OR CONTAINS(LOWER([result_title]),	" fisk"	)
OR CONTAINS(LOWER([result_title]),	"salmon"	)
OR CONTAINS(LOWER([result_title]),	" laks "	)
OR CONTAINS(LOWER([result_title]),	"spawn"	)
OR CONTAINS(LOWER([result_title]),	" cod "	)
OR CONTAINS(LOWER([result_title]),	"torsk"	)
OR CONTAINS(LOWER([result_title]),	"trout"	)
OR CONTAINS(LOWER([result_title]),	"goby"	)
OR CONTAINS(LOWER([result_title]),	"smolt"	)
OR CONTAINS(LOWER([result_title]),	"haddock"	)
OR CONTAINS(LOWER([result_title]),	"saithe"	)
OR CONTAINS(LOWER([result_title]),	"blue whiting"	)
OR CONTAINS(LOWER([result_title]),	"orange roughy"	)
OR CONTAINS(LOWER([result_title]),	"pollock"	)
OR CONTAINS(LOWER([result_title]),	"halibut"	)
OR CONTAINS(LOWER([result_title]),	" sole "	)
OR CONTAINS(LOWER([result_title]),	"redfish"	)
OR CONTAINS(LOWER([result_title]),	" ling "	)
OR CONTAINS(LOWER([result_title]),	" hake "	)
OR CONTAINS(LOWER([result_title]),	"charr"	)
OR CONTAINS(LOWER([result_title]),	"wrasse"	)
OR CONTAINS(LOWER([result_title]),	"herring"	)
OR CONTAINS(LOWER([result_title]),	" sild"	)
OR CONTAINS(LOWER([result_title]),	"mackerel"	)
OR CONTAINS(LOWER([result_title]),	"anchov"	)
OR CONTAINS(LOWER([result_title]),	"sardine"	)
OR CONTAINS(LOWER([result_title]),	"sea bream"	)
OR CONTAINS(LOWER([result_title]),	"european eel"	)
		
		
OR CONTAINS(LOWER([result_title]),	"sponge"	)
OR CONTAINS(LOWER([result_title]),	"ascidia"	)
OR CONTAINS(LOWER([result_title]),	"krill"	)
OR CONTAINS(LOWER([result_title]),	"amphipod"	)
OR CONTAINS(LOWER([result_title]),	"barnacl"	)
OR CONTAINS(LOWER([result_title]),	" crab"	)
OR CONTAINS(LOWER([result_title]),	"copepod"	)
OR CONTAINS(LOWER([result_title]),	"lobster"	)
OR CONTAINS(LOWER([result_title]),	"shrimp"	)
OR CONTAINS(LOWER([result_title]),	"anisakis"	)
OR CONTAINS(LOWER([result_title]),	"squid"	)
OR CONTAINS(LOWER([result_title]),	"octopus"	)
OR CONTAINS(LOWER([result_title]),	"cuttlefish"	)
OR CONTAINS(LOWER([result_title]),	"oyster"	)
OR CONTAINS(LOWER([result_title]),	"scallop"	)
OR CONTAINS(LOWER([result_title]),	"mussel"	)
OR CONTAINS(LOWER([result_title]),	"bivalv"	)
OR CONTAINS(LOWER([result_title]),	"sea slug"	)
OR CONTAINS(LOWER([result_title]),	"coral"	)
OR CONTAINS(LOWER([result_title]),	"anemone"	)
OR CONTAINS(LOWER([result_title]),	"ctenophore"	)
OR CONTAINS(LOWER([result_title]),	"echinoderm"	)
OR CONTAINS(LOWER([result_title]),	"starfish"	)
OR CONTAINS(LOWER([result_title]),	"sea cucumber"	)
OR CONTAINS(LOWER([result_title]),	"sea star"	)
OR CONTAINS(LOWER([result_title]),	"sea urchin"	)
OR CONTAINS(LOWER([result_title]),	"brittle star"	)
OR CONTAINS(LOWER([result_title]),	"sand dollar"	)
		
OR CONTAINS(LOWER([result_title]),	"plankto"	)
OR CONTAINS(LOWER([result_title]),	"kelp"	)
OR CONTAINS(LOWER([result_title]),	"seagrass"	)
OR CONTAINS(LOWER([result_title]),	"eelgrass"	)
OR CONTAINS(LOWER([result_title]),	"seaweed"	)
OR CONTAINS(LOWER([result_title]),	"algae"	)
OR CONTAINS(LOWER([result_title]),	"algal"	)
		
OR CONTAINS(LOWER([result_title]),	"cetacea"	)
OR CONTAINS(LOWER([result_title]),	"pinniped"	)
OR CONTAINS(LOWER([result_title]),	"laridae"	)
OR CONTAINS(LOWER([result_title]),	"teleost"	)
OR CONTAINS(LOWER([result_title]),	"salmo "	)
OR CONTAINS(LOWER([result_title]),	"gadus mor"	)
OR CONTAINS(LOWER([result_title]),	"sebastes mentella"	)
OR CONTAINS(LOWER([result_title]),	"hoplostethus atlanticus"	)
OR CONTAINS(LOWER([result_title]),	"calanus"	)
OR CONTAINS(LOWER([result_title]),	"euphausi"	)
OR CONTAINS(LOWER([result_title]),	"pandalus "	)
OR CONTAINS(LOWER([result_title]),	"gobiusculus "	)
OR CONTAINS(LOWER([result_title]),	"melanogrammus "	)
OR CONTAINS(LOWER([result_title]),	"hippoglossus "	)
OR CONTAINS(LOWER([result_title]),	"salvelinus "	)
OR CONTAINS(LOWER([result_title]),	"labridae"	)
OR CONTAINS(LOWER([result_title]),	"labrus bergylta"	)
OR CONTAINS(LOWER([result_title]),	"clupeidae"	)
OR CONTAINS(LOWER([result_title]),	"clupea "	)
OR CONTAINS(LOWER([result_title]),	"scomber "	)
OR CONTAINS(LOWER([result_title]),	"rastrelliger "	)
OR CONTAINS(LOWER([result_title]),	"merluccius "	)
OR CONTAINS(LOWER([result_title]),	"sparus aurata"	)
OR CONTAINS(LOWER([result_title]),	"ophidiidae"	)
OR CONTAINS(LOWER([result_title]),	"homarus gammarus"	)
OR CONTAINS(LOWER([result_title]),	"nephrops norv"	)
OR CONTAINS(LOWER([result_title]),	"cancer pagurus"	)
OR CONTAINS(LOWER([result_title]),	"lophelia pertusa"	)
OR CONTAINS(LOWER([result_title]),	"laminaria"	)
OR CONTAINS(LOWER([result_title]),	"saccharina latissima"	)
OR CONTAINS(LOWER([result_title]),	"fucus "	)
OR CONTAINS(LOWER([result_title]),	"zostera "	)
OR CONTAINS(LOWER([result_title]),	"porifera"	)
OR CONTAINS(LOWER([result_title]),	"hexactinel"	)
OR CONTAINS(LOWER([result_title]),	"demospongi"	)
OR CONTAINS(LOWER([result_title]),	"calcarea"	)
OR CONTAINS(LOWER([result_title]),	"cnidaria"	)
OR CONTAINS(LOWER([result_title]),	"anthozoa"	)
OR CONTAINS(LOWER([result_title]),	"balanus "	)
OR CONTAINS(LOWER([result_title]),	"ostrea edulis"	)
OR CONTAINS(LOWER([result_title]),	"anguilla anguilla"	)
OR CONTAINS(LOWER([result_title]),	"holothur"	)
OR CONTAINS(LOWER([result_title]),	"echinoid"	)
OR CONTAINS(LOWER([result_title]),	"ophiuroid"	)
OR CONTAINS(LOWER([result_title]),	"asteroidea"	)
OR CONTAINS(LOWER([result_title]),	"crinoid"	)
then "marin"		

ELSEIF 		
CONTAINS(LOWER([result_title_anthology]),	"atlantic "	)
OR (CONTAINS(LOWER([result_title_anthology])," pacific") AND NOT CONTAINS(LOWER([result_title_anthology]),"pacificat"))		
OR CONTAINS(LOWER([result_title_anthology]),	"mediterranean sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"barents sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"greenland sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"north sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"norwegian sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"nordic seas"	)
OR CONTAINS(LOWER([result_title_anthology]),	"skager"	)
OR CONTAINS(LOWER([result_title_anthology]),	"arctic sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ishav"	)
OR CONTAINS(LOWER([result_title_anthology]),	"jan mayen"	)		
OR CONTAINS(LOWER([result_title_anthology]),	"international water"	)
OR CONTAINS(LOWER([result_title_anthology]),	"gulf stream"	)		
OR CONTAINS(LOWER([result_title_anthology]),	"arctic water"	)
OR CONTAINS(LOWER([result_title_anthology]),	"polar water"	)			
THEN 'marin'
		
ELSEIF		
CONTAINS(LOWER([result_title_anthology]),	"marin"	)
OR CONTAINS(LOWER([result_title_anthology]),	"havet"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sjøområd"	)
OR CONTAINS(LOWER([result_title_anthology]),	"kyst "	)
OR CONTAINS(LOWER([result_title_anthology]),"ocean") AND NOT CONTAINS(LOWER([result_title_anthology]),"oceania")		
OR CONTAINS(LOWER([result_title_anthology]),	"seas "	)
OR CONTAINS(LOWER([result_title_anthology])," sea ") AND NOT CONTAINS(LOWER([result_title_anthology]),"sea scroll")		
OR CONTAINS(LOWER([result_title_anthology]),	"coastal"	)
OR CONTAINS(LOWER([result_title_anthology]),	"seawater"	)
OR CONTAINS(LOWER([result_title_anthology]),	"deep sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"deep-sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"hydrothermal vent"	)
OR CONTAINS(LOWER([result_title_anthology]),	"vent field"	)		
		
OR CONTAINS(LOWER([result_title_anthology]),	"seamount"	)
OR CONTAINS(LOWER([result_title_anthology]),	"seabed"	)
OR CONTAINS(LOWER([result_title_anthology]),	"seafloor"	)
OR CONTAINS(LOWER([result_title_anthology]),	"shelf"	)
OR CONTAINS(LOWER([result_title_anthology]),	"pelagic"	)
OR CONTAINS(LOWER([result_title_anthology]),	"benth"	)
OR CONTAINS(LOWER([result_title_anthology]),	"subtidal"	)
OR CONTAINS(LOWER([result_title_anthology]),	"intertidal"	)
OR CONTAINS(LOWER([result_title_anthology]),	"coastal"	)
OR CONTAINS(LOWER([result_title_anthology]),	"estuar"	)
OR CONTAINS(LOWER([result_title_anthology]),	"seashore"	)
		
OR (CONTAINS(LOWER([result_title_anthology]),"fjord") AND (NOT CONTAINS(LOWER([result_title_anthology]),"fjordantologi") AND NOT CONTAINS(LOWER([result_title_anthology]),"fjords to the nile")))		
OR CONTAINS(LOWER([result_title_anthology]),	"reef"	)
OR CONTAINS(LOWER([result_title_anthology]),	"saltmarsh"	)
OR CONTAINS(LOWER([result_title_anthology]),	"salt marsh"	)
OR CONTAINS(LOWER([result_title_anthology]),	"mangrove"	)		
THEN 'marin'		

ELSEIF ((		
CONTAINS(LOWER([result_title_anthology]),	"arctic"	)
OR CONTAINS(LOWER([result_title_anthology]),	"arktisk"	)
OR CONTAINS(LOWER([result_title_anthology]),	"north pole"	)
OR CONTAINS(LOWER([result_title_anthology]),	"polar "	)
OR CONTAINS(LOWER([result_title_anthology]),	"high north"	)
OR CONTAINS(LOWER([result_title_anthology]),	"high-north"	)
OR CONTAINS(LOWER([result_title_anthology]),	"svalbard"	)
OR CONTAINS(LOWER([result_title_anthology]),	"spitsbergen"	)
OR CONTAINS(LOWER([result_title_anthology]),	"greenland"	)
OR CONTAINS(LOWER([result_title_anthology]),	"high latitude"	)
OR CONTAINS(LOWER([result_title_anthology]),	"high-latitude"	)
OR CONTAINS(LOWER([result_title_anthology]),	"south pole"	)
)		
AND (		
CONTAINS(LOWER([result_title_anthology]),	"glacier"	)
OR CONTAINS(LOWER([result_title_anthology]),	"isbre"	)
OR CONTAINS(LOWER([result_title_anthology]),	"breen"	)
OR CONTAINS(LOWER([result_title_anthology]),	"breer"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice cap"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice field"	)
OR CONTAINS(LOWER([result_title_anthology]),	"icefield"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice sheet"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice cover"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice retreat"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice extent"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice thickness"	)
OR CONTAINS(LOWER([result_title_anthology])," oil ") AND NOT CONTAINS(LOWER([result_title_anthology]),"oil sands")		
OR CONTAINS(LOWER([result_title_anthology]),	"petroleum"	)
))		
THEN 'marin'		

ELSEIF		
CONTAINS(LOWER([result_title_anthology]),	"havforsk"	)
OR (CONTAINS(LOWER([result_title_anthology]),"forvalt") AND CONTAINS(LOWER([result_title_anthology]),"hav"))		
OR CONTAINS(LOWER([result_title_anthology]),	"havrett"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sjørett"	)
		
OR CONTAINS(LOWER([result_title_anthology]),	"aquacult"	)
OR CONTAINS(LOWER([result_title_anthology]),	"maricult"	)
OR CONTAINS(LOWER([result_title_anthology]),	"havbruk"	)
OR CONTAINS(LOWER([result_title_anthology]),	"akvakultur"	)
OR CONTAINS(LOWER([result_title_anthology]),	"settefisk"	)
OR CONTAINS(LOWER([result_title_anthology]),	"lakseoppdrett"	)
OR CONTAINS(LOWER([result_title_anthology]),	"oppdrettsanlegg"	)
		
OR CONTAINS(LOWER([result_title_anthology]),	" dha "	)
OR CONTAINS(LOWER([result_title_anthology]),	"docosahexaenoic acid"	)
OR CONTAINS(LOWER([result_title_anthology]),	" epa "	)
OR CONTAINS(LOWER([result_title_anthology]),	"eicosapentaenoic acid"	)
OR CONTAINS(LOWER([result_title_anthology]),	"chain n-3 PUFA"	)
OR CONTAINS(LOWER([result_title_anthology]),	"omega 3"	)
OR CONTAINS(LOWER([result_title_anthology]),	"omega-3"	)
		
OR CONTAINS(LOWER([result_title_anthology]),	"havteknologi"	)
OR CONTAINS(LOWER([result_title_anthology]),	" rov "	)
OR CONTAINS(LOWER([result_title_anthology]),	" auv "	)
OR CONTAINS(LOWER([result_title_anthology]),	"underwater vehicle"	)
OR (CONTAINS(LOWER([result_title_anthology]),"underwater") AND CONTAINS(LOWER([result_title_anthology]),"robot"))		
OR CONTAINS(LOWER([result_title_anthology]),	"maritim"	)
OR CONTAINS(LOWER([result_title_anthology]),	"shipping"	)
OR CONTAINS(LOWER([result_title_anthology]),	" ship"	)
		
OR CONTAINS(LOWER([result_title_anthology]),	"sjøfart"	)
OR CONTAINS(LOWER([result_title_anthology]),	"fiskefartø"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sjømann"	)
OR CONTAINS(LOWER([result_title_anthology]),	"surface vessel"	)
OR CONTAINS(LOWER([result_title_anthology]),	"offshore"	)
OR CONTAINS(LOWER([result_title_anthology]),	"deep water"	)
OR CONTAINS(LOWER([result_title_anthology]),	"deep-water"	)
OR CONTAINS(LOWER([result_title_anthology]),	"deepwater"	)
OR CONTAINS(LOWER([result_title_anthology]),	"subsea "	)
OR CONTAINS(LOWER([result_title_anthology]),	"submersible"	)
OR CONTAINS(LOWER([result_title_anthology]),	"moonpool"	)
OR CONTAINS(LOWER([result_title_anthology]),	"mooring"	)
OR CONTAINS(LOWER([result_title_anthology]),	"moored"	)
OR CONTAINS(LOWER([result_title_anthology]),	"trawl"	)		
OR CONTAINS(LOWER([result_title_anthology]),	"lifeboat"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sailboat"	)
OR CONTAINS(LOWER([result_title_anthology]),	"seaport"	)		
OR CONTAINS(LOWER([result_title_anthology]),	"seafood"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sjømat"	)
OR CONTAINS(LOWER([result_title_anthology]),	"hvalfangst"	)
OR CONTAINS(LOWER([result_title_anthology]),	"whaling"	)
OR CONTAINS(LOWER([result_title_anthology]),	"oil spill"	)
OR CONTAINS(LOWER([result_title_anthology]),	"blue growth"	)
then "marin"	
	
ELSEIF		
CONTAINS(LOWER([result_title_anthology]),	"whale"	)
OR CONTAINS(LOWER([result_title_anthology]),	"polar bear"	)		
OR CONTAINS(LOWER([result_title_anthology]),	" fish"	)
OR CONTAINS(LOWER([result_title_anthology]),	" fisk"	)
OR CONTAINS(LOWER([result_title_anthology]),	"salmon"	)
OR CONTAINS(LOWER([result_title_anthology]),	" laks "	)
OR CONTAINS(LOWER([result_title_anthology]),	"spawn"	)
OR CONTAINS(LOWER([result_title_anthology]),	" cod "	)
OR CONTAINS(LOWER([result_title_anthology]),	"torsk"	)
OR CONTAINS(LOWER([result_title_anthology]),	"trout"	)
		
OR CONTAINS(LOWER([result_title_anthology]),	"plankto"	)
OR CONTAINS(LOWER([result_title_anthology]),	"algae"	)
OR CONTAINS(LOWER([result_title_anthology]),	"seaweed"	)
		
OR CONTAINS(LOWER([result_title_anthology]),	"echinoderm"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sponge"	)
OR CONTAINS(LOWER([result_title_anthology]),	"porifera"	)
THEN "marin"		

ELSEIF 
([institution_id] == 184 AND [unit_id_level_3] == 92)
THEN "marin"

ELSE "non"
END
```

## Maritim forskning

The string for marine should also contain all terms for maritime - don't add to maritime without adding to marine. 
It does however contain some additional terms as *limitations* of more general terms in the marine string. For example, "ocean" must be combined with "technology"; fishing and aquaculture terms must be used in combination with technology or safety terms. 

```Ceylon =
IF CONTAINS([scientific_field_npi],	"Marin og maritim teknologi"	)
		
OR CONTAINS(LOWER([journal]),	"sea tech"	)
OR CONTAINS(LOWER([journal]),	"nautilus"	)
OR CONTAINS(LOWER([journal]),	"wave"	)
OR CONTAINS(LOWER([journal]),	" ship"	)
OR CONTAINS(LOWER([journal]),	"ships"	)
OR CONTAINS(LOWER([journal]),	"offshore"	)
OR CONTAINS(LOWER([journal]),	"maritim"	)
OR CONTAINS(LOWER([journal]),	"aquacultural engineering"	)
OR CONTAINS(LOWER([journal]),	"ocean engineering"	)
THEN "maritim"		
		
ELSEIF ((		
CONTAINS(LOWER([journal]),	"ocean"	)
OR CONTAINS(LOWER([journal]),	"marine"	)
)		
AND 		
CONTAINS(LOWER([journal]),	"engineering"	)
)
THEN "maritim"		
		
ELSEIF		
CONTAINS(LOWER([result_title]),	"sjørett"	)
OR CONTAINS(LOWER([result_title]),	"oppdrettsanlegg"	)
OR CONTAINS(LOWER([result_title]),	"havteknologi"	)
OR CONTAINS(LOWER([result_title]),	" rov "	)
OR CONTAINS(LOWER([result_title]),	" auv "	)
OR CONTAINS(LOWER([result_title]),	"underwater vehicle"	)
OR (CONTAINS(LOWER([result_title]),"underwater") AND CONTAINS(LOWER([result_title]),"robot"))		
OR (CONTAINS(LOWER([result_title]),"maritim") AND NOT CONTAINS(LOWER([result_title]),"maritimum"))		
OR CONTAINS(LOWER([result_title]),	"shipping"	)
OR CONTAINS(LOWER([result_title]),	" ship"	)
OR CONTAINS(LOWER([result_title]),	"ship routing"	)
OR CONTAINS(LOWER([result_title]),	"sjøfart"	)
OR CONTAINS(LOWER([result_title]),	"fiskefartø"	)
OR CONTAINS(LOWER([result_title]),	"sjømann"	)
OR CONTAINS(LOWER([result_title]),	"surface vessel"	)
OR CONTAINS(LOWER([result_title]),	"offshore"	)
OR CONTAINS(LOWER([result_title]),	"subsea "	)
OR CONTAINS(LOWER([result_title]),	"submersible"	)
OR CONTAINS(LOWER([result_title]),	"moonpool"	)
OR CONTAINS(LOWER([result_title]),	"mooring"	)
OR CONTAINS(LOWER([result_title]),	"moored"	)
OR CONTAINS(LOWER([result_title]),	"codend"	)
OR CONTAINS(LOWER([result_title]),	"lifeboat"	)
OR CONTAINS(LOWER([result_title]),	"sailboat"	)
OR CONTAINS(LOWER([result_title]),	"seaport"	)
THEN "maritim"		
		
ELSEIF ((		
CONTAINS(LOWER([result_title]),	"vessel"	)
OR CONTAINS(LOWER([result_title]),	"hull "	)
)		
AND (		
CONTAINS(LOWER([result_title]),	"disabled"	)
OR CONTAINS(LOWER([result_title]),	"design"	)
OR CONTAINS(LOWER([result_title]),	"naval"	)
OR CONTAINS(LOWER([result_title]),	"fleet"	)
OR CONTAINS(LOWER([result_title]),	"harbour"	)
OR CONTAINS(LOWER([result_title]),	"navigat"	)
OR CONTAINS(LOWER([result_title]),	"route"	)
))		
THEN "maritim"		
		
ELSEIF (		
CONTAINS(LOWER([result_title]),	"fouling"	)
AND (		
CONTAINS(LOWER([result_title]),	"net"	)
OR CONTAINS(LOWER([result_title]),	"vessel"	)
OR CONTAINS(LOWER([result_title]),	"aquaculture"	)
OR CONTAINS(LOWER([result_title]),	"salmon farm"	)
))		
THEN "maritim"		
		
ELSEIF (		
CONTAINS(LOWER([result_title]),	"floating"	)
AND (		
CONTAINS(LOWER([result_title]),	"storage"	)
OR CONTAINS(LOWER([result_title]),	"bodies"	)
OR CONTAINS(LOWER([result_title]),	"structure"	)
OR CONTAINS(LOWER([result_title]),	"turbine"	)
OR CONTAINS(LOWER([result_title]),	"drift"	)
))		
THEN "maritim"		
		
ELSEIF (		
CONTAINS(LOWER([result_title]),	"wave"	)
AND (		
CONTAINS(LOWER([result_title]),	" forces"	)
OR CONTAINS(LOWER([result_title]),	" load"	)
OR CONTAINS(LOWER([result_title]),	"breaking"	)
OR CONTAINS(LOWER([result_title]),	"cylinder"	)
OR CONTAINS(LOWER([result_title]),	"monopile"	)
OR CONTAINS(LOWER([result_title]),	"platform"	)
OR CONTAINS(LOWER([result_title]),	"structure"	)
OR CONTAINS(LOWER([result_title]),	"anchor"	)
OR CONTAINS(LOWER([result_title]),	"vessel"	)
OR CONTAINS(LOWER([result_title]),	"fish farm"	)
OR CONTAINS(LOWER([result_title]),	"aquacult"	)
OR CONTAINS(LOWER([result_title]),	"pontoon"	)
OR CONTAINS(LOWER([result_title]),	"bridge"	)
OR CONTAINS(LOWER([result_title]),	"turbine"	)
OR CONTAINS(LOWER([result_title]),	"pipe"	)
OR CONTAINS(LOWER([result_title]),	"converter"	)
OR CONTAINS(LOWER([result_title]),	"combined energy"	)
OR CONTAINS(LOWER([result_title]),	"energy system"	)
))		
THEN 'maritim'		
		
ELSEIF ((		
CONTAINS(LOWER([result_title]),	"ocean"	)
OR CONTAINS(LOWER([result_title]),	"marine"	)
OR CONTAINS(LOWER([result_title]),	"deep water"	)
OR CONTAINS(LOWER([result_title]),	"deep-water"	)
OR CONTAINS(LOWER([result_title]),	"seabed"	)
OR CONTAINS(LOWER([result_title]),	"seafloor"	)
)
AND (		
CONTAINS(LOWER([result_title]),	" robot"	)
OR CONTAINS(LOWER([result_title]),	"cable"	)
OR CONTAINS(LOWER([result_title]),	"fleet"	)
OR (CONTAINS(LOWER([result_title])," pipe") AND NOT CONTAINS(LOWER([result_title]),"discovery pipe"))
OR CONTAINS(LOWER([result_title]),	"vehicle"	)
OR CONTAINS(LOWER([result_title]),	"operations"	)
OR CONTAINS(LOWER([result_title]),	" technolog"	)
))		
THEN "maritim"	

ELSEIF (	
CONTAINS(LOWER([result_title]),	"underwater vehicle")
OR (CONTAINS(LOWER([result_title]),"underwater") AND CONTAINS(LOWER([result_title]),"robot"))	
)	
THEN "maritim"	


ELSEIF ((		
CONTAINS(LOWER([result_title]),	"deep water"	)
OR CONTAINS(LOWER([result_title]),	"deep-water"	)
)
AND (		
CONTAINS(LOWER([result_title]),	"drill"	)
OR CONTAINS(LOWER([result_title]),	"anchor"	)
OR CONTAINS(LOWER([result_title]),	" oil"	)
))		
THEN "maritim"	
				
		
		
ELSEIF ((		
CONTAINS(LOWER([result_title]),	"fish"	)
OR CONTAINS(LOWER([result_title]),	"aquacult"	)
OR CONTAINS(LOWER([result_title]),	" cod "	)
OR CONTAINS(LOWER([result_title]),	"haddock"	)
OR CONTAINS(LOWER([result_title]),	"redfish"	)
OR CONTAINS(LOWER([result_title]),	"salmon"	)
OR CONTAINS(LOWER([result_title]),	"whiting"	)
OR CONTAINS(LOWER([result_title]),	"pollock"	)
OR CONTAINS(LOWER([result_title]),	"mackerel"	)
OR CONTAINS(LOWER([result_title]),	"herring"	)
OR CONTAINS(LOWER([result_title]),	"halibut"	)
OR CONTAINS(LOWER([result_title]),	" sole "	)
OR CONTAINS(LOWER([result_title]),	" hake "	)
OR CONTAINS(LOWER([result_title]),	"anchov"	)
OR CONTAINS(LOWER([result_title]),	"sardine"	))
AND (		
CONTAINS(LOWER([result_title]),	"gear"	)
OR CONTAINS(LOWER([result_title]),	"catch performance"	)
OR CONTAINS(LOWER([result_title]),	"catch efficiency"	)
OR CONTAINS(LOWER([result_title]),	"controlled storage"	)
OR CONTAINS(LOWER([result_title]),	"chilled storage"	)
OR CONTAINS(LOWER([result_title]),	"chilling"	)
OR CONTAINS(LOWER([result_title]),	"frozen storage"	)
OR CONTAINS(LOWER([result_title]),	"storage freez"	)
OR CONTAINS(LOWER([result_title]),	"ice storage"	)
OR CONTAINS(LOWER([result_title]),	"refridge"	)
OR CONTAINS(LOWER([result_title]),	"processing"	)
OR CONTAINS(LOWER([result_title]),	" grid"	)
OR CONTAINS(LOWER([result_title]),	"robot"	)
OR CONTAINS(LOWER([result_title]),	"autonomous"	)
OR CONTAINS(LOWER([result_title]),	"machine"	)
OR CONTAINS(LOWER([result_title]),	"hydraulic"	)
))		
THEN "maritim"		
		
ELSEIF ((		
CONTAINS(LOWER([result_title]),	"trawl"	)
OR CONTAINS(LOWER([result_title]),	"aquacult"	))
AND (		
CONTAINS(LOWER([result_title]),	"performance"	)
OR CONTAINS(LOWER([result_title]),	"device"	)
OR CONTAINS(LOWER([result_title]),	"vehicle"	)
OR CONTAINS(LOWER([result_title]),	"size selecti"	)
OR CONTAINS(LOWER([result_title]),	"design"	)
OR CONTAINS(LOWER([result_title]),	"operations"	)
OR CONTAINS(LOWER([result_title]),	"fillet quality"	)
OR CONTAINS(LOWER([result_title]),	"safety climate"	)
OR CONTAINS(LOWER([result_title]),	"occupational safety"	)
OR CONTAINS(LOWER([result_title]),	"technolog"	)
))		
THEN "maritim"		

ELSEIF		
CONTAINS(LOWER([result_title_anthology]),	"sjørett"	)
OR CONTAINS(LOWER([result_title_anthology]),	"oppdrettsanlegg"	)
OR CONTAINS(LOWER([result_title_anthology]),	"havteknologi"	)
OR CONTAINS(LOWER([result_title_anthology]),	" rov "	)
OR CONTAINS(LOWER([result_title_anthology]),	" auv "	)
OR CONTAINS(LOWER([result_title_anthology]),	"underwater vehicle"	)
OR (CONTAINS(LOWER([result_title_anthology]),"underwater") AND CONTAINS(LOWER([result_title_anthology]),"robot"))		
OR (CONTAINS(LOWER([result_title_anthology]),"maritim") AND NOT CONTAINS(LOWER([result_title_anthology]),"maritimum"))		
OR CONTAINS(LOWER([result_title_anthology]),	"shipping"	)
OR CONTAINS(LOWER([result_title_anthology]),	" ship"	)
		
OR CONTAINS(LOWER([result_title_anthology]),	"sjøfart"	)
OR CONTAINS(LOWER([result_title_anthology]),	"fiskefartø"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sjømann"	)
OR CONTAINS(LOWER([result_title_anthology]),	"surface vessel"	)
OR CONTAINS(LOWER([result_title_anthology]),	"offshore"	)
OR CONTAINS(LOWER([result_title_anthology]),	"subsea "	)
OR CONTAINS(LOWER([result_title_anthology]),	"submersible"	)
OR CONTAINS(LOWER([result_title_anthology]),	"moonpool"	)
		
			
OR CONTAINS(LOWER([result_title_anthology]),	"lifeboat"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sailboat"	)
OR CONTAINS(LOWER([result_title_anthology]),	"seaport"	)
THEN "maritim"		

ELSE "non"		
END
```


