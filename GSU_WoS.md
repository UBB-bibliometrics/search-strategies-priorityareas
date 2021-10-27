#GSU

## Global health

#### Climate change/disasters and health

```
TS=
(
  (
    ("climate change" OR "global warming" OR "sustainable development" OR "disaster" OR "flood*" OR "drought" OR "tsunami") 
    AND 
    ("health" OR "wellbeing" OR "well-being" OR "medical" OR "healthcare")
   ) 
   NOT 
    (
      ("land health" OR "soil health" OR "grassland health" OR "forest health" OR "vegetation health" OR "ocean health" OR "ecosystem health") 
      NOT 
      ("human health" OR "public health" OR "mental health" OR "healthcare" OR "health care" OR "medical" OR "wellbeing" OR "well-being")
    )
 )

```

#### Diseases/health issues prevalent in LMCs and neglected tropical diseases

Not combined with any countries

```
TS =
(
    "maternal mortality" OR "child mortality" OR "infant mortality"
    OR
    (
      ("water borne" OR "waterborne" OR "water-borne" OR "water-related")
      NEAR/5
          ("disease$" OR "infection$" OR "epidemic$" OR "illness*")
    )
    OR "acquired immune deficiency syndrome" OR "acquired immuno-deficiency syndrome"  OR "acquired immunodeficiency syndrome" OR "Human Immunodeficiency Virus" OR "HIV"
    OR "tuberculosis"
    OR "malaria"
    OR "polio*"

    OR "cholera"
    OR "giardiasis" OR "giardia infection$"
    OR "typhoid"
    OR "diarrheal disease$"

    OR "neglected tropical disease$"
    OR "buruli ulcer"
    OR "chagas"
    OR "dengue"
    OR "chikungunya"
    OR "dracunculiasis" OR "guinea-worm disease"
    OR "echinococcosis"
    OR "foodborne trematodiases"
    OR "human african trypanosomiasis" OR "sleeping sickness"
    OR "leishmaniasis"
    OR "leprosy"
    OR "lymphatic filariasis"
    OR "mycetoma" OR "chromoblastomycosis" OR "deep mycoses"
    OR "onchocerciasis" OR "river blindness"
    OR "rabies"
    OR "scabies"
    OR "schistosomiasis"
    OR "soil-transmitted helminthiases"
    OR "snakebite envenoming"
    OR "taeniasis" OR "cysticercosis"
    OR "trachoma"
    OR "yaws"
)
```
