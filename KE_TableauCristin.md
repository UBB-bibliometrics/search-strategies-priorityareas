
# Climate and energy transition (Klima og energiomstilling)

Identifies scientific articles/books/chapters connected to the climate and energy transition priority area. String to use in Tableau against "FOR_data_sted_total"-extract from DUCT or live.

The searches are run in mainly 2 fields, result title (title of the work) and journal name. **Important note**: Each string must ALSO be run against "result_title_anthology" to catch book results (where book titles are in a different field, and chapter titles count as result titles). This is NOT added explicitly here (except in the first, general string). Strings for result_title can be repeated, and this field changed out.

## Description provided in reports (Norwegian)

Tematiske områder som er inkludert i den bibliometriske kartleggingen 2020 (Bibliometrigruppen, Universitetsbiblioteket i samråd med forskningsdekan Gunn Mangerud og direktørene Kristin Guldbransen Frøysa, Tore Furevik). Redigert etter forslag om søkebegrep fra KGF i vår 2024. 

Klimasystemer og Effekter

- Klimaendringer i atmosfære og hav (ikke all meteorologi og oseanografi)
- Klima i polare regioner
- Havis og isbreer /kryosfære
- Utvikling av klimamodeller
- cloud-atmosphere feedback 
- Klimaekstremer (nedbør, temperatur mm)
- Havforsuring
- Klimaendringer og påvirkning på
	- dyr, dyremangfold og habitat
	- menneskers habitat, landbruk og matforsyning
- Klimagasser/greenhouse gasses
- Endringer i permafrost
- (Paleoklima) så lenge forskningen er relatert til dagens klimaendringer
- Ikke miljøvern

Klimatilpasning
- Tilpasning/politikk/rammeverk/tiltak mot klimaendringene
- Tilpasse seg klimarelaterte farer og naturkatastrofer /klimaekstreme
- Klimaholdinger livstilendringer, rammeverk, kultur, moral, etikk, debatt
- Klimarettferdighet, lover, regler og etikk

Klimatilpasning og Energiomstilling (overlapp)
- C02 lagring (CSS/CCUS) 
- Klimakvoteloven/utslippskvoter/avtaler (Paris, COP osv.)
- Grønt skifte
- Sirkulær økonomi
- Green cities 
- Green transport
- Green processes (industry)
- Lave klimautslipp 

Energiomstilling
- Energiomstilling, regulering av energisystemer (politisk, økonomisk, juridisk)
- Energieffektiv
- Fornybare energikilder generelt
- Vindenergi (havvind og landvind)
- Energi, kraft, brensel, drivstoff fra algae, lignin, ammoniakk, tidevann og hydrogen
- Geotermisk energi
- Fotovoltaik (PV), solenergi
- Bioenergi

Merk an noen områder overlapper med satsningen for Globale Samfunnsutfordringer, for eksempel:
- «Klimaflykninger», klimaendringer og migrasjon
- Klimaendringer og jordbruk/landbruk, klimaendringer i low and middle income countries
- Klimaendringer og helse


## Any undertopic (generic terms)

Title and journal search. These are generic terms, so it is hard to pin them to a sub-topic, but we want to make sure that they are caught.

```py =
IF			
(CONTAINS(LOWER([Result Title]),"climat") AND CONTAINS(LOWER([Result Title]), "chang"))
OR (CONTAINS(LOWER([Result Title]),"warm") AND CONTAINS(LOWER([Result Title]), "global"))
OR (CONTAINS(LOWER([Result Title]),"climat") AND CONTAINS(LOWER([Result Title]), "warm"))
OR (CONTAINS(LOWER([Result Title]),"ocean") AND CONTAINS(LOWER([Result Title]),	"warm"))
OR CONTAINS([Result Title],"IPCC") 

OR CONTAINS(LOWER([Result Title]),"klimaendring") 
		
OR CONTAINS(LOWER([Journal]), "nature climate change")
OR CONTAINS(LOWER([Journal]), "weather, climate and society")
OR CONTAINS(LOWER([Journal]), "disciplinary reviews: climate change")
THEN "general"
ELSE "non"
END
```

## Climate systems and effects (Klimasystemer og effekter)

### Title search

```py =
IF
CONTAINS(LOWER([result_title]),	"klimasystem"	)
OR CONTAINS(LOWER([result_title]),	"klimadynamikk"	)
OR CONTAINS(LOWER([result_title]),	"klimamodell"	)
OR CONTAINS(LOWER([result_title]),	"klimaeffekt"	)
OR CONTAINS(LOWER([result_title]),	"klimavirkni"	)
OR CONTAINS(LOWER([result_title]),	"klimavit"	)
OR
(
	CONTAINS(LOWER([result_title]),	"climat"	)
	AND	(		
	CONTAINS(LOWER([result_title]),	"coupl"	)
	OR CONTAINS(LOWER([result_title]),	"vulnerable"	)
	OR CONTAINS(LOWER([result_title]),	"projection"	)
	OR CONTAINS(LOWER([result_title]),	"dynamic"	)
	OR CONTAINS(LOWER([result_title]),	"system"	)
	OR CONTAINS(LOWER([result_title]),	"data"	)
	OR CONTAINS(LOWER([result_title]),	"model"	)
	OR CONTAINS(LOWER([result_title]),	"carbon"	)
	OR CONTAINS(LOWER([result_title]),	"feedback"	)
	OR CONTAINS(LOWER([result_title]),	"interact"	)
	OR CONTAINS(LOWER([result_title]),	"scenario"	)
	OR CONTAINS(LOWER([result_title]),	"regime"	)
	OR CONTAINS(LOWER([result_title]),	"shift"	)
	OR CONTAINS(LOWER([result_title]),	"extreme"	)
	OR CONTAINS(LOWER([result_title]),	"responce"	)
	OR CONTAINS(LOWER([result_title]),	"response"	)
	OR CONTAINS(LOWER([result_title]),	"forc"	)
	OR CONTAINS(LOWER([result_title]),	"sensitiv"	)
	OR CONTAINS(LOWER([result_title]),	"warm"	)
	OR CONTAINS(LOWER([result_title]),	"goal"	)
	OR CONTAINS(LOWER([result_title]),	"amplificat"	)
	OR CONTAINS(LOWER([result_title]),	"record"	)
	OR CONTAINS(LOWER([result_title]),	"predict"	)
	OR CONTAINS(LOWER([result_title]),	"state"	)
	OR CONTAINS(LOWER([result_title]),	"fluctuat"	)
	OR CONTAINS(LOWER([result_title]),	"simulat"	)
	OR CONTAINS(LOWER([result_title]),	"variab"	)
	OR CONTAINS(LOWER([result_title]),	"driver"	)
	OR CONTAINS(LOWER([result_title]),	"trend"	)
	OR CONTAINS(LOWER([result_title]),	"legacy"	)
	OR CONTAINS(LOWER([result_title]),	"anthropo"	)
	OR CONTAINS(LOWER([result_title]),	"trigger"	)

	OR CONTAINS(LOWER([result_title]),	"oscillation"	)
	OR CONTAINS(LOWER([result_title]),	"annular mode"	)
	OR CONTAINS(LOWER([result_title]),	"pattern"	)
	OR CONTAINS(LOWER([result_title]),	"atmosph"	)
	OR CONTAINS(LOWER([result_title]),	"cloud"	)
	OR CONTAINS(LOWER([result_title]),	"rain"	)
	OR CONTAINS(LOWER([result_title]),	"precipitation"	)
	OR CONTAINS(LOWER([result_title]),	"snow"	)
	OR CONTAINS(LOWER([result_title]),	"storm"	)
	OR CONTAINS(LOWER([result_title]),	"weather"	)
	OR CONTAINS(LOWER([result_title]),	"monsoon"	)
	OR CONTAINS(LOWER([result_title]),	"cyclon"	)
	OR CONTAINS(LOWER([result_title]),	"typho"	)
	OR CONTAINS(LOWER([result_title]),	"temperatur"	)
	OR CONTAINS(LOWER([result_title]),	"meteorolog"	)
	OR CONTAINS(LOWER([result_title]),	"overturning"	)

	OR CONTAINS(LOWER([result_title]),	"permafrost"	)
	OR CONTAINS(LOWER([result_title]),	"paleo"	)
	OR CONTAINS(LOWER([result_title]),	"past"	)
	OR CONTAINS(LOWER([result_title]),	"reconstruction"	)
	OR CONTAINS(LOWER([result_title]),	"ice-core"	)
	OR CONTAINS(LOWER([result_title]),	"ice core"	)
	OR CONTAINS(LOWER([result_title]),	"precambrian"	)
	OR CONTAINS(LOWER([result_title]),	"phanerozoi"	)
	OR CONTAINS(LOWER([result_title]),	"quaternary"	)
	OR CONTAINS(LOWER([result_title]),	"pleistocene"	)
	OR CONTAINS(LOWER([result_title]),	"phanerozoi"	)
	OR CONTAINS(LOWER([result_title]),	"holocene"	)
	OR CONTAINS(LOWER([result_title]),	"litholog"	)
	OR CONTAINS(LOWER([result_title]),	"geologic"	)
	OR CONTAINS(LOWER([result_title]),	"history"	)

	OR CONTAINS(LOWER([result_title]),	"arid"	)
	OR CONTAINS(LOWER([result_title]),	"desert"	)
	OR CONTAINS(LOWER([result_title]),	"flood"	)
	OR CONTAINS(LOWER([result_title]),	"drought"	)
	OR CONTAINS(LOWER([result_title]),	"landslide"	)
	OR CONTAINS(LOWER([result_title]),	"cryosphere"	)
	OR CONTAINS(LOWER([result_title]),	"wetland"	)
	OR CONTAINS(LOWER([result_title]),	"erosion"	)
	OR CONTAINS(LOWER([result_title]),	"groundwater"	)

	OR CONTAINS(LOWER([result_title]),	"tundra"	)
	OR CONTAINS(LOWER([result_title]),	"ecosystem"	)
	OR CONTAINS(LOWER([result_title]),	"forest"	)
	OR CONTAINS(LOWER([result_title]),	"taiga"	)
	OR CONTAINS(LOWER([result_title]),	"treeline"	)
	OR CONTAINS(LOWER([result_title]),	"forest"	)
	OR CONTAINS(LOWER([result_title]),	"diversity"	)
	OR CONTAINS(LOWER([result_title]),	"pollen"	)
	OR CONTAINS(LOWER([result_title]),	"vegetation"	)
	OR CONTAINS(LOWER([result_title]),	"swamp"	)
	OR CONTAINS(LOWER([result_title]),	"coral"	)
	OR CONTAINS(LOWER([result_title]),	"plankton"	)
	OR CONTAINS(LOWER([result_title]),	"alga"	)
	OR CONTAINS(LOWER([result_title]),	"reef"	)
	OR CONTAINS(LOWER([result_title]),	"ocean"	)
	OR REGEXP_MATCH([result_title],	"\bsea"	))
)	
THEN "SYSEFF"

ELSEIF (		
CONTAINS(LOWER([result_title]),	"arctic future"	)
OR CONTAINS(LOWER([result_title]),	"future arctic"	)
OR CONTAINS(LOWER([result_title]),	"water mass transformation"	)
OR CONTAINS(LOWER([result_title]),	"water mass formation"	)
OR
(
	(CONTAINS(LOWER([result_title]),	"decadal"	)
	OR CONTAINS(LOWER([result_title]),	"seasonal"	))
	AND		
	(CONTAINS(LOWER([result_title]),	"prediction"	)
	OR CONTAINS(LOWER([result_title]),	"variabilit"	)
	OR CONTAINS(LOWER([result_title]),	"oscillation"	))
)
)
THEN "SYSEFF"		

ELSEIF		
(
	(CONTAINS(LOWER([result_title]),	"climat"	)
	OR CONTAINS(LOWER([result_title]),	"klima"	))
	AND		
	(CONTAINS(LOWER([result_title]),	"arctic"	)
	OR REGEXP_MATCH([result_title],	"\barktisk"	)
	OR REGEXP_MATCH([result_title],	"\bantarktisk"	)
	OR CONTAINS(LOWER([result_title]),	"polar"	)
	OR CONTAINS(LOWER([result_title]),	"northpole"	)
	OR CONTAINS(LOWER([result_title]),	"north pole"	)
	OR CONTAINS(LOWER([result_title]),	"highnorth"	)
	OR CONTAINS(LOWER([result_title]),	"high-north"	)
	OR CONTAINS(LOWER([result_title]),	"svalbard"	)
	OR CONTAINS(LOWER([result_title]),	"spitsbergen"	)
	OR CONTAINS(LOWER([result_title]),	"bjornoya"	)
	OR CONTAINS(LOWER([result_title]),	"jan mayen"	)
	OR CONTAINS(LOWER([result_title]),	"greenland"	)
	OR CONTAINS(LOWER([result_title]),	"north alaska"	)
	OR CONTAINS(LOWER([result_title]),	"north quebec"	)

	OR CONTAINS(LOWER([result_title]),	"northslope"	)
	OR CONTAINS(LOWER([result_title]),	"prudhoe"	)
	OR CONTAINS(LOWER([result_title]),	"barrow"	)
	OR CONTAINS(LOWER([result_title]),	"zemlya"	)
	OR CONTAINS(LOWER([result_title]),	"yermak"	)
	OR CONTAINS(LOWER([result_title]),	"franz josef"	)
	OR CONTAINS(LOWER([result_title]),	"north west territories"	)
	OR CONTAINS(LOWER([result_title]),	"high latitude"	)
	OR CONTAINS(LOWER([result_title]),	"high-latitude"	)
	OR CONTAINS(LOWER([result_title]),	"southpole"	)
	OR CONTAINS(LOWER([result_title]),	"atlantic"	)
	OR CONTAINS(LOWER([result_title]),	"barents sea"	)
	OR CONTAINS(LOWER([result_title]),	"greenland sea"	)
	OR CONTAINS(LOWER([result_title]),	"north sea"	)
	OR CONTAINS(LOWER([result_title]),	"norwegian sea"	)
	OR CONTAINS(LOWER([result_title]),	"nordic seas"	)
	OR CONTAINS(LOWER([result_title]),	"skager"	)
	OR CONTAINS(LOWER([result_title]),	"chukchisea"	)
	OR CONTAINS(LOWER([result_title]),	"east siberian sea"	)
	OR CONTAINS(LOWER([result_title]),	"laptev sea"	)
	OR CONTAINS(LOWER([result_title]),	"kara sea"	)
	OR CONTAINS(LOWER([result_title]),	"labroadorsea"	)
	OR CONTAINS(LOWER([result_title]),	"greenland sea"	)
	OR CONTAINS(LOWER([result_title]),	"beaufort sea"	)
	OR CONTAINS(LOWER([result_title]),	"sea of okhotsk"	)

	OR CONTAINS(LOWER([result_title]),	"weddel sea"	)
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
	OR CONTAINS(LOWER([result_title]),	"gulfstream"	)
	OR CONTAINS(LOWER([result_title]),	"polar water"	)
	OR CONTAINS(LOWER([result_title]),	"polar current"	)
	OR CONTAINS(LOWER([result_title]),	"south polar"	))
)		
THEN "SYSEFF"		

ELSEIF		
CONTAINS(LOWER([result_title]),	"glacier"	)
OR CONTAINS(LOWER([result_title]),	"isbre"	)
OR CONTAINS(LOWER([result_title]),	"breen"	)
OR CONTAINS(LOWER([result_title]),	"breer"	)
OR CONTAINS(LOWER([result_title]),	"ice cap"	)
OR CONTAINS(LOWER([result_title]),	"ice-field"	)
OR CONTAINS(LOWER([result_title]),	"ice sheet"	)
OR CONTAINS(LOWER([result_title]),	"ice shelves"	)
OR CONTAINS(LOWER([result_title]),	"iceshelf"	)
OR CONTAINS(LOWER([result_title]),	"sea-ice"	)
OR CONTAINS(LOWER([result_title]),	"sea ice"	)
OR CONTAINS(LOWER([result_title]),	"pack ice"	)
OR CONTAINS(LOWER([result_title]),	"polynya"	)
OR CONTAINS(LOWER([result_title]),	"ice variability"	)
OR CONTAINS(LOWER([result_title]),	"ice cover"	)
OR CONTAINS(LOWER([result_title]),	"ice retreat"	)
OR CONTAINS(LOWER([result_title]),	"ice exten"	)
OR CONTAINS(LOWER([result_title]),	"ice thickness"	)
OR CONTAINS(LOWER([result_title]),	"nilas"	)
OR CONTAINS(LOWER([result_title]),	"ice chart"	)
OR CONTAINS(LOWER([result_title]),	"ice-berg"	)
OR CONTAINS(LOWER([result_title]),	"ice berg"	)
OR CONTAINS(LOWER([result_title]),	"iceberg"	)
OR CONTAINS(LOWER([result_title]),	"slush"	)
OR CONTAINS(LOWER([result_title]),	"pancake ice"	)
OR CONTAINS(LOWER([result_title]),	"pack ice"	)
OR CONTAINS(LOWER([result_title]),	"iceridge"	)
OR CONTAINS(LOWER([result_title]),	"grease ice"	)
OR CONTAINS(LOWER([result_title]),	"havis"	)
OR CONTAINS(LOWER([result_title]),	"marginal ice zone"	)
OR CONTAINS(LOWER([result_title]),	"multi-year ice"	)
OR CONTAINS(LOWER([result_title]),	"first-year ice"	)
OR (REGEXP_MATCH([result_title], "\bwarm") AND CONTAINS(LOWER([result_title]), "arctic" ))
OR CONTAINS(LOWER([result_title]),	"arctic amplification"	)
THEN "SYSEFF"		

ELSEIF		
(		
	CONTAINS(LOWER([result_title]),	"anthropo"	)
	AND		
	(CONTAINS(LOWER([result_title]),	"heating"	)
	OR CONTAINS(LOWER([result_title]),	"warming"	)
	OR CONTAINS(LOWER([result_title]),	"forcing"	)
	OR CONTAINS(LOWER([result_title]),	"change"	)
	OR CONTAINS(LOWER([result_title]),	"driv"	)
	OR CONTAINS(LOWER([result_title]),	"feedback"	))
)		
OR CONTAINS(LOWER([result_title]),	"climatology"	)
OR CONTAINS(LOWER([result_title]),	"climate scien"	)
OR CONTAINS(LOWER([result_title]),	"earth system"	)
OR CONTAINS(LOWER([result_title]),	"noresm"	)
OR CONTAINS(LOWER([result_title]),	"echam5"	)
OR CONTAINS(LOWER([result_title]),	"cmip"	)
OR CONTAINS(LOWER([result_title]),	"gcm"	)
OR CONTAINS(LOWER([result_title]),	"aogsm"	)
OR CONTAINS(LOWER([result_title]),	"ukmo-had"	)
OR CONTAINS(LOWER([result_title]),	"gfdl-cm"	)
OR CONTAINS(LOWER([result_title]),	"giss-eh"	)
OR CONTAINS(LOWER([result_title]),	"giss-er"	)
OR CONTAINS(LOWER([result_title]),	"inm-cm"	)

OR CONTAINS(LOWER([result_title]),	"ipsl-cm"	)
OR CONTAINS(LOWER([result_title]),	"miroc3"	)
OR CONTAINS(LOWER([result_title]),	"bcc-cm"	)
OR CONTAINS(LOWER([result_title]),	"bccr-bcm"	)
OR CONTAINS(LOWER([result_title]),	"ccsm3"	)
OR CONTAINS(LOWER([result_title]),	"cgcm3"	)
OR CONTAINS(LOWER([result_title]),	"cnrm-cm3"	)
OR CONTAINS(LOWER([result_title]),	"csiro"	)

OR CONTAINS(LOWER([result_title]),	"cloud forcing"	)
OR CONTAINS(LOWER([result_title]),	"cloud interaction"	)
OR CONTAINS(LOWER([result_title]),	"aerosol effect"	)
OR CONTAINS(LOWER([result_title]),	"black carbon"	)
OR CONTAINS(LOWER([result_title]),	"albedo change")
THEN "SYSEFF"		

ELSEIF	
CONTAINS(LOWER([result_title]),	"tipping point"	)
OR CONTAINS(LOWER([result_title]),	"heat wave"	)
OR CONTAINS(LOWER([result_title]),	"heatwave"	)
OR	
(		
	(CONTAINS(LOWER([result_title]),	"extreme"	)
	OR CONTAINS(LOWER([result_title]),	"chang"	)
	OR CONTAINS(LOWER([result_title]),	"rise"	)
	OR CONTAINS(LOWER([result_title]),	"record"	)
	OR CONTAINS(LOWER([result_title]),	"global"	)
	OR CONTAINS(LOWER([result_title]),	"increas"	)
	OR CONTAINS(LOWER([result_title]),	"variab"	)
	OR CONTAINS(LOWER([result_title]),	"predict"	)
	)		
	AND
	(CONTAINS(LOWER([result_title]),	"precipitation"	)
	OR CONTAINS(LOWER([result_title]),	"temperature"	)
	OR CONTAINS(LOWER([result_title]),	"drought"	)
	OR CONTAINS(LOWER([result_title]),	"atmospher"	)
	OR CONTAINS(LOWER([result_title]),	"ocean"	)
	OR CONTAINS(LOWER([result_title]),	"flood"	)
	OR CONTAINS(LOWER([result_title]),	"weather"	))
)		
OR CONTAINS(LOWER([result_title]),	"varmebølg"	)
OR CONTAINS(LOWER([result_title]),	"hetebølg"	)
OR	
(		
	(CONTAINS(LOWER([result_title]),	"ekstrem"	)
	OR CONTAINS(LOWER([result_title]),	"klimaendr"	)
	)		
	AND
	(CONTAINS(LOWER([result_title]),	"vær"	)
	OR CONTAINS(LOWER([result_title]),	"regn"	)
	OR CONTAINS(LOWER([result_title]),	"nedbør"	)
	OR CONTAINS(LOWER([result_title]),	"temperatur"	)
	OR REGEXP_MATCH([result_title],	"\bflom"	))
)	
OR CONTAINS(LOWER([result_title]),	"havforsur"	)	
OR
(		
	(REGEXP_MATCH([result_title], "\bsea\b" )
	OR CONTAINS(LOWER([result_title]),	"ocean"	))		
	AND		
	(CONTAINS(LOWER([result_title]),	"level"	)
	OR CONTAINS(LOWER([result_title]),	"heat"	)
	OR CONTAINS(LOWER([result_title]),	"acidification"	)
	OR CONTAINS(LOWER([result_title]),	"co2"	)
	OR CONTAINS(LOWER([result_title]),	"carbon"	)
	OR CONTAINS(LOWER([result_title]),	"predict"	)
	OR CONTAINS(LOWER([result_title]),	"variabil"	))
)	
THEN "SYSEFF"		

ELSEIF		
(		
	(
	(CONTAINS(LOWER([Result Title]),"climat") AND CONTAINS(LOWER([Result Title]), "chang"))
	OR (CONTAINS(LOWER([Result Title]),"climat") AND CONTAINS(LOWER([Result Title]), "warm"))
	OR (CONTAINS(LOWER([Result Title]),"ocean") AND CONTAINS(LOWER([Result Title]),	"warm"))
	OR CONTAINS(LOWER([result_title]),	"global warming"	)
	)		
AND		
	(CONTAINS(LOWER([result_title]),	"disaster"	)
	OR CONTAINS(LOWER([result_title]),	"collapse"	)
	OR CONTAINS(LOWER([result_title]),	"diversity"	)
	OR CONTAINS(LOWER([result_title]),	"habitat"	)
	OR CONTAINS(LOWER([result_title]),	"extinction"	)
	OR CONTAINS(LOWER([result_title]),	"species"	)
	OR CONTAINS(LOWER([result_title]),	"population"	)
	OR CONTAINS(LOWER([result_title]),	"response"	)
	OR CONTAINS(LOWER([result_title]),	"emission"	)
	OR CONTAINS(LOWER([result_title]),	"consequence"	)
	OR CONTAINS(LOWER([result_title]),	"crisis"	)
	OR CONTAINS(LOWER([result_title]),	"crises"	)

	OR CONTAINS(LOWER([result_title]),	"hazards"	)
	OR CONTAINS(LOWER([result_title]),	"impact"	)
	OR CONTAINS(LOWER([result_title]),	"footprint"	)
	OR CONTAINS(LOWER([result_title]),	"assess"	)
	OR CONTAINS(LOWER([result_title]),	"risk"	)
	OR CONTAINS(LOWER([result_title]),	"econom"	)
	OR CONTAINS(LOWER([result_title]),	"quota"	)
	OR REGEXP_MATCH([result_title],	"\bwar"	)
	OR CONTAINS(LOWER([result_title]),	"conflict"	)
	OR CONTAINS(LOWER([result_title]),	"affect"	)
	OR CONTAINS(LOWER([result_title]),	"effect"	)
	OR CONTAINS(LOWER([result_title]),	"influence"	)
	OR CONTAINS(LOWER([result_title]),	"scenario"	)
	OR REGEXP_MATCH([result_title],	"\bscien"	)
	OR CONTAINS(LOWER([result_title]),	"infrastructure"	)
	OR REGEXP_MATCH([result_title],	"\bship"	)

	OR CONTAINS(LOWER([result_title]),	"forest"	)
	OR CONTAINS(LOWER([result_title]),	"resources"	)
	OR CONTAINS(LOWER([result_title]),	"health"	)
	OR CONTAINS(LOWER([result_title]),	"disease"	)
	OR CONTAINS(LOWER([result_title]),	"sick"	)
	OR CONTAINS(LOWER([result_title]),	"death"	)
	OR CONTAINS(LOWER([result_title]),	"hunger"	)
	OR CONTAINS(LOWER([result_title]),	"hungry"	)

	OR CONTAINS(LOWER([result_title]),	"migrat"	)
	OR CONTAINS(LOWER([result_title]),	"migrant"	)
	OR CONTAINS(LOWER([result_title]),	"refugee"	)
	OR CONTAINS(LOWER([result_title]),	"societ"	)
	OR CONTAINS(LOWER([result_title]),	"communit"	)
	OR CONTAINS(LOWER([result_title]),	"agricultur"	)
	OR CONTAINS(LOWER([result_title]),	"aquacultur"	)
	OR CONTAINS(LOWER([result_title]),	"landuse"	)
	OR CONTAINS(LOWER([result_title]),	"land use"	)
	OR CONTAINS(LOWER([result_title]),	"land area cover"	)
	OR CONTAINS(LOWER([result_title]),	"soil"	)
	OR CONTAINS(LOWER([result_title]),	"food"	))
)		
THEN "SYSEFF"		

ELSEIF
(
	(CONTAINS(LOWER([result_title]),	"ozone"	)
	OR CONTAINS(LOWER([result_title]),	"carbon"	)
	OR CONTAINS(LOWER([result_title]),	"greenhouse"	)
	OR CONTAINS(LOWER([result_title]),	"co2"	)
	)
	AND
	(CONTAINS(LOWER([result_title]),	"scenario"	)
	OR CONTAINS(LOWER([result_title]),	"emission"	)
	OR CONTAINS(LOWER([result_title]),	"effect"	))
)
OR		
(		
	CONTAINS(LOWER([result_title]),	"permafrost"	)
	AND
	(CONTAINS(LOWER([result_title]),	"melt"	)
	OR CONTAINS(LOWER([result_title]),	"methan"	)
	OR CONTAINS(LOWER([result_title]),	"production"	)
	OR CONTAINS(LOWER([result_title]),	"feedback"	))
)		
THEN "SYSEFF"

ELSEIF		
CONTAINS(LOWER([result_title]),	"human footprint"	)
OR CONTAINS(LOWER([result_title]),	"climate footprint"	)
OR CONTAINS(LOWER([result_title]),	"global footprint"	)
OR CONTAINS(LOWER([result_title]),	"greenhouse effect"	)
THEN "SYSEFF"		
ELSE 'non'
END
```

### Journal search

```py =
IF CONTAINS(LOWER([journal]),	"climate change ecology"	)
OR CONTAINS(LOWER([journal]),	"climate system"	)
THEN "SYSEFF"
ELSE 'non'
END
```


## Climate adaptation (klimatilpasning)

### Title search

```py =
IF		
(		
	(		
		(CONTAINS(LOWER([result_title]), "climat") AND CONTAINS(LOWER([result_title]), "chang"))
		OR(CONTAINS(LOWER([result_title]), "climat") AND CONTAINS(LOWER([result_title]), "warm")		
		OR (CONTAINS(LOWER([result_title]), "global") AND CONTAINS(LOWER([result_title]), "warm"))
	)		
AND		
	(CONTAINS(LOWER([result_title]),	"action"	)
	OR CONTAINS(LOWER([result_title]),	"preparedness"	)
	OR CONTAINS(LOWER([result_title]),	"anticipat"	)
	OR CONTAINS(LOWER([result_title]),	"prevent"	)	
	OR CONTAINS(LOWER([result_title]),	"minimi"	)
	OR CONTAINS(LOWER([result_title]),	"plan"	)
	OR CONTAINS(LOWER([result_title]),	"resilie"	)
	OR CONTAINS(LOWER([result_title]),	"adapt"	)
	OR CONTAINS(LOWER([result_title]),	"mitiga"	)
	OR CONTAINS(LOWER([result_title]),	"manage"	)
	OR CONTAINS(LOWER([result_title]),	"governance"	)
	OR CONTAINS(LOWER([result_title]),	"leadership"	)
	OR CONTAINS(LOWER([result_title]),	"politic"	)
	OR CONTAINS(LOWER([result_title]),	"polic"	)
	OR CONTAINS(LOWER([result_title]),	"regulation"	)
	OR REGEXP_MATCH([result_title],	"\blaw"	)
	OR CONTAINS(LOWER([result_title]),	"penalty"	)
	OR CONTAINS(LOWER([result_title]),	"litigation"	)
	OR CONTAINS(LOWER([result_title]),	"justice"	)
	OR CONTAINS(LOWER([result_title]),	"risk"	)
	OR CONTAINS(LOWER([result_title]),	"challenge"	)
	OR CONTAINS(LOWER([result_title]),	"negotiation"	)
	OR CONTAINS(LOWER([result_title]),	"solution"	)

	OR CONTAINS(LOWER([result_title]),	"lifestyle"	)
	OR CONTAINS(LOWER([result_title]),	"adjust"	)
	OR CONTAINS(LOWER([result_title]),	"transition"	)
	OR CONTAINS(LOWER([result_title]),	"sustainability"	)
	OR CONTAINS(LOWER([result_title]),	"service"	)
	OR CONTAINS(LOWER([result_title]),	"consumer"	)
	OR CONTAINS(LOWER([result_title]),	"concept"	)
	OR CONTAINS(LOWER([result_title]),	"post normal"	)
	OR CONTAINS(LOWER([result_title]),	"post-normal"	)
	OR CONTAINS(LOWER([result_title]),	"information"	)
	OR CONTAINS(LOWER([result_title]),	"ethic"	)
	OR CONTAINS(LOWER([result_title]),	"perception"	)
	OR CONTAINS(LOWER([result_title]),	"engagement"	)
	OR CONTAINS(LOWER([result_title]),	"initiat"	)
	OR CONTAINS(LOWER([result_title]),	"debate"	)
	OR CONTAINS(LOWER([result_title]),	"stories"	)
	OR CONTAINS(LOWER([result_title]),	"discours"	)
	OR CONTAINS(LOWER([result_title]),	"discurs"	)
	OR CONTAINS(LOWER([result_title]),	"narrative"	)
	OR CONTAINS(LOWER([result_title]),	"acceptance"	)
	OR CONTAINS(LOWER([result_title]),	"worries"	)
	OR CONTAINS(LOWER([result_title]),	"fear"	)
	OR REGEXP_MATCH([result_title],	"\bbelie"	))
)		
THEN "TILPASNING"

ELSEIF
(
	CONTAINS(LOWER([result_title]),	"climat" )
	AND			
	(CONTAINS(LOWER([result_title]),	"service"	)
	OR CONTAINS(LOWER([result_title]),	"negotioation"	)
	OR CONTAINS(LOWER([result_title]),	"skepsis"	)
	OR CONTAINS(LOWER([result_title]),	"skeptic"	)
	OR CONTAINS(LOWER([result_title]),	"consensus"	)
	OR CONTAINS(LOWER([result_title]),	"policy"	)
	OR CONTAINS(LOWER([result_title]),	"target"	)
	OR CONTAINS(LOWER([result_title]),	"goal"	)
	OR CONTAINS(LOWER([result_title]),	"policies"	)
	OR CONTAINS(LOWER([result_title]),	"ethics"	))
)	
THEN "TILPASNING"

ELSEIF
	CONTAINS(LOWER([Result Title]),	"climate perspective"	)
	OR CONTAINS(LOWER([Result Title]),	"climate perception"	)
	OR CONTAINS(LOWER([Result Title]),	"climate concern"	)
	OR CONTAINS(LOWER([Result Title]),	"climate knowledge"	)
	OR CONTAINS(LOWER([Result Title]),	"climate adapt"	)
	OR CONTAINS(LOWER([Result Title]),	"climate resilien"	)
	OR CONTAINS(LOWER([Result Title]),	"climate mitigat"	)
	OR CONTAINS(LOWER([Result Title]),	"climate action"	)
	OR CONTAINS(LOWER([Result Title]),	"climate planning"	)
	OR CONTAINS(LOWER([Result Title]),	"climate financ")
	OR CONTAINS(LOWER([Result Title]),	"climate fund")
	OR CONTAINS(LOWER([Result Title]),	"climate law")
	OR CONTAINS(LOWER([Result Title]),	"climate polic")
	OR CONTAINS(LOWER([Result Title]),	"climate justice")
	OR CONTAINS(LOWER([Result Title]),	"climate crisis")
THEN "TILPASNING"

ELSEIF			
(			
	(CONTAINS(LOWER([result_title]),	"heat wave"	)
	OR CONTAINS(LOWER([result_title]),	"tipping point"	)
	OR CONTAINS(LOWER([result_title]),	"sea level"	)
	OR CONTAINS(LOWER([result_title]),	"temperature"	)
	OR CONTAINS(LOWER([result_title]),	"drought"	)
	OR CONTAINS(LOWER([result_title]),	"flood"	)
	OR CONTAINS(LOWER([result_title]),	"extreme weather"	)
	OR CONTAINS(LOWER([result_title]),	"extreme precipita"	)
	)			
	AND			
	(CONTAINS(LOWER([result_title]),	"adapt"	)
	OR CONTAINS(LOWER([result_title]),	"mitiga"	)
	OR CONTAINS(LOWER([result_title]),	"prevent"	)
	OR CONTAINS(LOWER([result_title]),	"resilie"	)
	OR CONTAINS(LOWER([result_title]),	"plan"	)
	OR CONTAINS(LOWER([result_title]),	"governance"	)
	OR CONTAINS(LOWER([result_title]),	"polic"	))
)			
THEN "TILPASNING"

ELSEIF			
(
	CONTAINS(LOWER([result_title]),	"klima"	)
	AND			
	(CONTAINS(LOWER([result_title]),	"holdning"	)
	OR CONTAINS(LOWER([result_title]),	"omstilling"	)
	OR CONTAINS(LOWER([result_title]),	"tilpasning"	)
	OR CONTAINS(LOWER([result_title]),	"tilpass"	)
	OR CONTAINS(LOWER([result_title]),	"tiltak"	)
	OR CONTAINS(LOWER([result_title]),	"avtaler"	)
	OR CONTAINS(LOWER([result_title]),	"rammeverk"	)
	OR CONTAINS(LOWER([result_title]),	"midler"	)
	OR CONTAINS(LOWER([result_title]),	"livstil"	)
	OR CONTAINS(LOWER([result_title]),	"opprør"	)
	OR CONTAINS(LOWER([result_title]),	"politik"	)
	OR CONTAINS(LOWER([result_title]),	"lovverk"	)
	OR REGEXP_MATCH([result_title],	"\brett"	)
	OR CONTAINS(LOWER([result_title]),	"følel"	)
	OR CONTAINS(LOWER([result_title]),	"spørsmål"	)
	OR CONTAINS(LOWER([result_title]),	"skepsis"	)
	OR CONTAINS(LOWER([result_title]),	"paradoks"	)
	OR CONTAINS(LOWER([result_title]),	"perspektiv"	)
	OR CONTAINS(LOWER([result_title]),	"bistand"	)
	OR CONTAINS(LOWER([result_title]),	"kultur"	)
	OR CONTAINS(LOWER([result_title]),	"vennlig"	)
	OR CONTAINS(LOWER([result_title]),	"krise"	)
	OR CONTAINS(LOWER([result_title]),	"tiltak"	)
	OR CONTAINS(LOWER([result_title]),	"debatt"	)
	OR CONTAINS(LOWER([result_title]),	"forhandlinger"	)
	OR CONTAINS(LOWER([result_title]),	"moral"	)
	OR CONTAINS(LOWER([result_title]),	"etikk"	)
	OR CONTAINS(LOWER([result_title]),	"fremtid"	)
	OR CONTAINS(LOWER([result_title]),	"endringskapasitet"	)
	OR CONTAINS(LOWER([result_title]),	"narrativ"	)
	OR CONTAINS(LOWER([result_title]),	"engasjement"	)
	OR CONTAINS(LOWER([result_title]),	"bevisst"	)
	OR CONTAINS(LOWER([result_title]),	"innovasjon"	)
	OR CONTAINS(LOWER([result_title]),	"fortelling"	)
	OR CONTAINS(LOWER([result_title]),	"aksjon"	))
)			
OR CONTAINS(LOWER([result_title]),	"klimalov"	)
OR CONTAINS(LOWER([result_title]),	"klimamål"	)
THEN "TILPASNING"		

ELSEIF
	CONTAINS([Result Title],	"SDG13"	)
	OR CONTAINS([Result Title],	"SDG 13"	)
THEN "TILPASNING"
			
ELSE "non"
END
```

### Journal search

```py =
IF 		
CONTAINS(LOWER([journal]),	"climate and development"	)
OR CONTAINS(LOWER([journal]),	"climate change mitigation"	)
OR CONTAINS(LOWER([journal]),	"climate change adaptation"	)
OR CONTAINS(LOWER([journal]),	"climate change economics"	)
OR CONTAINS(LOWER([journal]),	"economics of disasters and climate change"	)
OR CONTAINS(LOWER([journal]),	"economics of climate change"	)
OR CONTAINS(LOWER([journal]),	"climate change management"	)
OR CONTAINS(LOWER([journal]),	"climate policy"	)
OR CONTAINS(LOWER([journal]),	"weather, climate and society climate policy"	)
OR CONTAINS(LOWER([journal]),	"climate services"	)
OR CONTAINS(LOWER([journal]),	"journal of climate change strategies"	)
OR CONTAINS(LOWER([journal]),	"urban studies"	)
OR CONTAINS(LOWER([journal]),	"urban climate"	)
OR CONTAINS(LOWER([journal]),	"global transition"	)
OR CONTAINS(LOWER([journal]),	"journal of water and climate change"	)
OR CONTAINS(LOWER([journal]),	"sustainability"	)
OR CONTAINS(LOWER([journal]),	"current climate change reports"	)

OR CONTAINS(LOWER([journal]),	"carbon and climate law review"	)
OR
(
	(CONTAINS(LOWER([journal]),	"carbon"	)
	OR CONTAINS(LOWER([journal]),	"climate"	))
	AND
	CONTAINS(LOWER([journal]),	"law"	)
)

THEN "TILPASNING"		
ELSE 'non'		
END
```

## Climate adapatation AND energy transitions (klimatipasning og energiomstilling)

In practice it is not possible to completely/reliably separate these two sub-topics, so the strings under count for both.  

### Title search

```py =
IF
CONTAINS(LOWER([result_title]),	"klimaomstilling")
OR CONTAINS(LOWER([result_title]),	"green economy")
OR CONTAINS(LOWER([result_title]),	"grønt skifte")
OR CONTAINS(LOWER([result_title]),	"grønne skift")
OR CONTAINS(LOWER([result_title]),	"grønn omstilling")
OR CONTAINS(LOWER([result_title]),	"sirkulærøkomoni"	)
OR CONTAINS(LOWER([result_title]),	"circular economy"	)
THEN "TILPASENERGI"		

ELSEIF		
CONTAINS(LOWER([result_title]),	"green climate"	)
OR CONTAINS(LOWER([result_title]),	"climate city")
OR CONTAINS(LOWER([result_title]),	"green capital")
OR CONTAINS(LOWER([result_title]),	"smart city")
OR CONTAINS(LOWER([result_title]),	"smart cities")
OR CONTAINS(LOWER([result_title]),	"sustainable city")
OR CONTAINS(LOWER([result_title]),	"sustainable cities")
OR CONTAINS(LOWER([result_title]),	"urban sustainablity")
OR CONTAINS(LOWER([result_title]),	"urban transformation")
OR CONTAINS(LOWER([result_title]),	"climate-smart")
OR CONTAINS(LOWER([result_title]),	"climate smart")
OR
(
	(CONTAINS(LOWER([result_title]),	"green")
	OR CONTAINS(LOWER([result_title]),	"grønn")
	OR REGEXP_MATCH([result_title], "\bcarbon\b")
	OR REGEXP_MATCH([result_title], "\bkarbon\b")
	OR REGEXP_MATCH([result_title], "lavkarbon\b")
	OR CONTAINS(LOWER([result_title]),	"emission")
	OR CONTAINS(LOWER([result_title]),	"utslipp")
	OR CONTAINS(LOWER([result_title]),	"electric")
	OR CONTAINS(LOWER([result_title]),	"elektrisk")
	OR CONTAINS(LOWER([result_title]),	"hybrid")
	OR CONTAINS(LOWER([result_title]),	"clean")
	OR CONTAINS(LOWER([result_title]),	"renewable")
	OR CONTAINS(LOWER([result_title]),	"fornybar"))
	AND
	(REGEXP_MATCH([result_title], "\bcity")
	OR CONTAINS(LOWER([result_title]), "cities")
	OR CONTAINS(LOWER([result_title]), "byer")

	OR CONTAINS(LOWER([result_title]), "shipping")
	OR CONTAINS(LOWER([result_title]), "skipsfart")
	OR CONTAINS(LOWER([result_title]), "ferries")
	OR CONTAINS(LOWER([result_title]), "transport")
	OR CONTAINS(LOWER([result_title]), "vehicle")
	OR CONTAINS(LOWER([result_title]), "aviation")

	OR CONTAINS(LOWER([result_title]),	"infrastructure"	)
	OR CONTAINS(LOWER([result_title]),	"supply"	)
	OR CONTAINS(LOWER([result_title]),	"investment"	)
	OR CONTAINS(LOWER([result_title]),	"incentive"	)
	OR CONTAINS(LOWER([result_title]),	"certificate"	)
	)
)
OR CONTAINS(LOWER([result_title]),	"electric car")
OR REGEXP_MATCH([result_title], "\bel-bil")
OR REGEXP_MATCH([result_title], "\belbil")
OR
(
	(CONTAINS(LOWER([result_title]),	"green")
	OR CONTAINS(LOWER([result_title]),	"grønn")
	OR CONTAINS(LOWER([result_title]),	"decarbon")
	OR REGEXP_MATCH([result_title], "low carbon\b")
	OR REGEXP_MATCH([result_title], "low-carbon\b")
	OR REGEXP_MATCH([result_title], "\bkarbon\b")
	OR REGEXP_MATCH([result_title], "lavkarbon\b")
	OR CONTAINS(LOWER([result_title]),	"emission")
	OR CONTAINS(LOWER([result_title]),	"utslipp")
	OR CONTAINS(LOWER([result_title]),	"clean")
	OR CONTAINS(LOWER([result_title]),	"renewable")
	OR CONTAINS(LOWER([result_title]),	"fornybar"))
	AND
	(CONTAINS(LOWER([result_title]),	"design"	)
	OR CONTAINS(LOWER([result_title]),	"process"	)
	OR CONTAINS(LOWER([result_title]),	"production"	)
	OR CONTAINS(LOWER([result_title]),	"industri"	)
	OR CONTAINS(LOWER([result_title]),	"manufactur"	)
	OR CONTAINS(LOWER([result_title]),	"waste"	)
	OR CONTAINS(LOWER([result_title]),	"disposal"	)
	OR CONTAINS(LOWER([result_title]),	"area use"	)
	OR CONTAINS(LOWER([result_title]),	"technolog"	)
	)
)
THEN "TILPASENERGI"		

ELSEIF					
CONTAINS(LOWER([result_title]),	"kyoto protocol")
OR CONTAINS(LOWER([result_title]),	"cop2")
OR
(
	(CONTAINS(LOWER([result_title]),	"climat"	)
	OR CONTAINS(LOWER([result_title]),	"paris"	))
	AND 			
	(CONTAINS(LOWER([result_title]),	"agreement"	)
	OR CONTAINS(LOWER([result_title]),	"target"	)
	OR CONTAINS(LOWER([result_title]),	"treaty"	))
)			
THEN "TILPASENERGI"

ELSEIF			
CONTAINS(LOWER([result_title]),	"klimautslipp"	)
OR CONTAINS(LOWER([result_title]),	"klimagass"	)
OR CONTAINS(LOWER([result_title]), "karbonfangst")
OR CONTAINS(LOWER([result_title]), "co2-fangst")
OR CONTAINS(LOWER([result_title]), "co2-lagring")

OR REGEXP_MATCH([result_title],	"\bCCS\b"	)
OR CONTAINS(([result_title]),	"CCUS"	)
OR		
(		
	(CONTAINS(LOWER([result_title]),	"co2"	)
	OR CONTAINS(LOWER([result_title]),	"co 2"	)
	OR CONTAINS(LOWER([result_title]),	"greenhouse gas"	)
	OR CONTAINS([result_title],	"GHG"	)
	OR CONTAINS(LOWER([result_title]),	"methane"	)
	OR CONTAINS(LOWER([result_title]),	"n2o"	)
	OR CONTAINS(LOWER([result_title]),	"nitrous oxide"	)
	OR CONTAINS(LOWER([result_title]),	"ozone"	)
	OR CONTAINS(LOWER([result_title]),	"carbon"	))
	AND		
	(CONTAINS(LOWER([result_title]),	"emission")
	OR CONTAINS(LOWER([result_title]),	"footprint"	)
	OR CONTAINS(LOWER([result_title]),	"sink"	)
	OR CONTAINS(LOWER([result_title]),	"capture"	)
	OR CONTAINS(LOWER([result_title]),	"sequestration"	)
	OR CONTAINS(LOWER([result_title]),	"storage"	)
	OR CONTAINS(LOWER([result_title]),	"remov"	)
	OR CONTAINS(LOWER([result_title]),	"stabile"	)
	OR CONTAINS(LOWER([result_title]),	"trap"	)
	OR CONTAINS(LOWER([result_title]),	"budget"	)
	OR CONTAINS(LOWER([result_title]),	"trade"	)
	OR CONTAINS(LOWER([result_title]),	"doubling"	))
)		
OR
(
	(CONTAINS(LOWER([result_title]),	"carbon"	)
	OR CONTAINS(LOWER([result_title]),	"greenhouse gas"	)
	OR CONTAINS([result_title],	"GHG"	)
	OR CONTAINS(LOWER([result_title]),	"co2 "	))
	AND		
	(CONTAINS(LOWER([result_title]),	"pric"	)
	OR CONTAINS(LOWER([result_title]),	"cost"	)
	OR CONTAINS(LOWER([result_title]),	"trading"	)
	OR CONTAINS(LOWER([result_title]),	"trade"	))
)	

OR CONTAINS(LOWER([result_title]),	"carbon cut"	)
OR CONTAINS(LOWER([result_title]),	"zero emission"	)
OR CONTAINS(LOWER([result_title]),	"null utslipp"	)
OR CONTAINS(LOWER([result_title]),	"nullutslipp"	)
OR (CONTAINS(LOWER([result_title]), "climate") AND CONTAINS(LOWER([result_title]), "technology"))

THEN "TILPASENERGI"
ELSE 'non'
END
```	

### Journal search

```py =
IF CONTAINS(LOWER([journal]),	"greenhouse gas control"	)		
OR CONTAINS(LOWER([journal]),	"carbon capture"	)
OR CONTAINS(LOWER([journal]),	"Sustainable Energy Technologies and Assessments"	)
OR CONTAINS(LOWER([journal]),	"journal of cleaner production"	)
OR CONTAINS(LOWER([journal]),	"sustainable chemistry and engineering"	)
THEN "TILPASENERGI"
ELSE 'non'
END
```

## Energy transitions (Energiomstilling)

### Title search

```py =
IF 	
CONTAINS(LOWER([result_title]),	"energiomstilling"	)
OR CONTAINS(LOWER([result_title]),	"energy transition")
OR
(
	(CONTAINS(LOWER([result_title]),	"energy sector"	)
	OR CONTAINS(LOWER([result_title]),	"energy system"	))
	AND		
 	(CONTAINS(LOWER([result_title]),	"transformation"	)
	OR CONTAINS(LOWER([result_title]),	"future"	)
	OR CONTAINS(LOWER([result_title]),	"transition"	)
	OR CONTAINS(LOWER([result_title]),	"green"	)
	OR CONTAINS(LOWER([result_title]),	"sustainab"	))
)		
OR CONTAINS(LOWER([result_title]),	"energy mix"	)
OR CONTAINS(LOWER([result_title]),	"energy ratio"	)
OR CONTAINS(LOWER([result_title]),	"energy management"	)
OR CONTAINS(LOWER([result_title]),	"energy planning"	)
OR CONTAINS(LOWER([result_title]),	"energy strateg"	)
OR CONTAINS(LOWER([result_title]),	"energy market"	)
OR CONTAINS(LOWER([result_title]),	"electricity market"	)
OR CONTAINS(LOWER([result_title]),	"energy payback time"	)
OR CONTAINS(LOWER([result_title]),	"energy cost"	)
OR CONTAINS(LOWER([result_title]),	"climate and energy solution"	)

OR CONTAINS(LOWER([result_title]),	"energy policy"	)
OR CONTAINS(LOWER([result_title]),	"energy law"	)
OR CONTAINS(LOWER([result_title]),	"energy poverty"	)
OR CONTAINS(LOWER([result_title]),	"fuel poverty"	)
OR CONTAINS(LOWER([result_title]),	"energy justice"	)
OR CONTAINS(LOWER([result_title]),	"energy security"	)
OR CONTAINS(LOWER([result_title]),	"energy vulnerab"	)
OR CONTAINS(LOWER([result_title]),	"energy future"	)

OR CONTAINS(LOWER([result_title]),	"energy infrastructure"	)
OR CONTAINS(LOWER([result_title]),	"national energy"	)
OR CONTAINS(LOWER([result_title]),	"local energy"	)
OR CONTAINS(LOWER([result_title]),	"community energy"	)
OR CONTAINS(LOWER([result_title]),	"energy coop"	)
OR CONTAINS(LOWER([result_title]),	"energy co-op"	)
OR CONTAINS(LOWER([result_title]),	"microgrid"	)
OR
(
	(CONTAINS(LOWER([result_title]),	"sustainable"	)
	OR CONTAINS(LOWER([result_title]),	"bærekraft"	)
	OR CONTAINS(LOWER([result_title]),	"renewable"	)
	OR CONTAINS(LOWER([result_title]),	"fornybar"	)
	OR CONTAINS(LOWER([result_title]),	"green"	))
	AND		
 	(CONTAINS(LOWER([result_title]),	"batter"	)
	OR CONTAINS(LOWER([result_title]),	"grid"	)
	OR CONTAINS(LOWER([result_title]),	"electricity"	)
	OR CONTAINS(LOWER([result_title]),	"elektrisitet"	)
	OR CONTAINS(LOWER([result_title]),	"fuel cell"	))
)	

OR CONTAINS(LOWER([result_title]),	"energisystem"	)
OR CONTAINS(LOWER([result_title]),	"energitiltak"	)
OR CONTAINS(LOWER([result_title]),	"energistrateg"	)
OR CONTAINS(LOWER([result_title]),	"energimarked"	)
OR CONTAINS(LOWER([result_title]),	"energiinfrastruk"	)
OR CONTAINS(LOWER([result_title]),	"energipoli"	)
OR CONTAINS(LOWER([result_title]),	"energirett"	)
THEN "ENERGI"

ELSEIF
CONTAINS(LOWER([result_title]), "energy efficien")
OR CONTAINS(LOWER([result_title]), "energieffektiv")
OR CONTAINS(LOWER([result_title]), "energy saving")
OR CONTAINS(LOWER([result_title]), "energisparing")
OR CONTAINS(LOWER([result_title]), "energy consumption")
OR CONTAINS(LOWER([result_title]), "energiforbruk")
OR CONTAINS(LOWER([result_title]), "energy suffici")
THEN "ENERGI"	

ELSEIF
(
	(CONTAINS(LOWER([result_title]),	"renewable"	)
	OR CONTAINS(LOWER([result_title]),	"sustainable"	)
	OR CONTAINS(LOWER([result_title]),	"clean"	)
	OR CONTAINS(LOWER([result_title]),	"modern"	)
	OR CONTAINS(LOWER([result_title]),	"green"	)
	OR CONTAINS(LOWER([result_title]),	"alternative"	))
	AND		
 	(CONTAINS(LOWER([result_title]),	"power"	)
	OR CONTAINS(LOWER([result_title]),	"energy"	)
	OR CONTAINS(LOWER([result_title]),	"fuel"	))
)		
OR CONTAINS(LOWER([result_title]),	"new renewables")
OR CONTAINS(LOWER([result_title]),	"fornybar energi"	)

OR
(
	(CONTAINS(LOWER([result_title]),	"wind farm"	)
	OR CONTAINS(LOWER([result_title]),	"offshore wind"	)
	OR CONTAINS(LOWER([result_title]),	"wind energy"	)
	OR CONTAINS(LOWER([result_title]),	"landvind"	)
	OR CONTAINS(LOWER([result_title]),	"wind power"	)
	OR CONTAINS(LOWER([result_title]),	"wind turbine"	)
	OR CONTAINS(LOWER([result_title]),	"wave power"	)
	OR CONTAINS(LOWER([result_title]),	"havvind"	)
	OR CONTAINS(LOWER([result_title]),	"wind electricity"	)
	OR CONTAINS(LOWER([result_title]),	"wind recource"	))
	AND NOT (		
	CONTAINS(LOWER([result_title]),	"solar wind energy"	)
	OR CONTAINS(LOWER([result_title]),	"astro"	))
)		

OR
(
	CONTAINS(LOWER([result_title]),	"algae" 	)
	AND		
	(CONTAINS(LOWER([result_title]),	" energy"	)
	OR CONTAINS(LOWER([result_title]),	"fuel"	))
)		

OR CONTAINS(LOWER([result_title]),	"tidal energy "	)
OR CONTAINS(LOWER([result_title]),	"tidal electricity"	)
OR CONTAINS(LOWER([result_title]),	"tidal power"	)
OR CONTAINS(LOWER([result_title]),	"stream turbine "	)
OR CONTAINS(LOWER([result_title]),	"tidal turbine"	)
OR CONTAINS(LOWER([result_title]),	"current turbine"	)
OR CONTAINS(LOWER([result_title]),	"hydropower"	)
OR CONTAINS(LOWER([result_title]),	"hydro-power"	)
OR CONTAINS(LOWER([result_title]),	"hydroelectric"	)
OR CONTAINS(LOWER([result_title]), "vannkraft")
OR CONTAINS(LOWER([result_title]), "vasskraft")
OR CONTAINS(LOWER([result_title]), "havenergi")
OR CONTAINS(LOWER([result_title]), "bølgekraft")
OR
(
	(CONTAINS(LOWER([result_title]),	"geothermal"	)
	OR CONTAINS(LOWER([result_title]),	"geotermisk"	))
	AND CONTAINS(LOWER([result_title]),	"energ"	)
)

OR CONTAINS(LOWER([result_title]),	"photovoltaic"	)
OR CONTAINS(LOWER([result_title]),	"solar PV"	)
OR
(
	(CONTAINS(LOWER([result_title]),	"PV"	)
	OR CONTAINS(LOWER([result_title]),	"solar"	))
	AND		
	(CONTAINS(([result_title]),	"kW"	)
	OR CONTAINS(([result_title]),	"MW"	)
	OR CONTAINS(LOWER([result_title]),	"power"	)
	OR CONTAINS(LOWER([result_title]),	"panel"	)
	OR CONTAINS(LOWER([result_title]),	"array"	)
	OR CONTAINS(LOWER([result_title]),	"cell"	))
)		

OR CONTAINS(LOWER([result_title]),	"bio-fuel"	)
OR CONTAINS(LOWER([result_title]),	"bio-energy"	)
OR CONTAINS(LOWER([result_title]),	"bio-diesel"	)
OR CONTAINS(LOWER([result_title]),	"bio-gas"	)
OR CONTAINS(LOWER([result_title]),	"bio-ethanol"	)
OR CONTAINS(LOWER([result_title]),	"biofuel"	)
OR CONTAINS(LOWER([result_title]),	"bioenergy"	)
OR CONTAINS(LOWER([result_title]),	"biodiesel"	)
OR CONTAINS(LOWER([result_title]),	"biogas"	)
OR CONTAINS(LOWER([result_title]),	"bioethanol")
OR CONTAINS(LOWER([result_title]),	"biodrivstoff")
OR CONTAINS(LOWER([result_title]),	"green petrol"	)

OR
(
	(CONTAINS(LOWER([result_title]),	"lignin"	)
	OR CONTAINS(LOWER([result_title]),	"wood"	))
	AND		
	(CONTAINS(LOWER([result_title]),	"fuel"	)
	OR CONTAINS(LOWER([result_title]),	"power"	)
	OR CONTAINS(LOWER([result_title]),	"energy"	))
)		
OR CONTAINS(LOWER([result_title]),	"ammonia energy"	)
OR CONTAINS(LOWER([result_title]),	"ammoniakk energi"	)
OR CONTAINS(LOWER([result_title]),	"green ammonia"	)
OR CONTAINS(LOWER([result_title]),	"grønn ammoniakk"	)
OR CONTAINS(LOWER([result_title]),	"ammoniakk drivstoff"	)
THEN "ENERGI"		

ELSEIF
(
	REGEXP_MATCH([result_title], "\bhydrogen"	)
	AND
	(CONTAINS(LOWER([result_title]),	"fuel"	)
	OR CONTAINS(LOWER([result_title]),	"energy"	)
	OR CONTAINS(LOWER([result_title]),	"cell"	)
	OR CONTAINS(LOWER([result_title]),	"green"	))
)
OR CONTAINS(LOWER([result_title]),	"liquid hydrogen"	)
OR CONTAINS(LOWER([result_title]),	"clean hydrogen"	)
THEN "ENERGI"		

ELSEIF		
(				
	(CONTAINS(LOWER([result_title]),	"phasing out"	)
	OR CONTAINS(LOWER([result_title]),	"phase out"	)
	OR CONTAINS(LOWER([result_title]),	"phased"	)
	OR CONTAINS(LOWER([result_title]),	"faser ut"	)
	OR CONTAINS(LOWER([result_title]),	"slutt"	)
	OR CONTAINS(LOWER([result_title]),	"subsid"	)
	OR CONTAINS(LOWER([result_title]),	"substitu"	)
	OR CONTAINS(LOWER([result_title]),	"transition"	)
	OR CONTAINS(LOWER([result_title]),	"omstilling"	)
	OR CONTAINS(LOWER([result_title]),	"consumption"	)
	OR CONTAINS(LOWER([result_title]),	"forbruk"	)
	)		
	AND		
	(REGEXP_MATCH([result_title], "\boil\b"	)
	OR REGEXP_MATCH([result_title], "\bcoal\b"	)
	OR CONTAINS(LOWER([result_title]),	"fossil fuel"	)
	OR CONTAINS(LOWER([result_title]),	"natural gas"	)
	OR CONTAINS(LOWER([result_title]),	"petroleum"	)
	REGEXP_MATCH([result_title], "\bolje"	)
	OR CONTAINS(LOWER([result_title]),	"fossilt bren"	)
	OR CONTAINS(LOWER([result_title]),	"fossil energi"	))
)
THEN "ENERGI"		

ELSEIF
	CONTAINS([Result Title],	"SDG7"	)
	OR CONTAINS([Result Title],	"SDG 7"	)
THEN "ENERGI"
	
ELSE 'non'		
END
```

### Journal search

```py =
IF CONTAINS(LOWER([journal]),	"renewable energy"	)
OR CONTAINS(LOWER([journal]),	"renewable fuel"	)
OR CONTAINS(LOWER([journal]),	"green energy"	)
OR CONTAINS(LOWER([journal]),	"energy transition"	)
OR CONTAINS(LOWER([journal]),	"sustainable energy"	)
OR CONTAINS(LOWER([journal]),	"energy procedia"	)
OR CONTAINS(LOWER([journal]),	"energy research journal"	)
OR CONTAINS(LOWER([journal]),	"frontiers in energy research "	)

OR CONTAINS(LOWER([journal]),	"biofuel"	)
OR CONTAINS(LOWER([journal]),	"biopower"	)
OR CONTAINS(LOWER([journal]),	"bioresource technology"	)
OR CONTAINS(LOWER([journal]),	"bioenergy"	)
OR CONTAINS(LOWER([journal]),	"bio energy"	)
OR CONTAINS(LOWER([journal]),	"bioresource"	)
OR CONTAINS(LOWER([journal]),	"bio fuel"	)
OR CONTAINS(LOWER([journal]),	"bio power"	)
OR CONTAINS(LOWER([journal]),	"photovoltaic"	)
OR CONTAINS(LOWER([journal]),	"photo voltaic"	)
OR CONTAINS(LOWER([journal]),	"solar energy"	)
OR CONTAINS(LOWER([journal]),	"hydrogen energy"	)
OR CONTAINS(LOWER([journal]),	"wind energy"	)
OR CONTAINS(LOWER([journal]),	"geothermics"	)
OR CONTAINS(LOWER([journal]),	"geothermal energy"	)
OR CONTAINS(LOWER([journal]),	"hydropower"	)

OR CONTAINS(LOWER([journal]),	"energy research & social sciences"	)

OR CONTAINS(LOWER([journal]),	"green technology"	)
OR CONTAINS(LOWER([journal]),	"green battery"	)

THEN "ENERGI"
ELSE 'non'
END
```
