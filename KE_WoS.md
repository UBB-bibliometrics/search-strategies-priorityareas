# Climate and energy transition (Klima og energiomstilling)

See Tableau/Cristin file for main documentation.

## ANY

Note IPCC not included as it can be used in many other abbreviations - only included in title search in Cristin. 

```py =
TS=(
	("climat*" NEAR/3 ("chang*" OR "warm*"))
	OR ("ocean*" NEAR/3 ("warming" OR "warmer"))
	OR "global warming" 
)		
```

## Climate systems and effects

Klimasystemer og effekter.

```py =
TS=(
	("climat*"  
	AND 		
		("coupled*" OR "coupling" OR "vulnerable" OR "projection$" OR "dynamic*" OR "model*" OR "carbon" OR "feedback*" 
		OR "interact*" OR "scenario*" OR "regime*" OR "shift*" OR "forcing*" OR "goal*" OR "amplificat*" OR "predict*" 
		OR "fluctuat*" OR "simulat*" OR "variab*" OR "driver*" OR "anthropo*"
		OR ("oscillation*" NEAR/3 ("atmosph*" OR "atlantic" OR "ocean*" OR "southern" OR "pacific" OR "arctic")) 
		OR "annular mod" OR "pattern*" 
		OR "atmosph*" OR "cloud*" OR "rain*" OR "precipitation*" OR "snow*" OR "permafrost" OR "cryospher*" 
		OR "monsoon*" OR "cyclon*" OR "typho*" 
		OR "temperature*" OR "meteorolog*" OR "storm*" OR "weather" 
		OR "overturning"
		OR "palaeo*" OR "paleo*" OR "history" OR "reconstruct*" OR "ice-core" OR "icecore" OR "quaternary" OR "pleistocene" OR "holocene" OR "pliocene"

		OR "1.5 deg*" OR "1.5 C" OR "2 deg*" OR "2 C" 
		OR "el nino" OR  "la nina" OR "ENSO" OR "polar cell" OR "Hedley cell" OR "overturning"
		)  		
	) 		
)
OR			
TS=(
	("global warming" OR ("climat*" NEAR/3 ("change*" OR "warm*")))  
	NEAR/5 ("response" OR "forcing" OR "sensitiv*" OR "records" OR "trend*" OR "legacy" OR "trigger$")
)
OR			
TS=(		
	("climate" OR "warming" OR "global chang*" )  		
	AND  
		("coral*" OR "reef*" OR "*water*" OR "ocean*" OR "sea" OR "seas" OR "Atlantic" OR "Pacific"
		OR "*algae" OR "*algea*" OR "kelp$" OR "plankton*" OR "fish" OR "fishes" OR "shellfish*" OR "coast*" OR "estuary" OR "lake*" OR "marine" OR "SST" 
		OR "pollen" OR "flora"  OR "fauna" OR "plant" OR "plants" OR "biolog*" OR "biodiver*" OR "biota" OR "canopy"
		OR "tundra" OR "taiga" OR "tree line*" OR "aerosol*" OR "vegetation*" OR "swamp*"
		OR "ecology" OR "bushfire*" OR "bush fire*" OR "nitrogen" OR "pollution*" OR "ecosystem*"
		OR "wetland*" OR "arid*" OR "desert*" OR "dryland*" OR "groundwater"
		OR "geolog*" OR "geophys*" OR "dinoflagel*" OR "paleontolo*" OR "mineral*" OR "sediment*"

		OR "arctic*" OR "antarctic*" OR "polar" OR "north pole" OR "northpole" OR "high north" OR "high-north" OR "svalbard" OR "spitsbergen" OR "bjornoya"
		OR "jan mayen" OR "greenland" OR "north alaska" OR "north quebec" OR "axel heiberg" OR "north slope" OR "prudhoe" OR "barrow" OR "zemlya" OR "yermak" OR "franz josef" OR "northwest territories" OR "high latitude" OR "high-latitude" OR "south pole" OR "north atlantic" OR "mid-atlantic" OR "north-east atlantic" OR "atlantic" OR "barents sea" OR "greenland sea" OR "north sea" OR "norwegian sea"  OR "nordic seas" OR "skagerrak" OR "chukchi sea" OR "east Siberian sea" OR "laptev sea" OR "kara sea" OR "labroador sea" OR "Greenland sea" OR "Beaufort sea" OR "Sea of Okhotsk" OR "weddel sea" OR "ross sea" OR "hudson bay" OR "drake passage" OR "bering strait" OR "davis strait" OR "nares strait" OR "jan mayen" OR "scotland ridge" OR "greenland basin" OR "gulf stream" 
		)
)			
OR			
TS=(
	(("sea" OR "ocean*") NEAR/15 ("level" OR "warming" OR "acidification" OR "co2" OR "co 2" OR "heat*"))
	OR "water mass transformation" OR "water mass formation"
	OR "glacier*" OR "ice cap*" OR "ice-field*" OR "ice sheet*" OR "ice shelves" OR "ice shelf" OR "sea-ice" OR "sea ice" OR "pack ice" OR "polynya*" 
	OR "ice variab*" OR "ice cover*" OR "ice retreat*" OR "ice retract*" OR "ice exten*" OR "ice thickness" OR "nilas" OR "ice chart*" OR "ice-berg*" OR "ice berg*" OR "iceberg*" OR "slush" OR "pancake ice" OR "pack ice" OR "ice ridge*" OR "grease ice" OR "marginal ice zone*" OR "multi-year ice" OR "first-year ice" 
	OR ("anthropo*" NEAR/5 ("heating" OR "forcing*" OR "chang*" OR "driv*" OR "feedback*" OR "climat*"))	
	OR "climatology" OR "climate scien*"
	OR "noresm" OR "echam5" OR "cmip" OR "cmip5" OR "GCM" OR "AOGSM" OR "UKMO-hadcm" OR "UKMO-hadgem" 
	OR "FGOALS" OR "GFDL-CM" OR "GISS-EH" OR "GISS-ER" OR "INM-cm" OR "IPSL-CM" OR "MIROC3" OR "GISS-EH" OR "BCC-CM" OR "BCCR-BCM" 
	OR "ccsm3" OR "cgcm3" OR "cnrm-cm3" OR "csiro"  
	OR "albedo" OR "aerosol*" OR "black carbon"
	OR ("arctic" NEAR/5 "future")
	OR (("decadal" OR "seasonal" ) NEAR/5 ("prediction*" OR "variablilit*" OR "change*" OR "oscillation" OR "mode"))
)	
OR			
TS=(
	("climat*"		
	AND  
		("disaster*" OR "collaps*" OR "catastroph*" OR "extinct*" OR "crisis" OR "crises" OR "hazard*" 
		OR "impact*" OR "vulnerability" OR "footprint*" OR "tipping point*" 
		OR "heat wave*" OR "heatwave*"
		OR "flood*" OR "drought*" OR "land slide*" OR "avalanch*" OR "erosion*" OR "erodin*"
		OR ("extreme$" NEAR/5 ("climat*" OR "weather" OR "temperature$"))
		)
	)
)			
OR			
TS=(
	(
		(("climat*" NEAR/3 ("change*" OR "warm*"))
		OR "global warming"
		)  
		AND
			( "habitat*" OR "extinct*" OR "speci*" OR "population*" OR "ecosystem*"  
			OR "emission*" OR "consequence*" OR "impact*" OR "footprint*" OR "assess" OR "risk*" OR "quota*"
			OR "war" OR "wars" OR "milit* conflict*"  
			OR "affect*" OR "effect*" OR "influenc*" OR "scenario*" OR "impact$"
			OR "infrastructure*" OR "ship*"  
			OR "forest*" OR "resourc*"
			OR "health" OR "disease*" OR "sick*" OR "death*" OR "hunger" OR "hungry"  
			OR "migration*" OR "migrant$" OR "refugee$" 
			OR "societ*" OR "communit*"  OR "people" OR "human" OR "inuit"
			OR "agricultur*" OR "farmland*" OR "agricultur*" OR "aquacultur*" OR "land us*" OR "land area cover*" OR "soil*" OR "food"
			OR "finance*" OR "econom*"
			) 

	)
)
OR			
TS= ("human footprint*"
	OR (("ozone" OR "carbon" OR "greenhouse" OR "co 2" OR "co2") AND ("scenario*" OR "feedback*" OR "budget"))
	OR (("permafrost") AND ("melt*" OR "methane" OR "feedback"))
)			

```

## Climate adaptation 

Klimatilpasning.

Note, in the 2022 version, the number of results for "tilpasning" has been reduced slightly. This is due to a change in truncation of climate + plan*, which to climate + plan/plans/planning - before, it was erroneously finding results about climate change and plant communities (which should be in systems and effects).

```py =
TS=(
	(("climat*" NEAR/3 "change* ")
	OR ("climat*" NEAR/3 "warm*" )
	OR "global warming" OR "global change"
	)
	NEAR/15
		("action*"
		OR "preparedness" OR "anticipat*"
		OR "prevent*" OR "minimis*" OR "minimiz*" OR "tackl*" OR "protect*"
		OR "plan" OR "planning" OR "plans"
		OR "resilie*" OR "adapt*" OR "adjust*" OR "mitiga*" 
		OR "manag*" OR "governance" OR "leadership$"
		OR "politic*" OR "regulation$" OR "polic*" OR "target$"
		OR "law$" OR "litigation" OR "penalt*" OR "justice"
		OR "risk*" OR "challeng*" OR "negotiation$" OR "solution$"	
		OR "transition$" OR "lifestyle$" OR "service$" OR "consum*"
		OR "sustainab*"
		OR "concept$" OR "post normal" 
		OR "information$" OR "awareness" OR "consciousness" OR "education" OR "knowledge" 
		OR "engagement" OR "initiat*" OR "accept*"
		OR "perception$" OR "attitude$" OR "judegement$" OR "feeling$" OR "impressions" OR "image$"
		OR "stories" OR "story" OR	"narrative$"
		OR "discours*" OR "discurs*" OR "debate$"
		OR "moral" OR "ethic*"
		OR "obligation$" OR "fair share"
		OR "denial$" OR "skeptic$"
		OR "harming" OR "worries" OR "angst" OR "anxiety"
		OR "philosoph*" OR "belief" OR "believes"
		)
)				
OR
TS=(
	"climate action" OR "climate mitigation" OR "climate adaptation" OR "climate resilience" OR "climate planning"
	OR "climate justice" OR "climate law$" OR "climate polic*" OR "climate ethic*" OR "climate target$" OR "climate goal$"
	OR "climate education" OR "climate concern" OR "climate knowledge"
	OR "climate negotiation$" OR "climate fund*"
	OR "climate crisis"
	OR "climate service$"
	OR "SDG13" OR "SDG-13" 
	OR ("climate" NEAR/3 ("negotiation*" OR "skeptic*" OR "consens*" OR "policy" OR "policies" OR "goal$" OR "target$"))		
)				
OR														
TS=(
	(
		("extreme*" NEAR/3 ("weather" OR "precipitation" OR "temperature*" OR "rain*"))
		AND ("adapt*" OR "mitiga*" OR "prevent*" OR "resilie*" OR "plan" OR "planning" OR "plans" OR "governance" OR "polic*")
	)
	OR
	(
		("heat wave*" OR "heatwave*" OR "tipping point*" OR "sea level*" OR "bushfire" OR "drought*" OR "flood*")
		NEAR/15	("adapt*" OR "mitiga*" OR "prevent*" OR "resilie*" OR "planning" OR "plan" OR "plans" OR "governance" OR "polic*")
	)
)												
```
## Climate adaptation and Energy transitions (common)

```py =
TS=(
	"green economy" OR "circular econom*"
	OR 	"green cit*"  OR "climate city" OR "climate cities" OR "green capital*" OR "urban transformation*" OR "urban sustainability" OR "smart city" OR "smart cities" OR "sustainable cit*"
	OR 	"sustainable transformation" OR "climate smart"
	OR 
	(
		("green" OR "carbon" OR "emission" OR "electric" OR "hybrid" OR "clean" OR "renewable")
		NEAR/5 
			("cities" OR "city" OR "shipping" OR "ferries" OR "ferry" OR "transport" OR "vehicle$" OR "aviation"
			OR "infrastructur*" OR "supply" OR "investment$" OR "incentive$" OR "certificate$"
			)
	)
	OR "electric car$" 
	OR 
	(
		("green" OR "low carbon" OR "decarbon*" OR "de carbon*" OR "emission" OR "clean" OR "renewable")
		NEAR/5 ("design" OR "process*" OR "industr*" OR "manufactur*" OR "waste" OR "disposal" OR "area use" OR "land use" OR "technolog*")
	)
	OR "climate technolog*"
)
OR
TS=(
	"carbon capture" OR "carbon sequestrat*"
	OR
	(
		("co2" OR "co 2" OR "carbon" OR "greenhouse gas*" OR "ghg*" OR "methane" OR "n2o" OR "nitrous oxide" OR "ozone")
		NEAR/10	
			("emission$" OR "footprint" OR "sink$" OR "storage" OR "storing" OR "capture" OR "sequestration" OR "trap*"
			OR "trading" OR "trade" OR "pric*" OR "cost" OR "doubling")
	)
)
OR
TS=(
	"kyoto protocol" 	OR (("climate" OR "paris") NEAR/3 ("agreement" OR "treaty"))
	OR
	(
		(
			("lower*" OR "reduc*" OR "minim*" OR "reduc*" OR "zero")
			NEAR/3	("carbon" OR "greenhouse gas*" OR "co2" OR "co 2")
		)
		AND "emission$"
	)
)
OR TS= ("carbon cut*" OR "zero carbon" OR "zero emission$" OR "climate and energy poli*")
```

## Energy transitions

Energiomstilling og fornybar energi.

`(TS= (("micro-alga*" OR "microalga*") NEAR/15 ("energy" OR "fuel*")) NOT SU=("Biology" OR "Geology" OR "geoscience" OR "Oceanography"))` is taken out, as the relevant works seem to refer to "biofuels" OR "biodiesel" etc. which are included in the search anyway. 

```py =
TS= ("energy transition$")
OR
TS=(
	("energy sector$" OR "energy system$" OR "*national energy" OR "energy market$" OR "energy infrastructure$" OR "fuel$")
	NEAR/5 ("future" OR "transform*" OR "transition$" OR "green" OR "modern" OR "sustainable" OR "alternative$")		
)
OR
TS=
	("energy mix" OR "energy ratio" OR "energy management" OR "energy planning" OR "energy strateg*" OR "energy market$" OR "electricity market$"
	OR "energy payback time" OR "energy cost$"
	OR "climate and energy solution" 

	OR "energy polic*" OR "energy law$" OR "energy poverty" OR "fuel poverty" OR "energy justice" 
	OR "energy security" OR "energy insecurity" OR "energy vulnerab*" OR "energy future"

	OR "energy infrastructure$" OR "national energy" OR "local energy" OR "community energy" OR "energy coop*" OR "energy co-op*" OR "microgrid$"
	)
OR
TS=(
	("battery" OR "batteries" OR "grid$" OR "electricity" OR "fuel cell$")
	NEAR/15 ("sustainab*" OR "green" OR "renewable$")
)
OR
TS=("energy sufficien*")
OR
TS=
(
    (
      ("energy efficien*" OR "energy utili$ation efficiency" OR "energy saving" OR "energy loss" OR "energy conservation")
      NEAR/15
          ("housing" OR "houses" OR "homes" OR "household" OR "domestic" OR "residential" OR "building$" OR "cities"
          OR "service sector" OR "office$" OR "retail" OR "food services" OR "restaurants" OR "hotels" OR "warehouses"
          OR "lighting" OR "lamps" OR "cooking" OR "appliances" OR "white goods"
          OR "plug-in device$" OR "smart"
          OR "space cooler$" OR "air condition*" OR "space heat*" OR "room heating" OR "district heating" OR "heat pump$" OR "HVAC"
          OR "industry" OR "industrial" OR "manufacturing" OR "technolog*"
          OR "transport" OR "transportation" OR "vehicles" OR "cars" OR "train$" OR "airplane$" OR "aeroplane$" OR "ship$" OR "shipping" OR "freight"
          OR "telecomm*" OR "data centre$" OR "data center$" OR "data network$" OR "server" OR "servers" OR "wireless")
    )
    OR
      (("energy efficiency" OR "energy conservation")
      NEAR/5
            ("policy" OR "policies" OR "framework$" OR "legislation" OR "management" OR "planning" OR "plan" OR "plans"
            OR "initiative$" OR "intervention$" OR "incentive$" OR "investment$" OR "investing" OR "invest")
      )
    OR
      (("energy efficiency" OR "energy consumption")
      NEAR/15
            ("green bond$" OR "climate bond$"
            OR ("certificat*" NEAR/2 ("energy" OR "green"))
            OR "energy sustainability"
            OR "minimum energy performance" OR "energy labelling" OR "energy standard$" OR "energy efficiency standard$"
            OR "sustainable development")
      )
)
OR 
TS=("new renewables" 
	OR
	(
		("renewable" OR "sustainable" OR "green" OR "alternative" OR "clean")
		NEAR/3 ("power" OR "energy" OR "energies" OR "fuel*" OR "electricity")
	)							
)
OR
TS=(
	("wind farm*" OR "windfarm*" OR "offshore wind*" OR "wind energy" OR "wind power*"
	OR "wind profile$" OR "wind turbine*" OR "wind electricity*"
	OR "wind resource$"
	)
NOT ("solar wind")
)
OR
(TS=("tidal turbine*" OR "stream turbine*" OR "current turbine*" OR "tidal power" OR "tidal electricity" OR "tidal energy" OR "hydropower" OR "hydroelectric power")
NOT WC=("Marine & Freshwater Biology" OR "ECOLOGY" OR "Fisheries")
)
OR TS=("geothermal heat pump*" OR ("geother*" NEAR/3 ("energy" OR "reservoir*")))
OR
TS=
	("solar power" OR "solar plant" OR "solar panel" OR "PV" OR "solar-panel" OR "solar arra*" OR "solar cell*" OR "photovoltaic*" 
	OR ("solar" AND "kW") OR "solar electricity" OR "solar collector$"
	)
OR 
TS=
	("bio fuel*" OR "bio energy" OR "bio diesel" OR "bio gas" OR "bio ethanol" 
	OR "biofuel*" OR "bioenergy" OR "biodiesel" OR "biogas" OR "bioethanol"
	)
OR TS = ("green petroleum")
OR
TS=(
	("lignin" OR (("wood" OR "birch") NEAR/3 ("pellet*" OR "biomass")))
	NEAR/15 ("power" OR "energy" OR "energies" OR "fuel*")
)
OR
TS=(
	"clean hydrogen" OR "green hydrogen" OR "green ammonia"
	OR (("hydrogen" OR "ammonia") NEAR/3 ("power fuel*" OR "power cell*" OR "energy" OR "efficiency" OR "green"))
)
OR 
TS=(
	("phase* out" OR "transition" OR "substitut*" OR "relian*" OR "consumption"
    OR "policy" OR "policies" OR "legislation" OR "incentiv*" OR "subsidy" OR "subsidies" 
    OR
	(
        ("reduc*" OR "decreas*" OR "improv*" OR "support" OR "encourag*" OR "intervention$")
        NEAR/5 ("use" OR "usage")
    )
    )
	NEAR/15 ("crude oil" OR "conventional energy" OR "coal" OR "natural gas" OR "petroleum" OR "fossil fuel$")
)
OR TS=("Nuclear energy" OR "fusion power*" OR "nuclear power*")
											
```
