# Marine research (Marin forskning)

See Tableau/Cristin file for main documentation. 
This file includes a WoS translation and adpation of that search string, with some additions from SDG14 (as more terms can be searched for vs. in Tableau).
Due to searching in abstracts, and due to the interdisciplinary database, a number of expressions had to be adapted. This file mainly documents these adaptations.

The string is set up so that one can either get results for **all marine research**, or a subset covering **maritime research**. 
Unlike the other satsningsområder, these two are not two independent parts - the maritime string finds a SUBSET of the marine string results. 
Thus to get only the marine research which is not maritime, one must minus the maritime subset and look at what remains. 
This maritime subset is an *estimate* only - splitting off this research using a string is difficult.

*NOTE The string for marine should also contain all terms for maritime - don't add to maritime without adding to marine*

## Marin forskning

The general structure of the string is in sections of grouped search terms: 

* Marine activities, law and technologies (applied)
* Marine organisms and species
* Research from the Sars Centre - included in its entirity after specification from NG/ÅM. The Sars Centre does not have very many publications, but this may nevertheless give a slight unfair advantage when comparing with other institutions. 

#### Marine journals 

```Ceylon =
SO=
( 	
    ("marine*" OR "ocean*" OR "estuar*" OR "deep sea*" OR "maritim*" OR "ship*") 	
    OR  
    ("Annual  review  of  marine*" 	OR  "Advances  in  marine*" 	OR  "African  journal  of  marine*" 	OR  "Archive  of  fishery  and  marine*" 	
    OR  "Biologiya  moray  marine*" 	OR  "Bulletin  of  marine*" 	OR  "Cahiers  de  biologie  marine*" 	
    OR  "Frontiers  in  marine*" 	OR  "Geo  marine*" 	OR  "Helgoland  marine*" 	
    OR  "ICES  journal  of  marine*" 	OR  "Indian  journal  of  marine*" 	OR  "International  journal  of  marine*" 	
    OR  "Journal  of  experimental  marine*" 	OR  "Journal  of  marine*" 	
    OR  "Meeresforschung  reports  on  marine*" 	OR  "mer  marine*" 	OR  "molecular  marine*" 	
    OR  "Regional  studies  in  marine*" 	OR  "Research  in  marine*" 	OR  "Russian  journal  of  marine*" 	
    OR  "South  African  journal  of  marine*" 	OR  "Transnav  international  journal  on  marine*" 	
    OR  "Vie  et  milieu  serie  a  biologie  marine*" 	OR  "China  ocean*" 	
    OR  "Acta  ocean*" 	OR  "Annales  de  l  institut  ocean*" 	OR  "Applied  ocean*" 	
    OR  "Brazilian  journal  of  ocean*" 	OR  "Cahiers  orstom  ocean*" 	OR  "California  cooperative  ocean*" 	
    OR  "Fisheries  ocean*" 	OR  "Fishery  bulletin  of  the  national  ocean*" 	
    OR  "IEEE  journal  of  ocean*" 	OR  "International  journal  of  naval  architecture  and  ocean*" 	
    OR  "Journal  of  geophysical  research  ocean*" 	OR  "Journal  of  ocean*" 	OR  "Journal  of  operational  ocean*" 	
    OR  "Journal  of  physical  ocean*" 	OR  "Journal  of  the  waterway  port  coastal  and  ocean*" 	
    OR  "Physical  ocean*" 	OR  "Progress  in  ocean*" 	OR  "Revista  de  biologia  marina  y  ocean*" 	
    OR  "Vie  et  milieu  serie  b  ocean*" 	OR  "Sea  technolog*" 	OR  "Sarsia" 	
    OR  "Journal  of  maritime*" 	OR  "Journal  of  ship  research" 	
    ) 	
)
```

#### Marine geographic areas/seas

Major oceans, plus polar/northern seas and currents used as search terms. Some were dropped if already covered by a term. Terms from Cristin string, plus https://en.wikipedia.org/wiki/List_of_seas

```Ceylon =
TS=( "arctic water$" OR "polar water$" OR "arctic current$" OR "polar current$" OR "international water$" OR "gulf stream" OR "North Water Polynya" OR "Baffin Bay" OR "Davis Strait" OR "Labrador Sea" OR "Hudson Bay" OR "James Bay" OR "Gulf of St. Lawrence" OR "Gulf of Maine" OR "Bay of Fundy" OR "Massachusetts Bay" OR "Cape Cod Bay" OR "Nantucket Sound" OR "Vineyard Sound" OR "Buzzards Bay" OR "Narragansett Bay" OR "Rhode Island Sound" OR "Block Island Sound" OR "Fishers Island Sound" OR "Long Island Sound" OR "New York Bay" OR "Jamaica Bay" OR "Raritan Bay" OR "Sandy Hook Bay" OR "Delaware Bay" OR "Chesapeake Bay" OR "Albemarle Sound" OR "Pamlico Sound" OR "Bermuda Triangle" OR "Gulf of Mexico" OR "Caribbean Sea" OR "Argentine Sea" OR "Sargasso sea" OR "Norwegian Sea" OR "North Sea" OR "Nordic seas" OR "Kattegat" OR "Skagerrak" OR "Wadden Sea" OR "Dogger Bank" OR "Denmark Strait" OR "Baltic Sea" OR "Gulf of Bothnia" OR "Kvarken" OR "Bothnian Sea" OR "South Kvarken" OR "Sea of Åland" OR "Archipelago Sea" OR "Gulf of Finland" OR "Gulf of Riga" OR "Curonian Lagoon" OR "Vistula Lagoon" OR "Gdańsk Bay" OR "Bay of Pomerania" OR "Szczecin Lagoon" OR "Bay of Greifswald" OR "Rügischer Bodden" OR "Strelasund" OR "Bay of Lübeck" OR "Bay of Kiel" OR "Kalmar Strait" OR "Bight of Hanö" OR "Danish straits" OR "English Channel" OR "Irish Sea" OR "Celtic Sea" OR "Bay of Biscay" OR "Adriatic Sea" OR "Aegean Sea" OR "Alboran Sea" OR "Balearic Sea" OR "Gulf of Lion" OR "Gulf of Sidra" OR "Ionian Sea" OR "Levantine Sea" OR "Libyan Sea" OR "Ligurian Sea" OR "Sea of Cyprus" OR "Sea of Sardinia" OR "Sea of Sicily" OR "Tyrrhenian Sea" OR "Chukchi Sea" OR "East Siberian Sea" OR "Laptev Sea" OR "Kara Sea" OR "Barents Sea" OR "Pechora Sea" OR "White Sea" OR "Queen Victoria Sea" OR "Wandel Sea" OR "Greenland Sea" OR "Lincoln Sea" OR "Baffin Bay" OR "The Northwest Passages" OR "Prince Gustav Adolf Sea" OR "Amundsen Gulf" OR "Hudson Strait" OR "Hudson Bay" OR "James Bay" OR "Beaufort Sea" OR "nares strait" OR "Greenland sea" OR "Beaufort sea" OR "Sea of Okhotsk" OR "scotland ridge" OR "greenland basin" OR "Amundsen Sea" OR "Bass Strait" OR "Bellingshausen Sea" OR "Cooperation Sea" OR "Cosmonauts Sea" OR "Davis Sea" OR "D'Urville Sea" OR "Drake Passage" OR "Great Australian Bight" OR "Gulf St Vincent" OR "Investigator Strait" OR "King Haakon VII Sea" OR "Lazarev Sea" OR "Mawson Sea" OR "McMurdo Sound" OR "Riiser-Larsen Sea" OR "Ross Sea" OR "Scotia Sea" OR "Somov Sea" OR "Spencer Gulf" OR "Weddell Sea" OR "Weddell Polynya" OR "davis strait" OR "Andaman Sea" OR "Gulf of Martaban" OR "Arabian Sea" OR "Bay of Bengal" OR "Gulf of Aden" OR "Gulf of Oman" OR "Laccadive Sea" OR "Mozambique Channel" OR "Persian Gulf" OR "Red Sea" OR "Somali Sea" OR "Timor Sea" OR "Palk Strait" OR "Gulf of Khambhat" OR "Gulf of Kutch" OR "Gulf of Mannar" OR "Palk Bay" OR "bering strait" OR "Bering Sea" OR "Chilean Sea" OR "Sea of Chiloé" OR "Gulf of Alaska" OR "Gulf of California" OR "Grau Sea" OR "Salish Sea" OR "Arafura Sea" OR "Bali Sea" OR "Banda Sea" OR "Bay of Kampong Som" OR "Bay of Plenty" OR "Bismarck Sea" OR "Bohai Sea" OR "Bohol Sea" OR "Camotes Sea" OR "Celebes Sea" OR "Ceram Sea" OR "Coral Sea" OR "East China Sea" OR "Flores Sea" OR "Gulf of Carpentaria" OR "Gulf of Thailand" OR "Halmahera Sea" OR "Hauraki Gulf" OR "Hawke's Bay" OR "Java Sea" OR "Koro Sea" OR "Molucca Sea" OR "Philippine Sea" OR "Poverty Bay" OR "Savu Sea" OR "Sea of Japan" OR "Sea of Okhotsk" OR "Seto Inland Sea" OR "Sibuyan Sea" OR "Solomon Sea" OR "South China Sea" OR "Natuna Sea" OR "North Natuna Sea" OR "South Seas" OR "Sulu Sea" OR "Tasman Sea" OR "Visayan Sea" OR "Waihau Bay" OR "Yellow Sea" ) 
```

#### Marine environments/habitats

Adapted from SDG14

```Ceylon =
 TS=  
 (  
  "ocean$" OR "oceanogra*" OR "marine" OR "seas" 	
  OR "deep sea"	OR "seabed" OR "continental shelf" OR "seamount$" 	
  OR "hydrothermal vent$" OR "cold seep$" OR "organic fall$" 	
  OR "bathyal" OR "abyssal" 	
  OR "submarine" OR "subtidal" 	
  OR "intertidal"	OR "rocky shore$" 	
  OR "mangrove$" 	
  OR "beach*" 	
  OR "salt marsh*" OR "mud flat$"	OR "*tidal flat" OR "*tidal flats" 	
  OR "seashore$" 	
  OR "sponge ground$" OR "reef" OR "reefs" OR "maerl" 	
  OR "estuar*" OR "fjord$" OR "bight" 	
  OR "coastal habitat$" OR "coastal ecosystem$" 	
  OR "coastal communit*" OR "coastal water$" OR "coastal dune$" OR "coastal zone management" 	
  OR  
      (
        ("coast*" OR "*tidal") 	
        AND  ("marsh*" OR "wetland$" OR "bay$" OR "gulf" OR "lagoon$" OR "offshore" OR "upwelling" OR "fish*" OR "aquaculture" OR "shrimp farm*")
      ) 	
  OR  
        ("sea"  
        AND  ("marsh*" OR "wetland$" OR "bay$" OR "gulf" OR "lagoon$" OR "offshore" OR "*tidal" OR "fish*" OR "aquaculture" OR "shrimp farm*")
        ) 	
  OR  
      (
        ("harbour$" OR "port" OR "ports")  
        AND  ("sea" OR "seas" OR "coast*" OR "gulf" OR "ship*" OR "maritime") 
      )  
  OR "maritime" 	
)  
```

#### Polar ice and sea

```Ceylon =
TS=
(
  "sea ice" OR "ice floe$" OR "pack ice" OR "polynya$" OR "ice stream$" OR "ice shel*" OR "nilas" 
  OR "ice chart$" OR "iceberg$" OR "pancake ice" OR "ice ridge$" 
  OR "sea level$" OR "sea surface" OR "SST" 
  OR "air sea"
) 
```

#### Polar areas, ice and sea

Restricted in combination with ice, the sea or oil - i.e. must be polar research about polar oceans, sea-ice, glaciers, ice caps, oil drilling etc. 
Some of the islands are so small that nearly everything about them will be marine related, these are not combined. 

```Ceylon =
TS=
(
   "bear island" OR "bjørnøya" OR "jan mayan" OR "yermak plateau" OR "franz josef land" 
   OR "south orkneys" OR "south shetlands" OR "south sandwich islands" OR "bouvet island" 
   OR "kergelen island" OR "McDonald Islands" OR "Balleny island$" OR "Scott island" 
   OR 
    ( 
      ("arctic" OR "antarctica" OR "north pole" OR "south pole" OR "polar" 
      OR "high north" OR "high latitude" OR "svalbard" OR "spitsbergen" OR "greenland" 
      OR "north alaska" OR "northern quebec" OR "northwest territories" OR "prince edward island" 
      OR "axel heiberg" OR "alaska north slope" OR "prudhoe bay" OR "utqiagvik" OR "zemlya" OR "south georgia"
      ) 
      AND ("glacier$" OR "ice" OR "oil" OR "petroleum")
    ) 
) 
```

#### Miscellaneous phrase

Biodiversity, SDG14, oil spills

```Ceylon =
TS=
( 
  (
    ("biodivers*" OR "biological diversity") 
    NEAR/3 ("beyond national jurisdiction" OR "beyond areas of national jurisdiction" OR "ABNJ") 
  ) 
  OR "BBNJ" 
  OR "SDG14" OR "SDG 14" OR ("SDG" AND "life below water") 
  OR "oil spill$"
)  
```

#### Shipping and offshore

```Ceylon =
TS=
( "shipping" OR "container ship$" OR "rov" OR "auv" 
  OR ("underwater" NEAR/15 ("vehicle$" OR "robot$")) 
  OR "surface vessel$" OR "deep water" OR "subsea" OR "submersible" OR "moonpool" 
  OR "lifeboat$" OR "sailboat$" OR "seaport$" OR "wave energy conver*" 
) 
OR 
TS=
( 
  (
    ("vessel$" OR "hull" OR "ship$" OR "deep water") 
    AND ("disabled" OR "design" OR "naval" OR "fleet$" OR "harbour$" OR "navigat*" OR "routing" OR "route$" 
        OR "fouling" OR "biofouling" OR "ice interaction*" OR "collision$" OR "autonomous" OR "safety" OR "technolog*"
        ) 
  )
  NOT ("research vessel" OR "coronary" OR "cardiac" OR "blood" OR "stroke$" OR "aneurysm$" OR "*vascular" or "xylem") 
) 
OR 
TS=
(  "floating" 
   NEAR/5 ("storage" OR "bodies" OR "structure$" OR "turbine$" OR "drift") 
) 
OR 
TS=
(  "mooring" 
   NEAR/5 ("line$" OR "system$" OR "safety" OR "force$" OR "point" OR "multipoint" OR "floating" OR "chain$") 
) 
OR
TS=
(  "offshore" 
   AND ("oil" OR "petroleum" OR "pipe*" OR "drilling" 
       OR "turbine$" OR "offshore wind" 
       OR "structure$" OR "platform$" OR "installation$" OR "cylinder$" OR "monopile$" OR "anchor*" OR "mooring$" 
       OR "vessel$" OR "ship$" 
       OR "technolog*" OR "algorithm$" 
       OR "operations" OR "occupational safety" OR "occupational health" 
       OR "CO2" OR "winds" OR "basin" 
       ) 
)
```




## Maritim forskning

The string for marine should also contain all terms for maritime - don't add to maritime without adding to marine. 
It does however contain some additional terms as *limitations* of more general terms in the marine string. 
For example, "ocean" must be combined with "technology"; fishing and aquaculture terms must be used in combination with technology or safety terms. 

```Ceylon =

```


