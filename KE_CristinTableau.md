
# KE

String to use in Tableau against "FOR_data_sted_total" ecxtract from DUCT or live

## Combinations

#### TOTAL KE

```Ceylon =
STR([HEALTH total] + "," + [MIGRATION total] + "," + [INEQUALITY total] + "," + [CC in LMCs])
```
#### TOTAL GSU (nocat)

IF(CONTAINS(LOWER([result_title]),	"climat"	)
		
AND		
(		
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
OR CONTAINS(LOWER([result_title]),	"post normal"	)
OR CONTAINS(LOWER([result_title]),	"legacy"	)
OR CONTAINS(LOWER([result_title]),	"target"	)
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
		
		
		
		
OR CONTAINS(LOWER([result_title]),	"coral"	)
OR CONTAINS(LOWER([result_title]),	"reef"	)
OR CONTAINS(LOWER([result_title]),	"ocean"	)
OR CONTAINS(LOWER([result_title]),	"sea"	)
		
		
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
OR CONTAINS(LOWER([result_title]),	"biota"	)
OR CONTAINS(LOWER([result_title]),	"taiga"	)
OR CONTAINS(LOWER([result_title]),	"treeline"	)
OR CONTAINS(LOWER([result_title]),	"biota"	)
OR CONTAINS(LOWER([result_title]),	"alga"	)
OR CONTAINS(LOWER([result_title]),	"diversity"	)
OR CONTAINS(LOWER([result_title]),	"plankton"	)
OR CONTAINS(LOWER([result_title]),	"pollen"	)
OR CONTAINS(LOWER([result_title]),	"vegetation"	)
OR CONTAINS(LOWER([result_title]),	"swamp"	)
))		
THEN "KLIMA"	
	
ELSEIF (		
 CONTAINS(LOWER([result_title]),	"arctic future"	)
OR CONTAINS(LOWER([result_title]),	"future arctic"	)
OR CONTAINS(LOWER([result_title]),	"water mass transformation"	)
OR CONTAINS(LOWER([result_title]),	"water mass formation"	)

OR ((CONTAINS(LOWER([result_title]),	"decadal"	)
OR CONTAINS(LOWER([result_title]),	"seasonal"	))
AND		
(CONTAINS(LOWER([result_title]),	"prediction"	)
OR CONTAINS(LOWER([result_title]),	"variabilit"	)
OR CONTAINS(LOWER([result_title]),	"oscillation"	)
	
))
		
)
THEN "KLIMA"		

ELSEIF		
(CONTAINS(LOWER([result_title]),	"climat"	)
AND		
(		
CONTAINS(LOWER([result_title]),	" arctic"	)
OR CONTAINS(LOWER([result_title]),	" arktisk"	)
OR CONTAINS(LOWER([result_title]),	" antarktisk"	)
OR CONTAINS(LOWER([result_title]),	" antarktisk"	)
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
OR CONTAINS(LOWER([result_title]),	"northatlantic"	)
OR CONTAINS(LOWER([result_title]),	"mid-atlantic"	)
OR CONTAINS(LOWER([result_title]),	"north-east atlantic"	)
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
OR CONTAINS(LOWER([result_title]),	"arctic water"	)
OR CONTAINS(LOWER([result_title]),	"polar water"	)
OR CONTAINS(LOWER([result_title]),	"arctic current"	)
OR CONTAINS(LOWER([result_title]),	"polar current"	)
OR CONTAINS(LOWER([result_title]),	"south polar"	)
))		
THEN "KLIMA"		
		
ELSEIF		
		
//OR CONTAINS(LOWER([Artikel/kapiteltittel]),	"glacial"	)
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
		
OR (CONTAINS(LOWER([result_title]),	" warm"	)
AND CONTAINS(LOWER([result_title]),	"arctic "	))
OR CONTAINS(LOWER([result_title]),	"arctic amplification"	)
THEN "KLIMA"		
		
ELSEIF		
(		
CONTAINS(LOWER([result_title]),	"anthropo"	)
AND		
(CONTAINS(LOWER([result_title]),	"heating"	)
OR CONTAINS(LOWER([result_title]),	"forcing"	)
OR CONTAINS(LOWER([result_title]),	"change"	)
OR CONTAINS(LOWER([result_title]),	"driv"	)
OR CONTAINS(LOWER([result_title]),	"feedback"	)
))		
		
OR CONTAINS(LOWER([result_title]),	"climatology"	)
OR CONTAINS(LOWER([result_title]),	"global warming"	)
OR CONTAINS(LOWER([result_title]),	"earth system"	)
OR CONTAINS(LOWER([result_title]),	"noresm"	)
OR CONTAINS(LOWER([result_title]),	"echam5"	)
OR CONTAINS(LOWER([result_title]),	"cmip"	)
OR CONTAINS(LOWER([result_title]),	"gcm"	)
OR CONTAINS(LOWER([result_title]),	"aogsm"	)
OR CONTAINS(LOWER([result_title]),	"ukmo-hadcm"	)
OR CONTAINS(LOWER([result_title]),	"ukmo-hadgem"	)
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
OR CONTAINS(LOWER([result_title]),	"heat wave"	)
OR CONTAINS(LOWER([result_title]),	"heatwave"	)
OR CONTAINS(LOWER([result_title]),	"tipping point"	)
OR CONTAINS(LOWER([result_title]),	"albedo changes"	)
		
THEN "KLIMA"		
		
ELSEIF		
(		
(CONTAINS(LOWER([result_title]),	"extreme"	)
OR CONTAINS(LOWER([result_title]),	"chang"	)
OR CONTAINS(LOWER([result_title]),	"rise"	)
OR CONTAINS(LOWER([result_title]),	"record"	)
OR CONTAINS(LOWER([result_title]),	"global"	)
OR CONTAINS(LOWER([result_title]),	"increas"	)
OR CONTAINS(LOWER([result_title]),	"variab"	)
//OR CONTAINS(LOWER([Artikel/kapiteltittel]),	"predict"	)
)		
AND(		
CONTAINS(LOWER([result_title]),	"precipitation"	)
OR CONTAINS(LOWER([result_title]),	"temperature"	)
OR CONTAINS(LOWER([result_title]),	"drought"	)
OR CONTAINS(LOWER([result_title]),	"atmospher"	)
OR CONTAINS(LOWER([result_title]),	"ocean"	)
OR CONTAINS(LOWER([result_title]),	"flood"	)
OR CONTAINS(LOWER([result_title]),	"weather"	)
))		
	
		
OR(		
(CONTAINS(LOWER([result_title]),	" sea "	)
OR CONTAINS(LOWER([result_title]),	"ocean"	)
)		
AND		
(CONTAINS(LOWER([result_title]),	"level"	)
OR CONTAINS(LOWER([result_title]),	"warm"	)
OR CONTAINS(LOWER([result_title]),	"heat"	)
OR CONTAINS(LOWER([result_title]),	"acidification"	)
OR CONTAINS(LOWER([result_title]),	"co2"	)
OR CONTAINS(LOWER([result_title]),	"co2"	)
OR CONTAINS(LOWER([result_title]),	"carbon"	)
OR CONTAINS(LOWER([result_title]),	"predict"	)
OR CONTAINS(LOWER([result_title]),	"variabil"	)
))		
		
		
		
		
THEN "KLIMA"		
ELSEIF		
(		
(		
(CONTAINS(LOWER([result_title]),	"climat"	)
AND CONTAINS(LOWER([result_title]),	"chang"	)
)		
OR		
(CONTAINS(LOWER([result_title]),	"warm"	)
AND CONTAINS(LOWER([result_title]),	"global"	)
))		
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
OR CONTAINS(LOWER([result_title]),	"war"	)
OR CONTAINS(LOWER([result_title]),	"conflict"	)
OR CONTAINS(LOWER([result_title]),	"affect"	)
OR CONTAINS(LOWER([result_title]),	"effect"	)
OR CONTAINS(LOWER([result_title]),	"influence"	)
OR CONTAINS(LOWER([result_title]),	"scenario"	)
OR CONTAINS(LOWER([result_title]),	"infrastructure"	)
OR CONTAINS(LOWER([result_title]),	"ship"	)
		
OR CONTAINS(LOWER([result_title]),	"forest"	)
OR CONTAINS(LOWER([result_title]),	"resources"	)
OR CONTAINS(LOWER([result_title]),	"health"	)
OR CONTAINS(LOWER([result_title]),	"disease"	)
OR CONTAINS(LOWER([result_title]),	"sick"	)
OR CONTAINS(LOWER([result_title]),	"death"	)
OR CONTAINS(LOWER([result_title]),	"hunger"	)
OR CONTAINS(LOWER([result_title]),	"hungry"	)
		
OR CONTAINS(LOWER([result_title]),	"migrat"	)
OR CONTAINS(LOWER([result_title]),	"refugee"	)
OR CONTAINS(LOWER([result_title]),	"ecosystem"	)
OR CONTAINS(LOWER([result_title]),	"societ"	)
OR CONTAINS(LOWER([result_title]),	"communit"	)
OR CONTAINS(LOWER([result_title]),	"agricultur"	)
OR CONTAINS(LOWER([result_title]),	"landuse"	)
OR CONTAINS(LOWER([result_title]),	"land area cover"	)
OR CONTAINS(LOWER([result_title]),	"soil"	)
		
OR CONTAINS(LOWER([result_title]),	"food"	)
))		
THEN "KLIMA"		
		
ELSEIF		
		
		
(CONTAINS(LOWER([result_title]),	"ozone"	)
OR CONTAINS(LOWER([result_title]),	"carbon"	)
OR CONTAINS(LOWER([result_title]),	"greenhouse"	)
OR CONTAINS(LOWER([result_title]),	"co2"	)
OR CONTAINS(LOWER([result_title]),	"co2"	)
		
)AND(		
(CONTAINS(LOWER([result_title]),	"scenario"	)
OR CONTAINS(LOWER([result_title]),	"emission"	)
OR CONTAINS(LOWER([result_title]),	"effect"	)
))
OR		
(		
CONTAINS(LOWER([result_title]),	"permafrost"	)
AND(		
CONTAINS(LOWER([result_title]),	"melt"	)
OR CONTAINS(LOWER([result_title]),	"methan"	)
OR CONTAINS(LOWER([result_title]),	"production"	)
OR CONTAINS(LOWER([result_title]),	"feedback"	)
))		
		
THEN "KLIMA"		
ELSEIF		
		
CONTAINS(LOWER([result_title]),	"human footprint"	)
OR CONTAINS(LOWER([result_title]),	"carbon footprint"	)
OR CONTAINS(LOWER([result_title]),	"climate footprint"	)
OR CONTAINS(LOWER([result_title]),	"global footprint"	)
OR CONTAINS(LOWER([result_title]),	"klimaeffekt"	)
OR CONTAINS(LOWER([result_title]),	"klimaendr"	)
OR CONTAINS(LOWER([result_title]),	"klimavirkn"	)
		
THEN "KLIMA"		

ELSE 'no'
END
