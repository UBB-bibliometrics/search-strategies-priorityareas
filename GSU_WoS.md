# GSU

## Global health

#### Global health

```
TS=
("global health" OR "international health" OR "global mental health"
)

```

#### Climate change/disasters and health

The double `NOT` statement removes papers talking about ecological health provided that they do not also mention human health.

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

Not combined with any countries. Adapted from SDG3 search. 

HIV, polio, malaria, TB, waterborne diseases and maternal/infant mortality are included as they are major in LMCs, even though they can also occur elsewhere.

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

#### General health terms, combined with LMCs

`health` and `medical` covers health care, services, education, rights, workers, coverage, sexual/mental/occupational health. However, as "health" can be used in other fields (ecosystem health), specific terms are included in the first phrase, while "health" generally is combined with human terms. 
`disease` covers a number of categories of disease (e.g. communicable disease), but these are occasionally duplicated anyway.
`therapy` covers various types (art, music, medicinal)

Specific diseases added from SDG3

List of countries includes all except high-income countries.

```
TS=
(
  (
    ("health education" OR "health polic*" OR "health organization$" OR "health service$"
    OR "health equity" OR "right to health*" OR "health rights" OR "health coverage" OR "health governance"
    OR "reproductive health" OR "sexual health" OR "mental health"
    OR "medical" OR "wellbeing" OR "well-being" OR "SDG 3"

    OR	"disease$" OR "infection$" OR "illness*" OR "mortality" OR "morbidity"
    OR	"trauma"  
    OR	"cancer$" OR "neoplasm$" 
    OR "diabetes"
    OR "chronic respiratory disease$" 
    OR "cancer$" OR "*sarcoma" OR "sarcoma$" OR "*carcinoma" OR "carcinoma$" OR "*blastoma" OR "blastoma$" OR "myeloma$" OR "lymphoma$" OR "leukaemia" OR "leukemia" OR "mesothelioma$" OR "melanoma$"  
    OR	"asthma" OR "chronic obstructive pulmonary disease$" OR "COPD" OR "chronic obstructive airway disease$" OR "chronic bronchitis" OR "emphysema" OR	"pneumonia"
    OR	"diabetes"
    OR  "cardiovascular disease$" OR "heart disease" OR "heart attack$" OR "stroke$"
    OR	"dust exposure"
    OR	"diarrhea*"
    OR  "WASH facilities"
    
    OR "sexually transmitted disease$" OR "sexually transmitted infection$"
    OR "syphilis"
    
    OR "coronavirus"
    OR "covid"
    OR "hepatitis"
    OR "acquired immune deficiency syndrome" OR "acquired immuno-deficiency syndrome"  OR "acquired immunodeficiency syndrome" OR "Human Immunodeficiency Virus" OR "HIV"
    OR "tuberculosis"
    OR "malaria"
    OR "cholera"
    OR "meningitis"
    OR "influenza"
    OR "rubella"
    OR "diphtheria"
    OR "japanese encephalitis"
    OR "measles"
    OR "mumps"
    OR "tetanus"
    OR "pertussis"
    OR "polio*"
    OR "yellow fever"

    OR	"vaccine$" OR "vaccinat*" OR "medicine$" OR "therapy" OR "therapies" 

    OR  "clinic$" OR "hospital$" OR "healthcare" OR "residential care"
    OR  "patient care"
    OR	"dentist$" OR "dental"
    OR	"surgery" OR "surgeon$"
    OR  "therapist$" OR "counselling"
    OR	"psycholog*" OR	"psychiat*"
    OR	"orthopedic$"
    OR  "health worker$" OR "health professional$" OR "health practitioner$"
    OR "nurse$" OR "doctor$" OR "physician$" OR "surgeon$" OR "midwife*" OR "midwives" OR "gynecologist$"
    OR "Anesthetist$" OR "Audiologist$" OR "Doula$" OR "Emergency Medical Dispatcher$" OR "Health Educator$"
    OR "Health Facility Administrator$" OR "Infection Control Practitioner$" 
    OR "Nutritionist$" OR "Optometrist$" OR "Pharmacist$" OR "Allergist$" OR "Anesthesiologist$"
    OR "Cardiologist$" OR "Dermatologist$" OR "Endocrinologist$" OR "Gastroenterologist$" 
    OR "General Practitioner$" OR "Geriatrician$" OR "Hospitalist$" OR "Nephrologist$" OR "Neurologist$"
    OR "Oncologist$" OR "Ophthalmologist$" OR "Otolaryngologist$" OR "Pathologist$" 
    OR "Pediatrician$" OR "Physiatrist$" OR "physiotherapist$" OR "Pulmonologist$" OR "Radiologist$" OR "Rheumatologist$" OR "Urologist$"

    OR	"obstetric$" OR	"childbirth" OR	"childbear*" 
    OR  "breastfeed*" OR	"birthweight"
    OR	"perinatal" OR "postnatal" OR	"antenatal" OR "prenatal"
    OR	"abortion*" OR "pregnan*"

    OR	"sex education" OR "family planning"

    OR	"disability" OR "disabled people*" OR "disabled child*"

    OR	"konzo" OR "marasmus" OR "kwashiorkor"

    OR	"child development"
    OR	"developmental disorder$"
    OR  "cognative decline"
    OR	"risk behavi*"
    OR	"suicid*" OR "self-harm"
    OR  "depression" OR "anxiety"
    OR 	"intimate partner violence"
    OR	"tombak" 
    OR	(("injury" OR "injuries" OR "accident$") NEAR/3 ("workplace" OR "occupation*" OR "traffic" OR "car" OR "road$"))
    OR	"alcoholism"
    OR	"binge drink*"
    OR	"addiction"
    OR
      (
        ("drug$" OR "narcotic$" OR "narcotic$" OR "substance"
        OR "alcohol"
        OR "amphetamine$" OR "methamphetamine$"
        OR "cocaine"
        OR "inhalant$"
        OR "marijuana" OR "cannabis"
        OR "opioid$" OR "opiate$" OR "heroin" OR "morphine"
        OR "phencyclidine" OR "LSD" OR "psilocybin" OR "dimethyltriptamine"
        OR "khat"
        OR "tobacco" OR "secondhand smok*" OR "second hand smok*" OR "involuntary smoking" OR "passive smoking"
        )
        NEAR/3
            ("abuse" OR "misuse" OR "harmful use*" OR "use disorder$" OR "dependence" OR "addict*" OR "overdose$")    
      )
    )
  OR
    (
      (   "health" 
      OR  "epidemic$" OR "pandemic$"
      OR  "antimalarial$" OR "antiviral$" OR "antibiotic$" OR "antiparasitic$"
      OR  "nutrition*" OR "malnutrition" OR "malnourish*" OR "vitamin$" OR "micronutrient$"
      OR  "toxicology" OR "aflatoxin" OR "accidental poisoning$" OR "mercury"
      OR  "hazardous chemical$" OR "hazardous material$" OR "hazardous substance$" 
      OR  "arsenic" OR "asbestos" OR "benzene" OR "cadmium" OR "dioxin$" OR "mercury" OR "fluoride" OR "pesticide$"
      OR  "lead poison*" OR "lead *toxicity" OR "lead mediated *toxicity" OR "lead induced *toxicity" OR "lead exposure" OR "lead carcinogen*" OR "blood lead"
      OR  "sanitation" OR "drinking water" OR "potable water"
      )
    AND
      ( "humans" OR "humanity" OR "human" OR "people" OR "person$"
        OR "children" OR "child" OR "infant$" OR "babies"
        OR "adult$" OR "women" OR "men" OR "woman" OR "man" OR "girls" OR "boys"
        OR "rural" OR "urban" OR "city" OR "cities" OR "town$" OR "village$" OR "countr*" OR "nation$" OR "develop* state$"
        OR "patient$" OR "hospital*" OR "health care" OR "healthcare"
        OR "premature death$" OR "premature mortality"
      )
    )
  )
AND
  ("afghanistan"	OR
  "angola" 	OR
  "antigua" 	OR
  "bahrain" 	OR
  "bangladesh" 	OR
  "barbados" 	OR
  "belize" 	OR
  "benin" 	OR
  "bermuda" 	OR
  "bhutan" 	OR
  "burkina faso" 	OR
  "burundi" 	OR
  "cabo verde" 	OR
  "cambodia" 	OR
  "chad" 	OR
  "marianas" 	OR
  "comoros" 	OR
  "congo" 	OR
  "cuba" 	OR
  "djibouti" 	OR
  "dominica" 	OR
  "eritrea" 	OR
  "ethiopia" 	OR
  "micronesia" 	OR
  "fiji" 	OR
  "french polynesia" 	OR
  "gambia" 	OR
  "grenada" 	OR
  "guadeloupe" 	OR
  "guyana" 	OR
  "haiti" 	OR
  "jamaica" 	OR
  "kiribati" 	OR
  "laos" 	OR
  "lesotho" 	OR
  "liberia" 	OR
  "madagascar" 	OR
  "malawi" 	OR
  "maldives" 	OR
  "mali" 	OR
  "marshall islands" 	OR
  "martinique" 	OR
  "mauritania" 	OR
  "mauritius" 	OR
  "montserrat" 	OR
  "mozambique" 	OR
  "myanmar" 	OR
  "nauru" 	OR
  "nepal" 	OR
  "new caledonia" 	OR
  "niger" 	OR
  "niue" 	OR
  "papua new guinea" 	OR
  "rwanda" 	OR
  "saint lucia" 	OR
  "grenadines" 	OR
  "la reunion" 	OR
  "samoa" 	OR
  "sao tome" 	OR
  "senegal" 	OR
  "sierra leone" 	OR
  "solomon islands" 	OR
  "somalia" 	OR
  "sudan" 	OR
  "suriname" 	OR
  "tanzania" 	OR
  "timor leste" 	OR
  "togo" 	OR
  "tonga" 	OR
  "tuvalu" 	OR
  "uganda" 	OR
  "vanuatu" 	OR
  "yemen" 	OR
  "zambia" 	OR
	
  "africa" 	OR
  "nigeria"	OR
  "egypt"	OR
  "kenya"	OR
  "algeria"	OR
  "morocco"	OR
  "ghana"	OR
  "ivory coast"	OR
  "cameroon"	OR
  "zimbabwe"	OR
  "tunisia"	OR
  "libya"	OR
  "botswana"	OR
  "gabon"	OR
  "equatorial guinea"	OR
  "eswatini"	OR
  "cape verde"	OR
  "western sahara"	OR
  "mayotte"	OR
	
  "albania"	OR
  "argentina"	OR
  "armenia"	OR
  "azerbaijan"	OR
  "belarus"	OR
  "bolivia"	OR
  "bosnia"	OR
  "brazil"	OR
  "bulgaria"	OR
  "china"	OR
  "colombia"	OR
  "costa rica"	OR
  "ecuador"	OR
  "el salvador"	OR
  "guatemala"	OR
  "honduras"	OR
  "india"	OR
  "indonesia"	OR
  "iran"	OR
  "iraq"	OR
  "jordan"	OR
  "kazakhstan"	OR
  "kosovo"	OR
  "kyrgyz"	OR
  "lebanon"	OR
  "malaysia"	OR
  "mexico"	OR
  "micronesia"	OR
  "moldova"	OR
  "mongolia"	OR
  "montenegro"	OR
  "nicaragua"	OR
  "macedonia"	OR
  "pakistan"	OR
  "paraguay"	OR
  "phillipines"	OR
  "peru"	OR
  "romania"	OR
  "russia"	OR
  "serbia"	OR
  "sri lanka"	OR
  "syria"	OR
  "tajikistan"	OR
  "thailand"	OR
  "turkey"	OR
  "turkmenistan"	OR
  "ukraine"	OR
  "venezuela"	OR
  "vietnam"	OR
  "west bank"	OR
  " gaza"
  )
)  
```
