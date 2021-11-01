# GSU

## Global health

#### Global health

``` Ceylon =
TS=
("global health" OR "international health" OR "global mental health"
)

```

#### Climate change/disasters and health

This is tricky as many papers talk about ecological/plant/animal health.

``` Ceylon =
TS=
(
  (
    ("climate change" OR "global warming" OR "sustainable development" OR "disaster$" OR "flood*" OR "drought$" OR "tsunami$")
    AND
    ("wellbeing" OR "well-being"
    OR "medical" OR "healthcare" OR "health care" OR "health sector" OR "hospital$" OR "intensive care" OR "essential medic*"
    OR "human health" OR "public health" OR "health promotion"
    OR "mental health" OR "psychosocial health"
    OR "workplace health" OR "occupational health"
    OR "global health" OR "social determinants of health" OR "health equity" OR "equity and health" OR "health for all"
    OR "child health"
    )
  )
  OR
  (
    ("climate change" OR "global warming" OR "sustainable development" OR "disaster$" OR "flood*" OR "drought$" OR "tsunami$")
    AND
    (	"health"
    	AND
	("children" OR "child" OR "youth" OR "adolescent$" OR "women" OR "girls" OR "men" OR "boys" OR "the elderly" OR "human$"
	OR "equity" OR "justice"
	OR "patient$" OR "victim$" OR "survivor$"
	)
    )
  )
)
```

``` Ceylon =
TS = 	("climate change" OR "global warming" OR "sustainable development" OR "disaster$" OR "flood*" OR "drought$" OR "tsunami$")
AND
WC = 	("Public Environmental Occupational Health" OR "medicine general internal" OR "health care sciences services" OR "health policy services" OR "psychiatry" OR "nursing" OR "emergency medicine" OR "pediatrics" OR "social sciences biomedical" OR "psychology clinical" OR "psychology multidisciplinary" OR "social work" OR "obstetrics gynecology")
```

The double NOT removes those talking about animal health which do not also talk about human health.

``` Ceylon =
(
   TS= 	("climate change" OR "global warming" OR "sustainable development" OR "disaster$" OR "flood*" OR "drought$" OR "tsunami$")
   AND
   TI= 	("health")
)
NOT
(  
   TS= 	("land health" OR "soil health" OR "grassland health" OR "forest health" OR "woodland health" OR "plant health" OR "vegetation health" OR "ocean health" OR "ecosystem health" OR "animal health" OR "livestock health" OR "fish health")
   NOT
   TS= 	("wellbeing" OR "well-being"
    	OR "medical" OR "healthcare" OR "health care" OR "health sector" OR "hospital$" OR "intensive care" OR "essential medic*"
    	OR "human health" OR "public health" OR "health promotion"
    	OR "mental health" OR "psychosocial health"
    	OR "workplace health" OR "occupational health"
    	OR "global health" OR "social determinants of health" OR "health equity" OR "equity and health" OR "health for all"
    	OR "child health"
	)
)
```

#### Diseases/health issues prevalent in LMCs and neglected tropical diseases

Not combined with any countries. Adapted from SDG3 search.

HIV, polio, malaria, TB, waterborne diseases and maternal/infant mortality are included as they are major in LMCs, even though they can also occur elsewhere.

``` Ceylon =
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
    OR "diarrheal disease$" OR "diarrhoeal disease$"

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

For many health terms, some of the results may be about animals or plants; thus some of the search terms are combined with terms for humans. It is otherwise very difficult to remove all results, for example, some about fish or cattle health in LMCs may be included. Can this be considered ok?

`health` and `medical` covers health care, services, education, rights, workers, coverage, sexual/mental/occupational health. However, as "health" can be used in other fields (ecosystem health), specific phrases are included in the first phrase, while "health" generally is combined with human terms. The same applies to `disease`, which covers a number of categories of disease (e.g. communicable disease). Phrases are included in the first part, while it is combined with human terms in the second part.
`therapy` covers various types (art, music, medicinal)

Specific diseases, health care occupations etc. added from SDG3

Countries includes all except high-income countries.

``` Ceylon =
TS=
(
  (
    ("health education" OR "health polic*" OR "health organization$" OR "health service$"
    OR "health equity" OR "right to health*" OR "health rights" OR "health coverage" OR "health governance"
    OR "medical" OR "wellbeing" OR "well-being" OR "SDG 3"

    OR	"infectious disease$" OR "communicable disease$" OR "contagious disease$" OR "transmissible disease$"
    OR 	"waterborne disease$" OR "water borne disease$"
    OR 	"infection$" OR "illness*" OR "premature mortality" OR "morbidity"
    OR	"trauma"  
    OR	"cancer$" OR "neoplasm$"
    OR 	"diabetes"
    OR 	"chronic respiratory disease$"
    OR 	"cancer$" OR "*sarcoma" OR "sarcoma$" OR "*carcinoma" OR "carcinoma$" OR "*blastoma" OR "blastoma$" OR "myeloma$" OR "lymphoma$" OR "leukaemia" OR "leukemia" OR "mesothelioma$" OR "melanoma$"  
    OR	"asthma" OR "chronic obstructive pulmonary disease$" OR "COPD" OR "chronic obstructive airway disease$" OR "chronic bronchitis" OR "emphysema" OR "pneumonia"
    OR	"diabetes"
    OR  "cardiovascular disease$" OR "heart disease" OR "heart attack$" OR "stroke"
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

    OR	"vaccine$" OR "vaccinat*" OR "therapy" OR "therapies"

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
    OR  "breastfeed*" OR "birthweight"
    OR	"perinatal" OR "postnatal" OR	"antenatal" OR "prenatal"
    OR	"abortion*" OR "pregnan*"
    OR 	"reproductive health" OR "sexual health"
    OR	"sex education" OR "family planning"

    OR	"disability" OR "disabled people*" OR "disabled child*"

    OR	"konzo" OR "marasmus" OR "kwashiorkor"

    OR	"child development"
    OR	"developmental disorder$"
    OR  "cognative decline"
    OR	"risk behavi*"
    OR 	"mental health"
    OR	"suicid*" OR "self-harm"
    OR 	"anxiety" OR "psychosis"
    OR 	"intimate partner violence"
    OR	"tombak"
    OR	(("injury" OR "injuries" OR "accident$") NEAR/3 ("workplace" OR "occupation*" OR "traffic" OR "car" OR "road$"))
    OR  "accidental poisoning$"
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
      OR  "disease$" OR "mortality"
      OR  "epidemic$" OR "pandemic$"
      OR  "medicine$" OR "antimalarial$" OR "antiviral$" OR "antibiotic$" OR "antiparasitic$"
      OR  "depression"
      OR  "nutrition*" OR "malnutrition" OR "malnourish*" OR "vitamin$" OR "micronutrient$"
      OR  "hazardous chemical$" OR "hazardous material$" OR "hazardous substance$"
      OR  "arsenic" OR "mercury" OR "asbestos" OR "benzene" OR "cadmium" OR "dioxin$" OR "fluoride"
      OR  "lead poison*" OR "lead *toxicity" OR "lead mediated *toxicity" OR "lead induced *toxicity" OR "lead exposure" OR "lead carcinogen*" OR "blood lead"
      OR  "sanitation" OR "drinking water" OR "potable water"
      )
    AND
      ( "humans" OR "humanity" OR "human" OR "people" OR "person$"
        OR "children" OR "child" OR "infant$" OR "babies" OR "adolescent$"
        OR "adult$" OR "women" OR "men" OR "woman" OR "man" OR "girls" OR "boys"
        OR "rural" OR "urban" OR "city" OR "cities" OR "town$" OR "village$" OR "countr*" OR "nation$" OR "develop* state$"
        OR "patient$" OR "hospital*" OR "health care" OR "healthcare"
        OR "premature death$" OR "premature mortality" OR "covid"
      )
    )
  )
AND
  ("global south" OR "least-developed countr*" OR "developing countr*" OR "low income countr*" OR "poor countr*"

  OR "afghanistan" OR "angola" OR "antigua" OR "bahrain" OR "bangladesh" OR "barbados" OR "belize" OR "benin" OR "bermuda" OR "bhutan" OR "burkina faso" OR "burundi" OR "cabo verde" OR "cambodia" OR "chad" OR "marianas" OR "comoros" OR "congo" OR "cuba" OR "djibouti" OR "dominica" OR "eritrea" OR "ethiopia" OR "micronesia" OR "fiji" OR "french polynesia" OR "gambia" OR "grenada" OR "guadeloupe" OR "guyana" OR "haiti" OR "jamaica" OR "kiribati" OR "laos" OR "lesotho" OR "liberia" OR "madagascar" OR "malawi" OR "maldives" OR "mali" OR "marshall islands" OR "martinique" OR "mauritania" OR "mauritius" OR "montserrat" OR "mozambique" OR "myanmar" OR "nauru" OR "nepal" OR "new caledonia" OR "niger" OR "niue" OR "papua new guinea" OR "rwanda" OR "saint lucia" OR "grenadines" OR "la reunion" OR "samoa" OR "sao tome" OR "senegal" OR "sierra leone" OR "solomon islands" OR "somalia" OR "sudan" OR "suriname" OR "tanzania" OR "timor leste" OR "togo" OR "tonga" OR "tuvalu" OR "uganda" OR "vanuatu" OR "yemen" OR "zambia"

  OR "africa" OR "nigeria" OR "egypt" OR "kenya" OR "algeria" OR "morocco" OR "ghana" OR "ivory coast" OR "cameroon" OR "zimbabwe" OR "tunisia" OR "libya" OR "botswana" OR "gabon" OR "equatorial guinea" OR "eswatini" OR "cape verde" OR "western sahara" OR "mayotte"

  OR "albania" OR "argentina" OR "armenia" OR "azerbaijan" OR "belarus" OR "bolivia" OR "bosnia" OR "brazil" OR "bulgaria" OR "china" OR "colombia" OR "costa rica" OR "ecuador" OR "el salvador" OR "guatemala" OR "honduras" OR "india" OR "indonesia" OR "iran" OR "iraq" OR "jordan" OR "kazakhstan" OR "kosovo" OR "kyrgyz" OR "lebanon" OR "malaysia" OR "mexico" OR "micronesia" OR "moldova" OR "mongolia" OR "montenegro" OR "nicaragua" OR "macedonia" OR "pakistan" OR "paraguay" OR "phillipines" OR "peru" OR "romania" OR "russia" OR "serbia" OR "sri lanka" OR "syria" OR "tajikistan" OR "thailand" OR "turkey" OR "turkmenistan" OR "ukraine" OR "venezuela" OR "vietnam" OR "west bank" OR "gaza"
  )
)  
```

## Inequality

#### General terms

1) Unlimited and 2) Limited by index

``` Ceylon=
TS=
  ("development assistance" OR "development aid"
  OR "otherness" OR "othering" OR "stereotypes"
  OR "human rights" OR "political rights" OR "civil right$" OR "voting right$" OR "sexual rights" OR "land rights" OR "land tenure" OR "constitutional right$" OR "social right$" OR "right to religion" OR "religious freedom$"
  OR (("rights") NEAR/3 ("child" OR "children*" OR "elderly" OR "tribal" OR "worker$" OR "elector*" OR "disabled" OR "disabilit*" OR "religious"))
  OR "welfare system" OR "social welfare" OR "social security" OR "social sustainability" OR "social polic*"   
  OR "social justice" OR "social sustainability" OR "social mobility"
  OR "climate justice" OR "environmental justice"
  OR "poverty" OR "microfinance" OR "microcredit" OR "homeless"
  OR ("intergeneration*" NEAR/5 ("wealth" OR "resource$" OR "mobility"))
  OR "slaves" OR "slave" OR "slavery"
  OR ("caste" NOT "bee$")
  OR "vulnerable people" OR "vulnerable person$" OR "vulnerable group$" OR "the vulnerable"
  OR "autochthonous" OR "sami" OR "sapmi"
  OR (("knowledge") NEAR/3 ("indigenous" OR "traditional" OR "local" OR "community based"))
  OR "minority group$" OR "minority language$" OR "minority stress"
  OR (("discrimination") NEAR/15 ("sociocultural" OR "racial" OR "race" OR "ethnic" OR "minorit*" OR "gender" OR "*sexual" OR "disabilit*" OR "disabled" OR "age" OR "appearance" OR "religi*" OR "muslim" OR "legal" OR "policy of" OR "perceived"))
  OR "racism" OR "racial" OR "apartheid"
  OR "colonialism" OR "postcolonial*" OR "decoloni*" OR "genocide$" OR "epistemicide"
  OR "riot" OR "riots" OR "uprising$" OR "insurrection$" OR "political protest$" OR "political conflict$"
  OR "gender perspective$" OR "gendered" OR "sexism" OR "misogyny"
  OR "intersectional"
  OR "ageism"
  OR "homophob*" OR "gay" OR "lesbian" OR "bisexual" OR "transgender" OR "queer" OR "LGBT" OR "LGBTQ"
)
```

The phrase below only searches in the arts and humanities and social sciences citation indicies in Web of Science, to avoid the medical/biological/physical uses of more generic terms.

``` Ceylon=
(TS=
  ("globalisation" OR "globalization"
  OR "global south" OR "least-developed countr*" OR "developing countr*" OR "low income countr*" OR "BRICS" OR "poor countr*"
  OR "equality" OR "inequalit*" OR "equity" OR "inequity" OR "egalitar*" OR "disparit*"
  OR "criminali*" OR "marginali*"
  OR "justice" OR "injustice" OR "oppressi*"
  OR "low income" OR "economic burden" OR "debt" OR "neoliberal"
  OR "disadvantaged"
  OR "indigenous"
  OR "minorities"
  OR "ethnicity" OR "ethnic"
  OR "colonial"
  )
)
AND
(EDN==("WOS.SSCI" OR "WOS.AHCI"))
```

#### Certain groups

1) Limited by index and 2) Unlimited.  

Note that some groups are not included here, because they are included in their entirety in the phrases above. The groups included below are only included when combined with certain terms.

``` Ceylon=
(TS=
  (
    ("women" OR "girls" OR "boys" OR "gender" OR "child" OR "children"
    OR "elderly" OR "disabilit*" OR "disabled"
    OR "islam" OR "muslim$" OR "christian$" OR "jewish" OR "hindu*" OR "sikh" OR "buddhis*"
    )
    NEAR/15
      ("freedom$"
      OR "security"
      OR "legislat*" OR "governance" OR "democracy"
      OR "power" OR "empower*"
      OR "quota$"
      OR "traditional law$" OR "sharia"
      OR "inclusion" OR "inclusive" OR "language polic*"
      OR "climate change" OR "environmental change$"
      )
  )
)
AND
(EDN==("WOS.SSCI" OR "WOS.AHCI" OR "WOS.ESCI"))
```

This phrase is the same as above, but only including terms that won't cause confusion when run against the science and medicine indices. Some additional terms are added that, while they could not be run alone against all indicies, can together with the groups. Hindu is taken out as also refers to a region in climate science ("hindu kush").

``` Ceylon=
TS=
(
  ("women" OR "girls" OR "boys" OR "gender" OR "child" OR "children"
  OR "elderly" OR "disabilit*" OR "disabled"
  OR "indigenous"
  OR "islam" OR "muslim$" OR "christian$" OR "jewish" OR "sikh" OR "buddhis*"
  )
  NEAR/15
    ("empower*" OR "democracy"
    OR "traditional law$" OR "sharia"
    OR "climate change" OR "environmental change$"
    OR "equity" OR "inequity" OR "egalitar*" OR "disparit*"
    OR "representation" OR "discrimination" OR "criminali*" OR "marginali*"
    OR "justice" OR "injustice" OR "oppressi*"
    OR "low income" OR "economic burden" OR "debt" OR "neoliberal"
    OR "disadvantaged"
    OR "minorities"
    OR "colonial"
    )
)
```

## Migration

The phrase below only searches in the arts and humanities and social sciences citation indicies in Web of Science, to avoid the medical/biological/ecological/physical uses of "migration".

``` Ceylon=
(TS=
  ("immigrant$" OR "immigration" OR "emigration"
  OR "migrant$" OR "migration"
  OR "refugee$" OR "displaced person$" OR "displaced people" OR "stateless person$" OR "stateless people"
  OR "returnee$"
  OR "asylum seek*" OR "people seeking asylum"
  OR "border regime"
  OR "cultural integration" OR "multicultural" OR "acculturat*"
  )
)
AND
(EDN==("WOS.SSCI" OR "WOS.AHCI"))
```

In phrase 2 the ESCI is included - here migration is NOT included - alhtough the majority of results from there seem to be from social sciences/humanities, some emerging geology/biology/medical journals may seep in.

``` Ceylon=
(TS=
  ("immigrant$" OR "immigration" OR "emigration"
  OR "migrant$" OR "human migration" OR "migration background$" OR "migration intention$" OR "worker migration" OR "labor migration"
  OR  ("migration"
      AND   ("asylum" OR "trafficking" OR "displacement"
            OR "rural" OR "urban"
            OR "law" OR "politic*" OR "biopolitics" OR "citizen*"
            OR "minority" OR "minorities"
            )
      )
  OR "refugee$" OR "displaced person$" OR "displaced people" OR "stateless person$" OR "stateless people"
  OR "returnee$"
  OR "asylum seek*" OR "people seeking asylum"
  OR "border regime"
  OR "cultural integration" OR "multicultural" OR "acculturat*" OR "intercultural"
  )
)
AND
(EDN==("WOS.ESCI"))
```

## Global health and inequality

#### Health equity

```
TS=
(	"health equity" OR "right to health*" OR "health rights"
	OR "health coverage" OR "health governance"
	OR
	  (
	    ("access" OR "barrier$")
	    NEAR/5 ("health care" OR "healthcare" OR "health services")
	  )
)
```

#### Health and inequality

Inequality taken directly from Cristin, with minor adaptations. Health terms copied from the global health query.

`LGBTQ` will also find LGBTQ+. `Racial` will find racial disparities etc.

```
TS=
(
  ("globalisation" OR "globalization"
  OR "development assistance" OR "development aid"
  OR "global south" OR "least-developed countr*" OR "developing countr*" OR "low income countr*" OR "poor countr*"
  OR "equality" OR "equity" OR "egalitar*" OR "disparit*"
  OR "representation" OR "discrimination" OR "criminali*" OR "marginali*" OR "otherness" OR "stereotypes"
  OR "human rights" OR "justice" OR "injustice"
  OR "social welfare" OR "social security" OR "social sustainability" OR "social polic*"
  OR "poverty" OR "low income" OR "economic burden" OR "debt" OR "microfinance" OR "homeless*"
  OR "disadvantaged" OR "vulnerable people" OR "vulnerable person$" OR "vulnerable group$"
  OR "indigenous" OR "autochthonous" OR "sami" OR "sapmi"
  OR "minority group$" OR "ethnicity" OR "ethnic"
  OR "racism" OR "racial" OR "apartheid"
  OR "colonial" OR "colonialism"
  OR "gender perspective$" OR "gendered" OR "sexism" OR "misogyny"
  OR "intersectional"
  OR "ageism"
  OR "homophob*" OR "gay" OR "lesbian" OR "bisexual" OR "transgender" OR "queer" OR "LGBT" OR "LGBTQ"
  )
  AND
  (
    ("health education" OR "health polic*" OR "health organization$" OR "health service$"
    OR "health equity" OR "right to health*" OR "health rights" OR "health coverage" OR "health governance"
    OR "medical" OR "wellbeing" OR "well-being" OR "SDG 3"

    OR	"infectious disease$" OR "communicable disease$" OR "contagious disease$" OR "transmissible disease$"
    OR 	"waterborne disease$" OR "water borne disease$"
    OR 	"infection$" OR "illness*" OR "premature mortality" OR "morbidity"
    OR	"trauma"  
    OR	"cancer$" OR "neoplasm$"
    OR 	"diabetes"
    OR 	"chronic respiratory disease$"
    OR 	"cancer$" OR "*sarcoma" OR "sarcoma$" OR "*carcinoma" OR "carcinoma$" OR "*blastoma" OR "blastoma$" OR "myeloma$" OR "lymphoma$" OR "leukaemia" OR "leukemia" OR "mesothelioma$" OR "melanoma$"  
    OR	"asthma" OR "chronic obstructive pulmonary disease$" OR "COPD" OR "chronic obstructive airway disease$" OR "chronic bronchitis" OR "emphysema" OR "pneumonia"
    OR	"diabetes"
    OR  "cardiovascular disease$" OR "heart disease" OR "heart attack$" OR "stroke"
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

    OR	"vaccine$" OR "vaccinat*" OR "therapy" OR "therapies"

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
    OR  "breastfeed*" OR "birthweight"
    OR	"perinatal" OR "postnatal" OR	"antenatal" OR "prenatal"
    OR	"abortion*" OR "pregnan*"
    OR 	"reproductive health" OR "sexual health"
    OR	"sex education" OR "family planning"

    OR	"disability" OR "disabled people*" OR "disabled child*"

    OR	"konzo" OR "marasmus" OR "kwashiorkor"

    OR	"child development"
    OR	"developmental disorder$"
    OR  "cognative decline"
    OR	"risk behavi*"
    OR 	"mental health"
    OR	"suicid*" OR "self-harm"
    OR 	"anxiety" OR "psychosis"
    OR 	"intimate partner violence"
    OR	"tombak"
    OR	(("injury" OR "injuries" OR "accident$") NEAR/3 ("workplace" OR "occupation*" OR "traffic" OR "car" OR "road$"))
    OR  "accidental poisoning$"
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
      OR  "disease$" OR "mortality"
      OR  "epidemic$" OR "pandemic$"
      OR  "medicine$" OR "antimalarial$" OR "antiviral$" OR "antibiotic$" OR "antiparasitic$"
      OR  "depression"
      OR  "nutrition*" OR "malnutrition" OR "malnourish*" OR "vitamin$" OR "micronutrient$"
      OR  "hazardous chemical$" OR "hazardous material$" OR "hazardous substance$"
      OR  "arsenic" OR "mercury" OR "asbestos" OR "benzene" OR "cadmium" OR "dioxin$" OR "fluoride"
      OR  "lead poison*" OR "lead *toxicity" OR "lead mediated *toxicity" OR "lead induced *toxicity" OR "lead exposure" OR "lead carcinogen*" OR "blood lead"
      OR  "sanitation" OR "drinking water" OR "potable water"
      )
    AND
      ( "humans" OR "humanity" OR "human" OR "people" OR "person$"
        OR "children" OR "child" OR "infant$" OR "babies" OR "adolescent$"
        OR "adult$" OR "women" OR "men" OR "woman" OR "man" OR "girls" OR "boys"
        OR "rural" OR "urban" OR "city" OR "cities" OR "town$" OR "village$" OR "countr*" OR "nation$" OR "develop* state$"
        OR "patient$" OR "hospital*" OR "health care" OR "healthcare"
        OR "premature death$" OR "premature mortality" OR "covid"
      )
    )
  )
)
```

#### Extra standalone terms for health and inequality

```
TS=
(	"femicide"
	OR "intimate partner violence" OR "domestic violence"
)
```

#### Right to food and water

```
TS=
(	"right to food" OR "right to water" OR "smallhold*"
	OR "food security" OR "water security"
	OR "access to food" OR "access to water"
)
```

## Global health and migration

Same health terms used as in the above 2 sections.

How to include `migration`? MANY results when adding it are definately not relevant; the problematic ones here are those that also relate to health. Many of these are from surgery, but there is also environmental migration of pollutants (pollutants, radon, PCBs, PM, mercury). Two alternatives - positive inclusion or negative exclusion. I have chosen exclusion of certain phrases (set 2), plus inclusion of certain phrases (set 1) and Web of Science categories (set 3).
An alternative would be to exclude Web of Science categories, but I found this to be difficult as there as so many. A starting list includes: `WC = ("surgery" OR "oncology" OR "neurosciences" OR "clinical neurology" OR "Biochemistry & Molecular Biology" OR "cell biology" OR "Genetics Heredity" OR "orthopedics" OR "Radiology Nuclear Medicine Medical Imaging" OR "Gastroenterology Hepatology" OR "Urology Nephrology" OR "Endocrinology Metabolism" OR "fisheries" OR "marine freshwater biology" OR "ecology" OR "veterinary sciences" OR "entomology" OR "Biodiversity Conservation" OR "toxicology" OR "limnology" OR "water resources" OR "Food Science Technology" OR "chemistry analytical" OR "chemistry multidisciplinary" OR "chemistry physical" OR "chemistry medicinal" OR "chemistry applied" OR "Spectroscopy" OR "optics" OR "engineering electrical electronic" OR "engineering chemical" OR "Biotechnology Applied Microbiology" OR "engineering biomedical" OR "materials science biomaterials" OR "nanoscience nanotechnology" OR "Medical Laboratory Technology")`

**COMBINE: (Set 1 OR (Set 2 AND Set 3)) AND Set 4**

### Set 1 - migrants/refugees

```
TS=
  ("migrant$" OR "immigrant$" OR "immigration" OR "emigration"
  OR "human migration" OR "migration background$" OR "migration intention$" OR "worker migration" OR "labor migration"
  OR  ("migration" AND ("asylum"))
  OR "refugee$" OR "displaced person$" OR "displaced people" OR "stateless person$" OR "stateless people"
  OR "returnee$"
  OR "asylum seek*" OR "people seeking asylum"
  OR "cultural integration" OR "language barrier$" OR "multicultural"
  )
```

### Set 2 - migration exclusions

```
TS = 	"migration"
NOT
  (
  TS = 	("surgical*" OR "surgery" OR "surgeries" OR "arthroplasty" OR "implant*" OR "stent$" OR "shunt" OR "catheter" OR "*prosthesis" OR "intragastric" OR "aberrant migration" OR "device migration" OR "valve migration"
  	OR "foreign bodies" OR "foreign body" OR "needle" OR "bone migration" OR "stone migration" OR "perforation" OR "obstruction" OR "silicone"
  	OR "cell" OR "cells" OR "cancer migration" OR "tumor migration" OR "carcinoma" OR "neoplasm$" OR "metastasis" OR "apoptosis" OR "transcription" OR "expression" OR "receptor" OR "clot migration" OR "neuron* migration" "monocyte$" OR "macrophage$" OR "leukocyte$" OR "chondrocyte$" OR "neutrophil$" OR "inhibitory factor" OR "anteriorly" OR "posteriorly" OR "transmembrane" OR "biomarker"
  	OR "pain migration" OR "periodontitis" OR "hip migration"
	OR "animal migration$" OR "migratory bird$" OR "biofilm migration" OR "seed migration" OR "larva* migration" OR "deer" OR "bats"
	OR "population genetics"
	OR "contaminant migration" OR "lead migration" OR "pb migration"
  	OR "electrokinetic migration"
  	)
  )
```

### Set 3 - migration inclusions

The categories "Medicine general internal" OR "tropical medicine" OR "infectious diseases" contain some irrelevant, but I think combined with the above terms there should not be too much noise...

```
TS = 	"migration"
AND
  WC = 	("Public Environmental Occupational Health" OR "Health policy services" OR "Health Care Sciences Services" OR "Medical ethics"
  	OR "Medicine general internal" OR "tropical medicine" OR "infectious diseases"
	OR "Environmental sciences"
	OR "Regional urban planning" OR "Economics" OR "Development studies" OR "urban studies" OR "geography" OR "demography" OR "area studies"
	OR "Family Studies" OR "Social Work"
	OR "psychiatry" OR "Psychology Social" OR "psychology multidisciplinary"
	OR "Social Sciences Interdisciplinary" OR "social sciences biomedical" OR "Sociology"
	OR "Multidisciplinary Sciences"
	)
```

### Set 4 - health terms

Removed some of the environmental pollutant terms from the medical terms, since these can combine with migration in ways that are nothing to do with human migration.

Some of the groups from Set 1 have been added to the bottom here as "human" terms - this means that a mention of health + refugee is enough to be included. For more general migration terms which can apply to animals, such as immigration, health is only in phrases that are mostly used for humans (e.g. health education, medical, wellbeing)

```
TS=
(
    "migrant health" OR "refugee health" OR "immigrant health"
    OR "health behavior$" OR "health education" OR "health polic*" OR "health organization$" OR "health service$"
    OR "health equity" OR "right to health*" OR "health rights" OR "health coverage" OR "health governance"
    OR "medical" OR "wellbeing" OR "well-being" OR "SDG 3"

    OR	"infectious disease$" OR "communicable disease$" OR "contagious disease$" OR "transmissible disease$"
    OR 	"waterborne disease$" OR "water borne disease$"
    OR 	"infection$" OR "illness*" OR "premature mortality" OR "morbidity"
    OR	"trauma"  
    OR	"cancer$" OR "neoplasm$"
    OR 	"diabetes"
    OR 	"chronic respiratory disease$"
    OR 	"cancer$" OR "*sarcoma" OR "sarcoma$" OR "*carcinoma" OR "carcinoma$" OR "*blastoma" OR "blastoma$" OR "myeloma$" OR "lymphoma$" OR "leukaemia" OR "leukemia" OR "mesothelioma$" OR "melanoma$"  
    OR	"asthma" OR "chronic obstructive pulmonary disease$" OR "COPD" OR "chronic obstructive airway disease$" OR "chronic bronchitis" OR "emphysema" OR "pneumonia"
    OR	"diabetes"
    OR  "cardiovascular disease$" OR "heart disease" OR "heart attack$" OR "stroke"
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

    OR	"vaccine$" OR "vaccinat*" OR "therapy" OR "therapies"

    OR  "clinic$" OR "hospital$" OR "healthcare" OR "health care" OR "residential care" OR  "patient care"
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
    OR  "breastfeed*" OR "birthweight"
    OR	"perinatal" OR "postnatal" OR	"antenatal" OR "prenatal"
    OR	"abortion*" OR "pregnan*"
    OR 	"reproductive health" OR "sexual health"
    OR	"sex education" OR "family planning"

    OR	"disability" OR "disabled people*" OR "disabled child*"

    OR	"konzo" OR "marasmus" OR "kwashiorkor"

    OR	"child development"
    OR	"developmental disorder$"
    OR  "cognative decline"
    OR	"risk behavi*"
    OR 	"mental health"
    OR	"suicid*" OR "self-harm"
    OR 	"anxiety" OR "psychosis"
    OR 	"intimate partner violence"
    OR	"tombak"
    OR	(("injury" OR "injuries" OR "accident$") NEAR/3 ("workplace" OR "occupation*" OR "traffic" OR "car" OR "road$"))
    OR  "accidental poisoning$"
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
    OR
      (
        (   "health"
        OR  "disease$" OR "mortality"
        OR  "epidemic$" OR "pandemic$"
      	OR  "medicine$" OR "antimalarial$" OR "antiviral$" OR "antibiotic$" OR "antiparasitic$"
      	OR  "depression"
     	  OR  "nutrition*" OR "malnutrition" OR "malnourish*" OR "vitamin$" OR "micronutrient$"
      	OR  "sanitation" OR "drinking water" OR "potable water"
      	)
      AND
      	("humans" OR "humanity" OR "human" OR "people" OR "person$"
        OR "children" OR "child" OR "infant$" OR "babies" OR "adolescent$"
        OR "adult$" OR "women" OR "men" OR "woman" OR "man" OR "girls" OR "boys"
        OR "rural" OR "urban" OR "city" OR "cities" OR "town$" OR "village$" OR "countr*" OR "nation$" OR "develop* state$"
        OR "patient$" OR "hospital*" OR "health care" OR "healthcare"
        OR "premature death$" OR "premature mortality" OR "covid"
	      OR "human migration" OR "migration background$" OR "migration intention$" OR "worker migration" OR "migrant worker$" OR "labor migration"
  	    OR "refugee$" OR "displaced person$" OR "displaced people" OR "stateless person$" OR "stateless people"
  	    OR "returnee$"
  	    OR "asylum seeker$" OR "people seeking asylum"
	      OR "cultural integration" OR "language barrier$" OR "multicultural"
        )
      )
)
```
