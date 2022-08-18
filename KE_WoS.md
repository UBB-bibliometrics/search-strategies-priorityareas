# Klima og Energiomstilling

See Tableau/Cristin file for main documentation. The string contains of four blocks

## ANY
```Ceylon =
TS=(
("climat* NEAR/3 change* ") OR ("climat*"  NEAR/3  "warm*") OR "global warming" )  
)			
```



## Klima 

```Ceylon =
TS=(
	("climat*"  
	AND 		
		("coupled*" OR "coupling" OR "vulnerable" OR "projection*" OR "dynamic*" OR "model*" OR "carbon" OR "feedback*" 
		OR "interact*" OR   "scenario*" OR   "regime*" OR   "shift*" OR    "forcing*" OR    "goal*" OR   "amplificat*" OR "predict*" 
		OR "fluctuat*" OR   "simulat*" OR   "variab*" OR   "driver*" OR   "post normal " OR   "anthropo*" OR   "pattern*" OR "tipping point*" 
		OR "annular mod" 
		OR ("oscillation*" AND ("atmosph*" OR "atlantic"  OR "ocean*" OR "southern" OR "pacific" OR "arctic"))  
		OR "el nino" OR  "la nina" OR   "ENSO"  or "polar cell" OR "Hedley cell" OR "overturning"
		OR "palaeo*" OR "paleo*" OR "past" OR "reconstruct*" OR " ice-core" OR "icecore" OR "quaternary" OR "pleistocene" OR   "holocene" OR   "pliocene"
		OR "atmosph*" OR "cloud*" OR   "rain*" OR   "precipitation*" OR   "snow*" OR   "storm*" OR   "weather" 
		OR "monsoon*" OR "cyclon*" OR "typho*" OR  "temperature*" OR "meteorolog*" OR "radiat*" OR "aerosol*"  OR "black carbon" 
		OR   "heat wave*"   OR   "heatwave*"  OR   "albedo"  OR   "1.5"  OR   "2 deg*" OR   "2 C"  
		)  		
	) 		
)			
OR			
TS=(	
	(		
	   ("climate" OR "warming" OR "global chang*" )  		
	   AND  
	      	("coral*" OR "reef*" OR "*water*" OR "ocean*" OR "sea" OR "seas" OR "Atlantic" OR "Pacific" 
		OR "*algae"  OR "*algea*" OR "plankton*" OR "fish" OR "fishes" OR "shellfish*" OR "coast*" OR "estuary" OR "lake*" OR "marine" OR "SST" 
	  	OR "pollen" OR "flora"  OR "fauna" OR "plant" OR "plants" OR "biolog*" OR "biodiver*" OR "biota" OR "canopy" 
		OR "ecology" OR "bushfire*" OR "bush fire*" OR "nitrogen" OR "pollution*" OR "ecosystem*" 
		OR "flood*" OR "drought*" OR "land slide*" OR "avalanch*" OR "erosion*" OR "erodin*"
		OR "wetland*" OR "arid*" OR "desert*" OR "dryland*" OR "groundwater*"
	  	OR "tundra" OR "taiga" OR "cryospher*"  OR "tree line*" OR "aerosol*" OR "vegetation*" OR "swamp*" OR "permafrost"   
		OR "geolog*" OR "geophys*" OR "dinoflagel*" OR "paleontolo*" OR "mineral*" OR "sediment*"
	  	OR "arctic*"  OR   "polar"  OR   "north pole" OR   "northpole" OR   "high nort " OR   "high-north" OR "svalbard" OR   "spitsbergen" OR   "bjornoya" OR   "jan mayen"   OR   "greenland" OR   "north alaska"    OR   "north quebec" OR   "axel heiberg"   OR   "north slope"  OR   "prudhoe" OR   "barrow"   OR   "zemlya"  OR   "yermak"    OR   "franz josef"    OR   "northwest territories"   OR   "high latitude" OR   "high-latitude"   OR   " south pole "  OR   "north atlantic" OR   "mid-atlantic"   OR   "north-east atlantic" OR   "atlantic " OR   "barents sea"    OR   "greenland sea" OR   "north sea"    OR   "norwegian sea"  OR   "nordic seas" OR   "skager"     OR   "chukchi sea" OR   "east Siberian sea" OR   "laptev sea"    OR   "kara sea"     OR   "labroador sea" OR   "Greenland sea" OR   "Beaufort sea"  OR   "Sea of Okhotsk" OR   "weddel sea"  OR   "ross sea"    OR   "hudson bay"  OR   "drake passage" OR   "bering strait" OR   "davis strait"     OR   "nares strait"   OR   "jan mayen"     OR   "scotland ridge" OR   "greenland basin"  OR   "gulf stream" 
		)	
	)	
)			
OR			
TS=(
	(("sea" OR "ocean*") AND ("level" OR "warming" OR "acidification" OR "co2" OR "co 2" OR "heat*"))
	OR "water mass transformation" OR "water mass formation"
	OR "glacier*" OR "ice cap*"  OR "ice-field*" OR "ice sheet*" OR "ice shelves" OR "ice shelf" OR "sea-ice" OR "sea ice" OR "pack ice" OR "polynya*"  
	OR   "ice variab*" OR   "ice cover*" OR   "ice retreat*"  OR   "ice retract*"    OR   "ice exten*"  OR   "ice thickness" OR   " nilas "   OR   "ice chart*"  OR   "ice-berg*" OR   "ice berg*" OR   "iceberg*" OR   "slush"   OR   "pancake ice" OR   "pack ice"   OR   "ice ridge*"   OR   "grease ice"   OR      "marginal ice zone*"   OR   "multi-year ice" OR   "first-year ice"  
	OR  "antarctic*" 
	OR "noresm" OR   " echam5"   OR   "cmip" OR   "GCM" OR   "AOGSM"   OR   "UKMO-hadcm" OR   "UKMO-hadgem" OR  "FGOALS" OR   "GFDL-CM" OR   "GISS-EH" OR   "GISS-ER"  OR   "INM-cm" OR   "IPSL-CM" OR   "MIROC3" OR   "GISS-EH"  OR   "BCC-CM"  OR   "BCCR-BCM"     OR   "ccsm3" OR   "cgcm3" OR   "cnrm-cm3" OR   "csiro"  
	OR ("arctic" AND "future")
	OR (("decadal" OR "seasonal" ) NEAR/3 ("prediction*" OR "variablilit*" OR "change*" OR "oscillation" OR "mode"))
)						
OR			
TS=(	
	("climat*'"		
	AND  
		("disaster*" OR "collaps*" OR "catastroph*" OR "extinct*" OR "respon*" OR "crisis" OR "crises" OR "hazard*" 
		OR "impact*" OR "vulnerability" OR "footprint*"
		)			
	)		
)			
OR			
TS=(	
	(		
		(("climat* NEAR/3 change* ") 
		OR ("climat*" NEAR/3 "warm*") 
		OR "global warming" OR "global change"
		)  
		AND
			( "habitat*" OR "extinct*" OR "speci*" OR "population*" OR "ecosystem*"  
			OR "emission*" OR "consequence*" OR "impact*" OR "footprint*" OR "assess" OR "risk*" 
			OR "quota*" OR "war" OR "wars" OR "milit* conflict*"   
			OR "affect*" OR "effect*" OR "influenc*" OR "scenario*"   
			OR "infrastructure*"   OR   "ship*"   
			OR "forest*"   OR   "resourc*"
			OR "health" OR "disease*" OR "sick*" OR "death*" OR "hunger" OR "hungry"   
			OR "migration*"     
			OR "societ*" OR "communit*"  OR "people" OR "human" OR "inuit"
			OR "agricultur*" OR "farmland*" OR "agricultur*" OR "land us*" OR "land area cover*" OR "soil*" OR "food" 
			OR "finance*" OR "economy*" ) 
			
	)		
)			
OR			
TS=(
	("anthropo*" AND ("heating" OR "forcing*" OR "chang*" OR "driv*" OR "feedback*" OR "climat*"))  
	OR "human footprint*" OR "carbon footprint*"	
	OR (("ozone" OR "carbon" OR "greenhouse" OR "co 2" OR "co2") AND ("scenario*" OR "feedback*" OR "budget"))
	OR (("permafrost") AND ("melt*" OR "methane" OR "feedback"))	
	OR "climatology" 
)			
			
```

## Tilpassning 

```Ceylon =
TS=(														
	(("climat*" NEAR/3 "change* ") OR ("climat*" NEAR/3 "warm*" ) OR "global warming" OR "global change")	
	NEAR/5	(	"action*"											
		OR	"plan*"											
		OR	"resilie*"											
		OR	"adapt*"											
		OR	"mitiga*"											
		OR	"preparedness"											
		OR	"adjust*"											
		OR	"transition$"											
		OR	"prevent*"											
		OR	"minimis*" OR	minimiz*										
		OR	"prevent*"											
		OR	"risk*"											
		OR	"challeng*"											
		OR	"lifestyle$"											
		OR	"anticipat*"											
														
		OR	"politic$"											
		OR	"law$"											
		OR	"regulation$"											
		OR	"manag*"											
		OR	"governance"											
		OR	"polic*"											
		OR	"penalt*"											
		OR	"leadership$"											
		OR	"negotiation$"											
		OR	"solution$"											
		OR	"information$"											
		OR	"justice"											
														
		OR	"ethic$"											
		OR	"service$"											
		OR	"energy"											
		OR	"litigation"											
		OR	perception$											
		OR	"concept$"											
		OR	"sustainab*"											
		OR	"engagement"											
														
		OR	"initiat*"											
		OR	"debate$"											
		OR	"stories"											
		OR	"story"											
		OR	"discours*"											
		OR	"discurs*"											
		OR	"narrative$"											
		OR	 ("action*" OR "anticipat*" OR "prevent*" OR "minimi*" OR "planning" OR "plan" OR "plans" OR "resilie*" OR "adapt*" OR "mitiga*" OR "politic*" OR "adjust*" OR "transition*" OR "manag*" OR "governance" OR "tackl*" OR "protect*" OR "polic*" OR "penalty" OR "leadership" OR "negoti*" OR "solution*" OR "information*" OR "justice" OR "regulat*" OR "ethic*" OR "service*" OR "energy" OR "litigation*" OR "perception*" OR "concept*" OR "sustainab*" OR "engag*" OR "initiat*" OR "geoengineer*" OR "energy law" OR   "consum*" OR   "percept*" OR   "angst" OR " attitude*" OR "awareness*" OR "concept$" OR "consciousness" OR "feeling$ " OR "image$" OR "impression$" OR "judgment$" ) 											
		OR	"accept*"											
		OR	"moral"											
		OR	"obligation$"											
		OR	"fair share"											
		OR	"denial$"											
		OR	"skeptic$"											
		OR	"harming"											
														
		OR	"worries"											
		OR	"philosoph*"											
		OR	"belief"											
		OR	"believes"	)										
)														
														
OR														
TS=(		(	("extreme*" near/3 ("weather"OR "precipitation"OR "temperature*" OR "rain*"))											
		AND	("adapt*" OR "mitiga*" OR "prevent*" OR "resilie*" OR "plan"OR "planning" OR "plans"OR "governance" OR "polic*")	)										
														
	OR	(	("heat wave*" OR "heatwave*" OR "tipping point*" OR "sea level*" OR "bushfire" OR "drought*" OR "flood*" )											
		NEAR/10	("adapt*" OR "mitiga*" OR "prevent*" OR "resilie*" OR "planning" OR "plan" OR "plans"OR "governance" OR "polic*")	)										
														
														
OR	(	("ipcc" OR "kyoto protocol") 												
	OR ("climate" OR "paris") NEAR/3 ("agreement" OR "treaty")													
)														
														
OR		(	(("lower*" OR "reduc*" OR "minim*" OR "reduc*"OR "zero")											
			NEAR/3	("carbon" OR "greenhouse gas*" OR "co2" OR "co 2"))										
			AND "emission$"											
			)											
		OR		("carbon cut*")										
		OR		"zero carbon"										
														
OR		("climate target*")												
OR		("climate law*" OR "climate action*"OR "SDG13" OR "SDG-13"OR "climate fear"OR "climate justice" OR ("law" near/3"environment*"))												
														
OR	(	("co2" OR "co 2" OR "greenhouse gas*" OR "ghg* " OR "methane" OR "n2o" OR "nitrous oxide" OR "ozone")												
	NEAR/10	("sink*" OR"storage" OR "storing"OR "trading" OR "doubling" OR "reduc*" OR "trap*")												
	)													
OR		("carbon cut*")												
OR		("carbon capture"OR"carbon sequestrat*")												
OR	(	("lower"OR"reduc*"OR"minim*")												
	 NEAR/5	("human footprint*" OR "carbon footprint*")												
	)													
														
														
OR 	("climate"													
	NEAR/3 													
	(	"service*"												
	OR	"negotiation*"												
	OR	"scepsis*"												
	OR	"consens*"												
	OR	"policy"												
	OR	"policies"												
	OR	"ethic$"												
	))													
	OR	("green economy" OR "circular econom*")												
	OR 	"green cit*"  OR "climate city" OR "climate cities" OR "green capital*" OR "urban transformation*" OR "smart city" OR "smart cities" 												
		OR "sustainable transformation"												
)														
														
OR														
TS= (	(	("subsidies" OR "subsidy")												
	NEAR/3	(	"oil"											
		OR	"coal"											
		OR	"fossil fuel$"											
		)												
	)													
	AND 	(	" reduc"											
		OR	"phasing out"											
		OR	"phase out"											
		OR	"remove"											
		OR	"reduce"											
		OR	" end "											
		)												
)														
```
## Energy

```Ceylon =

((TS= ( ( ("energy sector$") OR ("*national energy" ) OR ("energy market$" )  OR "energy infrastructure$") 														
	NEAR/3  ("future" OR "transform*" OR "transition$" OR "green" OR "modern" OR "sustainable")													
														
)														
														
OR														
(TS= ("energy transition") NOT SU="PSYCHOLOGY")														
														
OR														
(														
TS=( ( "energy management" OR "energy payback time" OR "energy cost$"														
OR "energy justice" OR "climate and energy solution" OR "energy poverty"														
OR "energy future")														
OR (("carbon" OR "co2" OR "greenhouse gas*" ) NEAR/3 ("cost" OR "trade" OR "trading" OR "pricing" OR "price$"))														
)														
														
	NOT (WC=("REHABILITATION" OR "CLINICAL NEUROLOGY" OR "HOSPITALITY LEISURE SPORT TOURISM "NOT "MATHEMATICS" NOT "THERMODYNAMICS") )													
)														
														
OR														
														
TS=( (( ("renewable" OR "sustainable" OR "green" OR "alternative" OR "clean")														
NEAR/3 ("power" OR "energy" OR "energies" OR "fuel*" OR "electricity")														
) NOT "metabolism")														
OR ("new renewables")														
)														
														
OR														
TS= ( ("wind farm*" OR "windfarm*" OR "offshore wind* " OR "wind energy" OR "windenergy"OR "wind power" OR "wind profile$" OR "wind turbine*"OR "wind electricity*"OR ("wind" NEAR/3 ("operation*" OR "maint*") ) OR "windresource$")														
NOT ("solar wind" OR "aquacultur*")														
)														
														
														
														
OR														
														
(TS= (("alga$" OR "alge$") near/3  (" energy" OR "fuel*" )) NOT  SU=("Biology" OR "Geology" OR "geoscience" OR "Oceanography") )														
														
OR														
(														
TS= (" tidal turbine*" OR " stream turbine* " OR " current turbine* " OR " tidal power " OR "tidal electricity" OR "tidal energy " OR "hydropower"  OR "hydroelectric power")														
NOT WC=("Marine & Freshwater Biology" OR "ECOLOGY" OR "Fisheries")														
)														
														
OR														
														
														
TS = ( (("geother*"														
NEAR/3 ( "energy" OR "reservoir*") ) OR "geothermal heat pump*")														
)														
														
OR														
(														
TS=( "solar power" OR "solar plant" OR "solar panel" OR "PV"OR "solar-panel" OR "solar arra*" OR "solar cell*" OR "photovoltaic*" OR ("solar"  AND "kW")														
or "solar electricity" OR "solar collector$"														
)														
NOT WC=( "ASTRONOMY ASTROPHYSICS" OR "MARINE FRESHWATER BIOLOGY" OR "BIOLOGY" OR "METALLURGY METALLURGICAL ENGINEERING")														) OR 
TS =	(	 "bio fuel*" OR "bio energy" OR "bio diesel"  OR "bio gas" OR "bio ethanol" OR												
		 "biofuel*" OR "bioenergy" OR "biodiesel"  OR "biogas" OR "bioethanol")												
														
OR														
TS = (														
				 "green petroleum"										
				OR		"climate technolog*"								
)														
														
														
														
														
														
														
OR 														
TS=(			("lignin" OR (("wood" OR "birch") NEAR/3("pellet*" OR "biomass")))											
		AND	("power" OR "energy" OR "energies" OR  "fuel*")											
														
	)													
OR 														
														
TS=(		 ("hydrogen" NEAR/3 ("power fuel*" OR "power cell*" OR "energy" OR "efficiency") )												
		)												
														
) NOT SO=("PETROLEUM SCIENCE AND TECHNOLOGY" OR "Petroleum Science" OR "PETROLEUM GEOSCIENCE" OR "Petroleum Exploration and Development" OR "PETROLEUM CHEMISTRY" OR "MARINE AND PETROLEUM GEOLOGY" OR "JOURNAL OF THE JAPAN" AND "PETROLEUM INSTITUTE" OR "JOURNAL OF PETROLEUM SCIENCE AND ENGINEERING" OR "JOURNAL OF PETROLEUM GEOLOGY" OR "China Petroleum Processing & Petrochemical Technology")														
														
 OR SO= 	(													
		WIND ENERGY												
	OR	Sustainable Energy Technologies and Assessments												
	OR	Sustainable Energy Grids & Networks												
	OR	Sustainable Energy & Fuels												
	OR	SOLAR ENERGY MATERIALS AND SOLAR CELLS												
	OR	SOLAR ENERGY												
	OR	RENEWABLE ENERGY												
	OR	RENEWABLE & SUSTAINABLE ENERGY REVIEWS												
	OR	PROGRESS IN PHOTOVOLTAICS												
	OR	JOURNAL OF SOLAR ENERGY ENGINEERING-TRANSACTIONS OF THE ASME												
	OR	Journal of Renewable and Sustainable Energy												
	OR	JOURNAL OF CLEANER PRODUCTION												
	OR	Journal of Biobased Materials and Bioenergy												
	OR	International Journal of Precision Engineering and Manufacturing-Green Technology												
	OR	INTERNATIONAL JOURNAL OF HYDROGEN ENERGY												
	OR	International Journal of Greenhouse Gas Control												
	OR	International Journal of Green Energy												
	OR	IEEE Transactions on Sustainable Energy												
	OR	IEEE Journal of Photovoltaics												
	OR	Green Energy & Environment												
	OR	Global Change Biology Bioenergy												
	OR	GEOTHERMICS												
	OR	Geothermal Energy												
	OR	Environmental Progress & Sustainable Energy												
	OR	Biotechnology for Biofuels												
	OR	BioResources												
	OR	BIORESOURCE TECHNOLOGY												
	OR	BIOMASS & BIOENERGY												
	OR	Biofuels-UK												
	OR	Biofuels Bioproducts & Biorefining-Biofpr												
	OR	BioEnergy Research												
	OR	Algal Research-Biomass Biofuels and Bioproducts												
	)													
```
