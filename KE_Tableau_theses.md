# Energiomstilling

String to use against an export from BORA to identify master and PhD theses related to energy transitions (energiomstilling). Exported from BORA via API. 

Search string and terms discussed with director for KE (KGF) january 2024. 

The string covers the following groups:
- Ammonia
- Bioenergy/biofuels/biogas
- CCS
- Energy system/transition/mix/policy
- Energy efficiency
- Geothermal
- Hydrogen
- Hydropower
- Nuclear
- Ocean/wave energy
- Offshore wind
- Power grid/batteries
- Renewable energy
- Solar
- Wind
- Zero emissions

## Search string
Some terms are combined with other terms (e.g. energy, renewable) to avoid noise. Some are not but seem to work ok on this limited dataset - they would likely be problematic in other, larger datasets (e.g. "hydrogen"). 

```py
IF CONTAINS(LOWER([Abstract]), "ammonia")
OR CONTAINS(LOWER([Subject]), "ammonia")
OR CONTAINS(LOWER([Name]), "ammonia")
THEN "Ammonia"

ELSEIF
CONTAINS(LOWER([Abstract]), "bioenergy")
OR CONTAINS(LOWER([Subject]), "bioenergy")
OR CONTAINS(LOWER([Name]), "bioenergy")
OR CONTAINS(LOWER([Abstract]), "bioenergi")
OR CONTAINS(LOWER([Subject]), "bioenergi")
OR CONTAINS(LOWER([Name]), "bioenergi")
OR CONTAINS(LOWER([Abstract]), "bio-oil")
OR CONTAINS(LOWER([Subject]), "bio-oil")
OR CONTAINS(LOWER([Name]), "bio-oil")
OR CONTAINS(LOWER([Abstract]), "bioolje")
OR CONTAINS(LOWER([Subject]), "bioolje")
OR CONTAINS(LOWER([Name]), "bioolje")

OR CONTAINS(LOWER([Abstract]), "bio-fuel")
OR CONTAINS(LOWER([Subject]), "bio-fuel")
OR CONTAINS(LOWER([Name]), "bio-fuel")
OR CONTAINS(LOWER([Abstract]), "biofuel")
OR CONTAINS(LOWER([Subject]), "biofuel")
OR CONTAINS(LOWER([Name]), "biofuel")
OR CONTAINS(LOWER([Abstract]), "bio fuel")
OR CONTAINS(LOWER([Subject]), "bio fuel")
OR CONTAINS(LOWER([Name]), "bio fuel")
OR CONTAINS(LOWER([Abstract]), "biodrivstoff")
OR CONTAINS(LOWER([Subject]), "biodrivstoff")
OR CONTAINS(LOWER([Name]), "biodrivstoff")

OR CONTAINS(LOWER([Abstract]), "biogas")
OR CONTAINS(LOWER([Subject]), "biogas")
OR CONTAINS(LOWER([Name]), "biogas")
THEN "Bioenergy/fuel/gas"

ELSEIF
CONTAINS(LOWER([Abstract]), "CCS")
OR CONTAINS(LOWER([Subject]), "CCS")
OR CONTAINS(LOWER([Name]), "CCS")
OR CONTAINS(LOWER([Abstract]), "CCUS")
OR CONTAINS(LOWER([Subject]), "CCUS")
OR CONTAINS(LOWER([Name]), "CCUS")
OR CONTAINS(LOWER([Abstract]), "carbon capture and storage")
OR CONTAINS(LOWER([Subject]), "carbon capture and storage")
OR CONTAINS(LOWER([Name]), "carbon capture and storage")
OR CONTAINS(LOWER([Abstract]), "karbonfangst og lagring")
OR CONTAINS(LOWER([Subject]), "karbonfangst og lagring")
OR CONTAINS(LOWER([Name]), "karbonfangst og lagring")
OR CONTAINS(LOWER([Abstract]), "CO2 capture")
OR CONTAINS(LOWER([Subject]), "CO2 capture")
OR CONTAINS(LOWER([Name]), "CO2 capture")
OR CONTAINS(LOWER([Abstract]), "CO2 storage")
OR CONTAINS(LOWER([Subject]), "CO2 storage")
OR CONTAINS(LOWER([Name]), "CO2 storage")
OR CONTAINS(LOWER([Abstract]), "CO2 lagring")
OR CONTAINS(LOWER([Subject]), "CO2 lagring")
OR CONTAINS(LOWER([Name]), "CO2 lagring")
THEN "Carbon capture and storage"

ELSEIF
CONTAINS(LOWER([Abstract]), "energy system")
OR CONTAINS(LOWER([Subject]), "energy system")
OR CONTAINS(LOWER([Name]), "energy system")
OR CONTAINS(LOWER([Abstract]), "energisystem")
OR CONTAINS(LOWER([Subject]), "energisystem")
OR CONTAINS(LOWER([Name]), "energisystem")
OR CONTAINS(LOWER([Abstract]), "kraftsystem")
OR CONTAINS(LOWER([Subject]), "kraftsystem")
OR CONTAINS(LOWER([Name]), "kraftsystem")
OR CONTAINS(LOWER([Abstract]), "energy polic")
OR CONTAINS(LOWER([Subject]), "energy polic")
OR CONTAINS(LOWER([Name]), "energy polic")
OR CONTAINS(LOWER([Abstract]), "energipoli")
OR CONTAINS(LOWER([Subject]), "energipoli")
OR CONTAINS(LOWER([Name]), "energipoli")

OR CONTAINS(LOWER([Abstract]), "småkraftverk")
OR CONTAINS(LOWER([Subject]), "småkraftverk")
OR CONTAINS(LOWER([Name]), "småkraftverk")
OR CONTAINS(LOWER([Abstract]), "local energy")
OR CONTAINS(LOWER([Subject]), "local energy")
OR CONTAINS(LOWER([Name]), "local energy")
OR CONTAINS(LOWER([Abstract]), "lokal energi")
OR CONTAINS(LOWER([Subject]), "lokal energi")
OR CONTAINS(LOWER([Name]), "lokal energi")

OR CONTAINS(LOWER([Abstract]), "energiomstilling")
OR CONTAINS(LOWER([Subject]), "energiomstilling")
OR CONTAINS(LOWER([Name]), "energiomstilling")
OR CONTAINS(LOWER([Abstract]), "energy transition")
OR CONTAINS(LOWER([Subject]), "energy transition")
OR CONTAINS(LOWER([Name]), "energy transition")
OR CONTAINS(LOWER([Abstract]), "energy transformation")
OR CONTAINS(LOWER([Subject]), "energy transformation")
OR CONTAINS(LOWER([Name]), "energy transformation")

OR CONTAINS(LOWER([Abstract]), "energy mix")
OR CONTAINS(LOWER([Subject]), "energy mix")
OR CONTAINS(LOWER([Name]), "energy mix")
OR CONTAINS(LOWER([Abstract]), "energimix")
OR CONTAINS(LOWER([Subject]), "energimix")
OR CONTAINS(LOWER([Name]), "energimix")

OR
((
CONTAINS(LOWER([Name]), "klimapolitikk")
OR CONTAINS(LOWER([Subject]), "klimapolitikk")
OR CONTAINS(LOWER([Abstract]), "klimapolitikk")
OR CONTAINS(LOWER([Name]), "climate poli")
OR CONTAINS(LOWER([Subject]), "climate poli")
OR CONTAINS(LOWER([Abstract]), "climate poli")
OR CONTAINS(LOWER([Name]), "grønt skifte")
OR CONTAINS(LOWER([Subject]), "grønt skifte")
OR CONTAINS(LOWER([Abstract]), "grønt skifte")
OR CONTAINS(LOWER([Name]), "grønne skifte")
OR CONTAINS(LOWER([Subject]), "grønne skifte")
OR CONTAINS(LOWER([Abstract]), "grønne skifte")
OR CONTAINS(LOWER([Name]), "green trans")
OR CONTAINS(LOWER([Subject]), "green trans")
OR CONTAINS(LOWER([Abstract]), "green trans")
)
AND 
(CONTAINS(LOWER([Name]), "energy")
OR CONTAINS(LOWER([Subject]), "energy")
OR CONTAINS(LOWER([Abstract]), "energy")
OR CONTAINS(LOWER([Name]), "energi")
OR CONTAINS(LOWER([Subject]), "energi")
OR CONTAINS(LOWER([Abstract]), "energi")
OR CONTAINS(LOWER([Name]), "fornybar")
OR CONTAINS(LOWER([Subject]), "fornybar")
OR CONTAINS(LOWER([Abstract]), "fornybar")
OR CONTAINS(LOWER([Name]), "renewable")
OR CONTAINS(LOWER([Subject]), "renewable")
OR CONTAINS(LOWER([Abstract]), "renewable")
))
THEN "Energy system/transition/mix"

ELSEIF CONTAINS(LOWER([Abstract]), "energy efficien")
OR CONTAINS(LOWER([Subject]), "energy efficien")
OR CONTAINS(LOWER([Name]), "energy efficien")
OR CONTAINS(LOWER([Abstract]), "energieffektiv")
OR CONTAINS(LOWER([Subject]), "energieffektiv")
OR CONTAINS(LOWER([Name]), "energieffektiv")
OR CONTAINS(LOWER([Abstract]), "energy suffici")
OR CONTAINS(LOWER([Subject]), "energy suffici")
OR CONTAINS(LOWER([Name]), "energy suffici")
THEN "Energy efficiency"

ELSEIF((CONTAINS(LOWER([Subject]), "geotherm")
OR CONTAINS(LOWER([Name]), "geotherm"))
AND 
(CONTAINS(LOWER([Name]), "energ")
OR CONTAINS(LOWER([Subject]), "energ"))
)
OR CONTAINS(LOWER([Abstract]), "geothermal energy")
OR CONTAINS(LOWER([Abstract]), "geothermisk energi")
THEN "Geothermal energy"

ELSEIF CONTAINS(LOWER([Abstract]), "hydrogen")
OR CONTAINS(LOWER([Subject]), "hydrogen")
OR CONTAINS(LOWER([Name]), "hydrogen")
THEN "Hydrogen"

ELSEIF CONTAINS(LOWER([Abstract]), "vannkraft")
OR CONTAINS(LOWER([Subject]), "vannkraft")
OR CONTAINS(LOWER([Name]), "vannkraft")
OR CONTAINS(LOWER([Abstract]), "vasskraft")
OR CONTAINS(LOWER([Subject]), "vasskraft")
OR CONTAINS(LOWER([Name]), "vasskraft")
OR CONTAINS(LOWER([Abstract]), "hydropower")
OR CONTAINS(LOWER([Subject]), "hydropower")
OR CONTAINS(LOWER([Name]), "hydropower")
OR CONTAINS(LOWER([Abstract]), "hydro-power")
OR CONTAINS(LOWER([Subject]), "hydro-power")
OR CONTAINS(LOWER([Name]), "hydro-power")
OR CONTAINS(LOWER([Abstract]), "hydroelectric")
OR CONTAINS(LOWER([Subject]), "hydroelectric")
OR CONTAINS(LOWER([Name]), "hydroelectric")
THEN "Hydropower"

ELSEIF CONTAINS(LOWER([Abstract]), "nuclear power")
OR CONTAINS(LOWER([Subject]), "nuclear power")
OR CONTAINS(LOWER([Name]), "nuclear power")
OR CONTAINS(LOWER([Abstract]), "nuclear reactor")
OR CONTAINS(LOWER([Subject]), "nuclear reactor")
OR CONTAINS(LOWER([Name]), "nuclear reactor")
OR CONTAINS(LOWER([Abstract]), "kjernekraft")
OR CONTAINS(LOWER([Subject]), "kjernekraft")
OR CONTAINS(LOWER([Name]), "kjernekraft")
THEN "Nuclear"

ELSEIF CONTAINS(LOWER([Abstract]), "ocean energy")
OR CONTAINS(LOWER([Subject]), "ocean energy")
OR CONTAINS(LOWER([Name]), "ocean energy")
OR CONTAINS(LOWER([Abstract]), "havenergi")
OR CONTAINS(LOWER([Subject]), "havenergi")
OR CONTAINS(LOWER([Name]), "havenergi")
OR CONTAINS(LOWER([Abstract]), "bølgekraft")
OR CONTAINS(LOWER([Name]), "bølgekraft")
OR CONTAINS(LOWER([Subject]), "bølgekraft")
OR 
((CONTAINS(LOWER([Name]), "wave energy")
OR CONTAINS(LOWER([Subject]), "wave energy")
OR CONTAINS(LOWER([Abstract]), "wave energy"))
AND (CONTAINS(LOWER([Name]), "power")
OR CONTAINS(LOWER([Subject]), "power")
OR CONTAINS(LOWER([Abstract]), "power")))
THEN "Ocean/wave energy"

ELSEIF CONTAINS(LOWER([Abstract]), "offshore wind")
OR CONTAINS(LOWER([Subject]), "offshore wind")
OR CONTAINS(LOWER([Name]), "offshore wind")
OR CONTAINS([Abstract], "havvind")
OR CONTAINS(LOWER([Subject]), "havvind")
OR CONTAINS(LOWER([Name]), "havvind")
THEN "Offshore wind"

ELSEIF CONTAINS(LOWER([Abstract]), "power grid")
OR CONTAINS(LOWER([Subject]), "power grid")
OR CONTAINS(LOWER([Name]), "power grid")
OR CONTAINS(LOWER([Abstract]), "kraftlinj")
OR CONTAINS(LOWER([Subject]), "kraftlinj")
OR CONTAINS(LOWER([Name]), "kraftlinj")
OR CONTAINS(LOWER([Abstract]), "strømkabler")
OR CONTAINS(LOWER([Subject]), "strømkabler")
OR CONTAINS(LOWER([Name]), "strømkabler")
OR CONTAINS(LOWER([Abstract]), "mikrogrid")
OR CONTAINS(LOWER([Subject]), "mikrogrid")
OR CONTAINS(LOWER([Name]), "mikrogrid")
OR CONTAINS(LOWER([Abstract]), "microgrid")
OR CONTAINS(LOWER([Subject]), "microgrid")
OR CONTAINS(LOWER([Name]), "microgrid")
OR CONTAINS(LOWER([Abstract]), "DC-grid")
OR CONTAINS(LOWER([Subject]), "DC-grid")
OR CONTAINS(LOWER([Name]), "DC-grid")
OR CONTAINS(LOWER([Abstract]), "energy storage device")
OR CONTAINS(LOWER([Subject]), "energy storage device")
OR CONTAINS(LOWER([Name]), "energy storage device")
OR CONTAINS(LOWER([Abstract]), "batterier")
OR CONTAINS(LOWER([Subject]), "batterier")
OR CONTAINS(LOWER([Name]), "batterier")
OR CONTAINS(LOWER([Abstract]), "batteries")
OR CONTAINS(LOWER([Subject]), "batteries")
OR CONTAINS(LOWER([Name]), "batteries")
THEN "Power grid/batteries"

ELSEIF((CONTAINS(LOWER([Subject]), "renewable")
OR CONTAINS(LOWER([Name]), "renewable")
OR CONTAINS(LOWER([Subject]), "fornybar")
OR CONTAINS(LOWER([Name]), "fornybar"))
AND 
(CONTAINS(LOWER([Name]), "energ")
OR CONTAINS(LOWER([Subject]), "energ")
OR CONTAINS(LOWER([Name]), "kraft")
OR CONTAINS(LOWER([Subject]), "kraft")))
OR CONTAINS(LOWER([Abstract]), "renewable energ")
OR CONTAINS(LOWER([Abstract]), "fornybar energi")
OR CONTAINS(LOWER([Abstract]), "fornybar kraft")
OR CONTAINS(LOWER([Subject]), "green energy")
OR CONTAINS(LOWER([Name]), "green energy")
OR CONTAINS(LOWER([Abstract]), "green energy")
OR CONTAINS(LOWER([Subject]), "grønn energi")
OR CONTAINS(LOWER([Name]), "grønn energi")
OR CONTAINS(LOWER([Abstract]), "grønn energi")
THEN "Renewable energy"

ELSEIF((CONTAINS(LOWER([Subject]), "solar")
OR CONTAINS(LOWER([Name]), "solar"))
AND 
(CONTAINS(LOWER([Name]), "energ")
OR CONTAINS(LOWER([Subject]), "energ")
OR CONTAINS(LOWER([Name]), "panel")
OR CONTAINS(LOWER([Subject]), "panel")
OR CONTAINS(LOWER([Name]), "pv")
OR CONTAINS(LOWER([Subject]), "pv")
OR CONTAINS(LOWER([Name]), "photovolta")
OR CONTAINS(LOWER([Subject]), "photovolta")
OR CONTAINS(LOWER([Name]), "collector")
OR CONTAINS(LOWER([Subject]), "collector"))
)
OR CONTAINS(LOWER([Abstract]), "solcell")
OR CONTAINS(LOWER([Abstract]), "solar panel")
OR CONTAINS(LOWER([Abstract]), "solar pv")
OR CONTAINS(LOWER([Abstract]), "solar collector")
OR CONTAINS(LOWER([Abstract]), "solfanger")
OR CONTAINS(LOWER([Name]), "solfanger")
OR CONTAINS(LOWER([Subject]), "solfanger")
OR CONTAINS(LOWER([Abstract]), "solar cell")
OR CONTAINS(LOWER([Name]), "solar cell")
OR CONTAINS(LOWER([Subject]), "solar cell")
THEN "Solar"

ELSEIF CONTAINS(LOWER([Abstract]), "wind energy")
OR CONTAINS(LOWER([Subject]), "wind energy")
OR CONTAINS(LOWER([Name]), "wind energy")
OR CONTAINS(LOWER([Abstract]), "wind power")
OR CONTAINS(LOWER([Subject]), "wind power")
OR CONTAINS(LOWER([Name]), "wind power")
OR CONTAINS(LOWER([Abstract]), "vindkraft")
OR CONTAINS(LOWER([Subject]), "vindkraft")
OR CONTAINS(LOWER([Name]), "vindkraft")
OR CONTAINS(LOWER([Abstract]), "wind turbine")
OR CONTAINS(LOWER([Subject]), "wind turbine")
OR CONTAINS(LOWER([Name]), "wind turbine")
OR CONTAINS(LOWER([Abstract]), "vindturbin")
OR CONTAINS(LOWER([Subject]), "vindturbin")
OR CONTAINS(LOWER([Name]), "vindturbin")
OR CONTAINS(LOWER([Abstract]), "wind farm")
OR CONTAINS(LOWER([Subject]), "wind farm")
OR CONTAINS(LOWER([Name]), "wind farm")
THEN "Wind energy"

ELSEIF CONTAINS(LOWER([Abstract]), "zero emission")
OR CONTAINS(LOWER([Subject]), "zero emission")
OR CONTAINS(LOWER([Name]), "zero emission")
OR CONTAINS(LOWER([Abstract]), "null utslipp")
OR CONTAINS(LOWER([Subject]), "null utslipp")
OR CONTAINS(LOWER([Name]), "null utslipp")
OR CONTAINS(LOWER([Abstract]), "nullutslipp")
OR CONTAINS(LOWER([Subject]), "nullutslipp")
OR CONTAINS(LOWER([Name]), "nullutslipp")
THEN "Zero emission"

Else "non"
END
```
