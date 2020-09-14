# pandas-challenge

nb_black
%load_ext lab_black
Import Pandas as pd
import os
import pandas as pd
import numpy as np
Load File
path = os.path.join(
    "..",
    "..",
    "UTA-AUS-DATA-PT-07-2020-U-C",
    "homework",
    "04-Pandas",
    "Instructions",
    "HeroesOfPymoli",
    "Resources",
    "purchase_data.csv",
)
purchase_data = pd.read_csv(path)
purchase_data.head()
Purchase ID	SN	Age	Gender	Item ID	Item Name	Price
0	0	Lisim78	20	Male	108	Extraction, Quickblade Of Trembling Hands	3.53
1	1	Lisovynya38	40	Male	143	Frenzied Scimitar	1.56
2	2	Ithergue48	24	Male	92	Final Critic	4.88
3	3	Chamassasya86	24	Male	100	Blindscythe	3.27
4	4	Iskosia90	23	Male	131	Fury	1.44
Total = purchase_data["Gender"].value_counts()
Total
Male                     652
Female                   113
Other / Non-Disclosed     15
Name: Gender, dtype: int64
Data Types
purchase_data.dtypes
Purchase ID      int64
SN              object
Age              int64
Gender          object
Item ID          int64
Item Name       object
Price          float64
dtype: object
Data Describe
purchase_data.describe()
Purchase ID	Age	Item ID	Price
count	780.000000	780.000000	780.000000	780.000000
mean	389.500000	22.714103	92.114103	3.050987
std	225.310896	6.659444	52.775943	1.169549
min	0.000000	7.000000	0.000000	1.000000
25%	194.750000	20.000000	48.000000	1.980000
50%	389.500000	22.000000	93.000000	3.150000
75%	584.250000	25.000000	139.000000	4.080000
max	779.000000	45.000000	183.000000	4.990000
Player Count
#Total Number of Players

# purchase_data["SN"].value_counts()
Total_Players_purchase_data = purchase_data["SN"].value_counts().count()
Total_Players_purchase_data
576
#List of Unique Players

purchase_data["SN"].unique()
array(['Lisim78', 'Lisovynya38', 'Ithergue48', 'Chamassasya86',
       'Iskosia90', 'Yalae81', 'Itheria73', 'Iskjaskst81', 'Undjask33',
       'Chanosian48', 'Inguron55', 'Haisrisuir60', 'Saelaephos52',
       'Assjaskan73', 'Saesrideu94', 'Lisassa64', 'Lisirra25',
       'Zontibe81', 'Reunasu60', 'Chamalo71', 'Iathenudil29',
       'Phiarithdeu40', 'Siarithria38', 'Eyrian71', 'Siala43',
       'Lisirra87', 'Lirtossa84', 'Eusri44', 'Aela59', 'Tyida79',
       'Idai61', 'Farusrian86', 'Aeralria27', 'Haillyrgue51', 'Sondim73',
       'Jeyciman68', 'Idaisuir85', 'Seuthep89', 'Reulae52',
       'Sondilsaya62', 'Aerithriaphos45', 'Assosia88', 'Aidaillodeu39',
       'Aelly27', 'Tyeosri53', 'Haerith37', 'Yasrisu92', 'Chanuchi25',
       'Asur96', 'Iaralrgue74', 'Chanosia34', 'Aelin32', 'Ilosianya35',
       'Zhisrisu83', 'Phaelap26', 'Raesty92', 'Palyon91', 'Tyisur83',
       'Yaliru88', 'Yadanu52', 'Jiskimya77', 'Yadaphos40', 'Alo38',
       'Phaena87', 'Chamirraya83', 'Chanastsda67', 'Indonmol95',
       'Jiskossa61', 'Pheodai94', 'Hari50', 'Marilsa69', 'Assistasda42',
       'Lisosia93', 'Philodil43', 'Mindadaran26', 'Lirtosia63',
       'Assjaskan56', 'Irithlis29', 'Heudai45', 'Haerithp41', 'Aina42',
       'Jiskjask60', 'Umolrian85', 'Qarirwen82', 'Laedallo55',
       'Eoralrap26', 'Undosian34', 'Chadolyla44', 'Chadistaya75',
       'Yathedeu43', 'Aina43', 'Ilassast39', 'Lisassala98', 'Aiduecal76',
       'Chadossa89', 'Pheodaisun84', 'Heollyriap59', 'Maropast28',
       'Frichim77', 'Thryallym62', 'Eulanurin88', 'Lassjaskan73',
       'Tyaerith73', 'Sondadarya58', 'Hirirap39', 'Ririp86', 'Sundim98',
       'Iskichinya81', 'Phyali88', 'Undirrala66', 'Nitherian58',
       'Lassilsala30', 'Frichaststa61', 'Frichosia58', 'Ilosia37',
       'Lisista27', 'Seudaillorap38', 'Aesty53', 'Yathecal82',
       'Lisossanya98', 'Iral74', 'Lisast87', 'Maridisya31', 'Jiskassa76',
       'Ethriel85', 'Iskirra45', 'Iri67', 'Rarallo90', 'Lisasi93',
       'Adastirin33', 'Eyista89', 'Ili43', 'Chamirra53', 'Hailaphos89',
       'Iskadarya95', 'Qilatista90', 'Inasti31', 'Marilsanya48',
       'Marjask87', 'Chanjaskan89', 'Hyaduesu61', 'Aillyrin83',
       'Marast30', 'Sundadar27', 'Tyaelorap29', 'Lirtimst73',
       'Styaduen40', 'Sidap51', 'Chanastst38', 'Lirtassa52', 'Sondim68',
       'Aeral97', 'Heosurnuru52', 'Lisopela58', 'Caesrinusuir82',
       'Tyirinu79', 'Fironon91', 'Lassjask63', 'Indcil77', 'Chamimla73',
       'Syathe73', 'Baelollodeu94', 'Mindista32', 'Saena74',
       'Marirrasta50', 'Lamil79', 'Aenarap34', 'Aisur51', 'Thrientossa55',
       'Chadista79', 'Tyeurith29', 'Malunil62', 'Hiasri33', 'Lisadar44',
       'Frichjask31', 'Lisjaskya84', 'Ristydru66', 'Frichast28',
       'Minduri31', 'Maradaran90', 'Mindetosya30', 'Ialallo29',
       'Pheusrical25', 'Chanosia60', 'Phistym51', 'Aelollo59',
       'Chamimla85', 'Haisurra41', 'Sondastsda82', 'Qilanrion65',
       'Eulasuir89', 'Eosrirgue62', 'Shaidanu32', 'Lirtastan49',
       'Iaralsuir44', 'Tyeudariasuir90', 'Cosadar58', 'Aelastirin39',
       'Aidai53', 'Jiskjask85', 'Ealrion88', 'Chamjask73', 'Tyaenasti87',
       'Alim85', 'Haeladil46', 'Jiskirran77', 'Undosia27', 'Peorith44',
       'Yarithsurgue62', 'Taeduenu92', 'Rairin89', 'Aerithriaphos46',
       'Idairin51', 'Lisista54', 'Eodailis27', 'Lirtastsda29',
       'Undilsan50', 'Eodaisu60', 'Quaranmol58', 'Lirtossa60',
       'Lirtilsa71', 'Isursuir31', 'Sundirrala66', 'Saerallora71',
       'Iasur80', 'Tyaelo67', 'Quanunwen42', 'Yasur35', 'Assehoan67',
       'Haellysu29', 'Saida58', 'Chamadar79', 'Aeral43', 'Lirtirra37',
       'Tyidaim51', 'Lassassast73', 'Assassasta79', 'Heollyra92',
       'Anallorgue57', 'Aerithllora36', 'Smaistysu35', 'Ennalmol65',
       'Yarithrgue83', 'Yana46', 'Sondimla25', 'Aidai61', 'Wailin72',
       'Firan91', 'Alaesu91', 'Aellynun67', 'Rilaera56', 'Eulaestira36',
       'Marim28', 'Idastidru52', 'Ilirrasda54', 'Alaephos75',
       'Syalollorap93', 'Minduli80', 'Chanastya70', 'Frichadaran88',
       'Siallylis44', 'Aeri84', 'Iasursti71', 'Mindilsa34', 'Chamastya76',
       'Undirra73', 'Aestysu37', 'Chadadarla74', 'Strithenu87',
       'Iasrira89', 'Ialidru40', 'Tyalaesu89', 'Tyidainu31', 'Lirtilsa72',
       'Undjaskla97', 'Saedaiphos46', 'Aerithnucal56', 'Lisossa46',
       'Layjask75', 'Lisista63', 'Ceoral34', 'Hilaerin92',
       'Chadilsasta32', 'Undassa89', 'Iduenu77', 'Lisosia66',
       'Undimsya85', 'Phaedue89', 'Yadacal26', 'Lisossa25', 'Ilmol66',
       'Yastyriaphos75', 'Hiasurria41', 'Palatyon26', 'Qilalista41',
       'Hada39', 'Chamilsala65', 'Rairith81', 'Ilarin91', 'Ryanara76',
       'Undista85', 'Tyeoralru41', 'Pheosrinudeu70', 'Heuli25',
       'Pheutherin27', 'Chadirra90', 'Ali84', 'Frichjaskan98', 'Malil90',
       'Yarithllodeu72', 'Tyaedainu44', 'Ethron58', 'Eusurdeu49',
       'Saistyphos30', 'Saisrilis27', 'Hallysucal81', 'Ilimya66',
       'Raysistast71', 'Haedairiadru51', 'Tyananurgue44', 'Risty84',
       'Aerillorin70', 'Phistyn52', 'Yalo85', 'Chamirrasya33', 'Hiral75',
       'Isursti83', 'Bartassaya73', 'Aeda94', 'Quinarap53', 'Asur53',
       'Alarap40', 'Sida61', 'Hiarideu73', 'Lassassasda30', 'Ennoncil86',
       'Siralsudeu54', 'Eusri26', 'Ardcil81', 'Marilsasya33', 'Lirtim36',
       'Heunadil74', 'Frichadar89', 'Aesurstilis64', 'Idaidil28',
       'Lisotesta51', 'Lisico81', 'Lisiriya82', 'Siana77', 'Marokian45',
       'Sausosia74', 'Assesi91', 'Eusri70', 'Aisurria69', 'Iarilis73',
       'Raisty38', 'Ilista82', 'Leyirra83', 'Aiduesu86', 'Frichynde86',
       'Hisridru55', 'Chamossa77', 'Irillo49', 'Lirtastsya71',
       'Frichosiala98', 'Qilunan34', 'Quarrion42', 'Aisurdru79',
       'Hiaral50', 'Iarallo65', 'Sondassasya91', 'Chanossast57',
       'Chanjask65', 'Ethralista69', 'Sondistanya61', 'Eudanu32',
       'Euthe35', 'Lassimla92', 'Lisossala30', 'Eulae84', 'Chamadarnya73',
       'Eolan54', 'Assistasda90', 'Ennrian78', 'Undirrasta89',
       'Rianistast50', 'Undare39', 'Adairialis76', 'Aesur96',
       'Tyialisudeu65', 'Arirgue63', 'Sundadarla27', 'Eyircil84', 'Ina92',
       'Lirtistanya48', 'Marassa62', 'Mindossa76', 'Salilis27',
       'Sondossa69', 'Sundjask71', 'Errian63', 'Eurithphos97',
       'Raillydeu47', 'Malon70', 'Jiskimsda56', 'Marughi89', 'Ingatcil75',
       'Chanirrasta87', 'Alaesu77', 'Ermol76', 'Tyeuduen32', 'Firon67',
       'Iadueria43', 'Pheulidil31', 'Eodairu79', 'Frichocesta66',
       'Thourdirra92', 'Chanastnya43', 'Iskim96', 'Eulolis41',
       'Sastydeu50', 'Ilaesudil92', 'Yasur85', 'Aidain51',
       'Aerithnuphos61', 'Yalostiphos68', 'Meosridil82', 'Aillyriadru65',
       'Sally64', 'Lisim51', 'Isurria36', 'Silaera56', 'Leetirraya83',
       'Lirtirra81', 'Eryon48', 'Iana95', 'Sondassan80', 'Chanadar44',
       'Eosurdru76', 'Shidai42', 'Aesri53', 'Syally44', 'Jiskadarst60',
       'Sondadar26', 'Malarrian73', 'Maluncil97', 'Ilunyon70', 'Yadam35',
       'Dyally87', 'Pheosurllorin41', 'Frichaya88', 'Lassadarsda57',
       'Marynde90', 'Isri34', 'Assastnya25', 'Ardonmol96',
       'Lassirrasda85', 'Chadossa56', 'Poshilsa82', 'Yoishirrala98',
       'Sundista37', 'Ilassa51', 'Filurarn35', 'Phaestycal84', 'Irilis75',
       'Aeralstical35', 'Chanirrala39', 'Chanirra79', 'Assirra56',
       'Seolollo93', 'Iathem87', 'Iasurriacal29', 'Lisast98', 'Filrion59',
       'Halaecal66', 'Iskosian40', 'Ilastilis78', 'Seosrim97',
       'Farrian71', 'Rithe53', 'Frichossala54', 'Chamjaskya75',
       'Quanrion96', 'Tyaelaelis94', 'Quanenrian83', 'Chanirra64',
       'Yadaisuir65', 'Syathecal44', 'Arin32', 'Aelaria33', 'Assassa81',
       'Filrion83', 'Eoral49', 'Airi27', 'Eurisuru25', 'Liawista80',
       'Lisirra58', 'Chamadarsda63', 'Haestyphos66', 'Phaedasurap84',
       'Mindimnya67', 'Chadjask85', 'Eustyria89', 'Iskim66', 'Chamast86',
       'Lirtassan78', 'Ethrasyon38', 'Quilassa66', 'Lisassasda39',
       'Mindilsa60', 'Lalossa38', 'Chamistast30', 'Hariphos58',
       'Assilsan72', 'Inasuir29', 'Chanilsasda38', 'Mindesi74',
       'Ililsan66', 'Idacal95', 'Aeral68', 'Tyarithn67', 'Asty82',
       'Yalaeria91', 'Chadjask77', 'Ealiril69', 'Quaecjask96',
       'Firatan58', 'Yarolwen77', 'Tyaelistidru84', 'Yarithrin84',
       'Tyaelly53', 'Phiristi62', 'Ililsasya43', 'Aithelis62',
       'Undotesta33', 'Aelidru27', 'Chanossanya44', 'Maradarnya40',
       'Lisilsa62', 'Saena89', 'Chanilsast61', 'Sundassa93', 'Aidai73',
       'Indirrian56', 'Lisassasta50', 'Iduelis31', 'Chanosiaya39',
       'Assylla81', 'Aidaira26', 'Eudanu84', 'Chamiman85', 'Tyialisti80',
       'Marundi65', 'Eusur90', 'Mindirranya33', 'Phiallylis33', 'Isty55',
       'Frichilsa31', 'Chanista95', 'Aellyria80', 'Rastynusuir31',
       'Iljask75', 'Lisjaskan36', 'Mindjasksya61', 'Frichirranya75',
       'Ilast79', 'Eratiel90', 'Assim27', 'Irith83', 'Ilosian36',
       'Iskossasda43', 'Hala31', 'Jiskjask80', 'Aethedru70', 'Yathecal72',
       'Sisur91'], dtype=object)
Purchasing Analysis (Total)
#Number of Unique Items

# purchase_data["Item ID"].value_counts()
Unique_Items_purchase_data = purchase_data["Item ID"].value_counts().count()
Unique_Items_purchase_data
183
#Number of Purchases

Number_Purchases_purchase_data = purchase_data["Purchase ID"].count()
Number_Purchases_purchase_data
780
#Average Price

Price_Average_purchase_data = purchase_data["Price"].mean()
Price_Average_purchase_data
3.050987179487176
#Total Revenue

Price_Total_Revenue_purchase_data = (
    Price_Average_purchase_data * Number_Purchases_purchase_data
)
Price_Total_Revenue_purchase_data
2379.7699999999973
Purchasing Analysis (Total- data summary )
data_summary = pd.DataFrame(
    [
        {
            "Number of Unique Items": Unique_Items_purchase_data,
            "Average Price": Price_Average_purchase_data,
            "Number of Purchases": Number_Purchases_purchase_data,
            "Total Revenue": Price_Total_Revenue_purchase_data,
        }
    ]
)
data_summary
Number of Unique Items	Average Price	Number of Purchases	Total Revenue
0	183	3.050987	780	2379.77
Gender Demographics / Purchasing Analysis (Gender)
#Count of Male Players

players_purchase_count_purchase_data = purchase_data.groupby(purchase_data["Gender"])[
    "SN"
].value_counts()
players_purchase_count_purchase_data
Gender                 SN         
Female                 Chamjask73     3
                       Ialallo29      3
                       Phyali88       3
                       Tyidaim51      3
                       Umolrian85     3
                                     ..
Other / Non-Disclosed  Haerithp41     1
                       Jiskirran77    1
                       Lirtim36       1
                       Rairith81      1
                       Sundim98       1
Name: SN, Length: 576, dtype: int64
Players_purchase_data = purchase_data.loc[:, ["SN", "Gender", "Age"]].drop_duplicates()
Players_purchase_data
SN	Gender	Age
0	Lisim78	Male	20
1	Lisovynya38	Male	40
2	Ithergue48	Male	24
3	Chamassasya86	Male	24
4	Iskosia90	Male	23
...	...	...	...
773	Hala31	Male	21
774	Jiskjask80	Male	11
775	Aethedru70	Female	21
777	Yathecal72	Male	20
778	Sisur91	Male	7
576 rows × 3 columns

Male_Players_purchase_data = (
    purchase_data.loc[purchase_data["Gender"] == "Male", "SN"].value_counts().count()
)
Male_Players_purchase_data
484
#Count of Male

Male_purchase_data = purchase_data.loc[
    purchase_data["Gender"] == "Male", "Purchase ID"
].count()
Male_purchase_data
652
#Percentage of Players Male

Percentage_Male_purchase_data = Male_Players_purchase_data / Total_Players_purchase_data
Percentage_Male_purchase_data
0.8402777777777778
#Count of Female Players

Female_Players_purchase_data = (
    purchase_data.loc[purchase_data["Gender"] == "Female", "SN"].value_counts().count()
)
Female_Players_purchase_data
81
# Count of Female
Female_purchase_data = purchase_data.loc[
    purchase_data["Gender"] == "Female", "Purchase ID"
].count()
Female_purchase_data
113
#Percentage of Players Female

Percentage_Female_purchase_data = (
    Female_Players_purchase_data / Total_Players_purchase_data
)
Percentage_Female_purchase_data
0.140625
#Count of Other / Non-Disclosed Players

Other_Non_Disclosed_Players_purchase_data = (
    purchase_data.loc[purchase_data["Gender"] == "Other / Non-Disclosed", "SN"]
    .value_counts()
    .count()
)
Other_Non_Disclosed_Players_purchase_data
11
#Count of Other / Non-Disclosed

Other_Non_Disclosed_purchase_data = purchase_data.loc[
    purchase_data["Gender"] == "Other / Non-Disclosed", "Purchase ID"
].count()
Other_Non_Disclosed_purchase_data
15
#Percentage of Other Non-Disclosed Players

Percentage_Other_Non_Disclosed_purchase_data = (
    Other_Non_Disclosed_Players_purchase_data / Total_Players_purchase_data
)
Percentage_Other_Non_Disclosed_purchase_data
0.019097222222222224
#Average Price Gender - Male

Average_Price_Male_purchase_data = purchase_data[purchase_data["Gender"] == "Male"][
    "Price"
].mean()
Average_Price_Male_purchase_data
3.0178527607361953
#Average Price Gender - Female

Average_Price_Female_purchase_data = purchase_data[purchase_data["Gender"] == "Female"][
    "Price"
].mean()
Average_Price_Female_purchase_data
3.203008849557519
#Average Price Gender - Other / Non-Disclosed

Average_Price_Other_Non_Disclosed_purchase_data = purchase_data[
    purchase_data["Gender"] == "Other / Non-Disclosed"
]["Price"].mean()
Average_Price_Other_Non_Disclosed_purchase_data
3.3460000000000005
#Total Male Purchase Value

Total_Male_Purchase_Value_purchase_data = (
    Average_Price_Male_purchase_data * Male_purchase_data
)
Total_Male_Purchase_Value_purchase_data
1967.6399999999994
#Total Female Purchase Value

Total_Female_Purchase_Value_purchase_data = (
    Average_Price_Female_purchase_data * Female_purchase_data
)
Total_Female_Purchase_Value_purchase_data
361.93999999999966
#Total Other Non-Disclosed Purchase Value

Total_Other_Non_Disclosed_Purchase_Value_purchase_data = (
    Average_Price_Other_Non_Disclosed_purchase_data * Other_Non_Disclosed_purchase_data
)
Total_Other_Non_Disclosed_Purchase_Value_purchase_data
50.190000000000005
# Avg Male Price Per Person
Avg_Male_Purchase_Per_person_purchase_data = (
    Total_Male_Purchase_Value_purchase_data / Male_Players_purchase_data
)
Avg_Male_Purchase_Per_person_purchase_data
4.065371900826445
#Avg Female Price Per Person

Avg_Female_Purchase_Per_person_purchase_data = (
    Total_Female_Purchase_Value_purchase_data / Female_Players_purchase_data
)
Avg_Female_Purchase_Per_person_purchase_data
4.4683950617283905
# Avg Other Non-Disclosed Price Per Person
Avg_Other_Non_Disclosed_Purchase_Per_person_purchase_data = (
    Total_Other_Non_Disclosed_Purchase_Value_purchase_data
    / Other_Non_Disclosed_Players_purchase_data
)
Avg_Other_Non_Disclosed_Purchase_Per_person_purchase_data
4.562727272727273
Gender Demographics - data summary
data_summary = pd.DataFrame(
    [
        {
            " ": "Male",
            "Total Count": Male_Players_purchase_data,
            "Percentage of Players": Percentage_Male_purchase_data,
        },
        {
            " ": "Female",
            "Total Count": Female_Players_purchase_data,
            "Percentage of Players": Percentage_Female_purchase_data,
        },
        {
            " ": "Other Non Disclosed",
            "Total Count": Other_Non_Disclosed_Players_purchase_data,
            "Percentage of Players": Percentage_Other_Non_Disclosed_purchase_data,
        },
    ]
)
data_summary
Total Count	Percentage of Players
0	Male	484	0.840278
1	Female	81	0.140625
2	Other Non Disclosed	11	0.019097
Purchasing Analysis (Gender - data summary)
data_summary = pd.DataFrame(
    [
        {
            "Gender": "Female",
            "Purchase Count": Female_purchase_data,
            "Average Price": Average_Price_Female_purchase_data,
            "Total Purchase Value": Total_Female_Purchase_Value_purchase_data,
            "Avg Total Purchase Per Person": Avg_Female_Purchase_Per_person_purchase_data,
        },
        {
            "Gender": "Male",
            "Purchase Count": Male_purchase_data,
            "Average Price": Average_Price_Male_purchase_data,
            "Total Purchase Value": Total_Male_Purchase_Value_purchase_data,
            "Avg Total Purchase Per Person": Avg_Male_Purchase_Per_person_purchase_data,
        },
        {
            "Gender": "Other Non Disclosed",
            "Purchase Count": Other_Non_Disclosed_purchase_data,
            "Average Price": Average_Price_Other_Non_Disclosed_purchase_data,
            "Total Purchase Value": Total_Other_Non_Disclosed_Purchase_Value_purchase_data,
            "Avg Total Purchase Per Person": Avg_Other_Non_Disclosed_Purchase_Per_person_purchase_data,
        },
    ]
)
data_summary
Gender	Purchase Count	Average Price	Total Purchase Value	Avg Total Purchase Per Person
0	Female	113	3.203009	361.94	4.468395
1	Male	652	3.017853	1967.64	4.065372
2	Other Non Disclosed	15	3.346000	50.19	4.562727
Age Demographics
#Establishing bins for ages

bins = [0, 9, 14, 19, 24, 29, 34, 39, 45]
group_names = [" <10", "10-14", "15-19", "20-24", "25-29", "30-34", "35-39", "40+"]
#The existing players categorized by the age bins.

purchase_data["Age Ranges"] = pd.cut(purchase_data["Age"], bins, labels=group_names)
purchase_data["Age Ranges"].value_counts().to_frame()
Age Ranges
20-24	365
15-19	136
25-29	101
30-34	73
35-39	41
10-14	28
<10	23
40+	13
Players_purchase_data = purchase_data.loc[:, ["SN", "Age", "Gender"]].drop_duplicates()
Players_purchase_data = pd.DataFrame(Players_purchase_data["SN"].value_counts())
Players_purchase_data
SN
Rilaera56	1
Lisim51	1
Saistyphos30	1
Haisurra41	1
Aillyrin83	1
...	...
Malil90	1
Chamimla73	1
Ardonmol96	1
Rairith81	1
Quilassa66	1
576 rows × 1 columns

Purchasing Analysis (Age)
#Pruchase Count

Purchase_Count_purchase_data = (
    purchase_data.groupby(purchase_data["Age Ranges"])["Purchase ID"].count().to_frame()
)
Purchase_Count = pd.DataFrame(Purchase_Count_purchase_data["Purchase ID"])
Purchase_Count
Purchase ID
Age Ranges	
<10	23
10-14	28
15-19	136
20-24	365
25-29	101
30-34	73
35-39	41
40+	13
Avg_Price_purchase_data = (
    purchase_data.groupby(purchase_data["Age Ranges"])["Price"].mean().to_frame()
)
Average_Price = pd.DataFrame(Avg_Price_purchase_data["Price"])
Average_Price
Price
Age Ranges	
<10	3.353478
10-14	2.956429
15-19	3.035956
20-24	3.052219
25-29	2.900990
30-34	2.931507
35-39	3.601707
40+	2.941538
#Average Purchase Price

Total_Value_purchase_data = (
    Purchase_Count_purchase_data["Purchase ID"] * Avg_Price_purchase_data["Price"]
)
Total_Value = pd.DataFrame(Total_Value_purchase_data)
Total_Value
0
Age Ranges	
<10	77.13
10-14	82.78
15-19	412.89
20-24	1114.06
25-29	293.00
30-34	214.00
35-39	147.67
40+	38.24
#Avg Total Purchase per Person

Purchase_Count_Players_purchase_data = purchase_data.groupby(
    purchase_data["Age Ranges"]
)["SN"].value_counts()
Total_Players = pd.DataFrame(Purchase_Count_Players_purchase_data)
Total_Players
SN
Age Ranges	SN	
<10	Haillyrgue51	3
Anallorgue57	2
Eurithphos97	2
Ilmol66	2
Sondadar26	2
...	...	...
40+	Isursuir31	1
Jiskjask85	1
Lisovynya38	1
Mindossa76	1
Salilis27	1
576 rows × 1 columns

Total_Purchase_Count_Players_purchase_data = (
    purchase_data.groupby(purchase_data["Age Ranges"])["SN"].value_counts().count()
)
Total_Purchase_Count_Players_purchase_data
576
Purchasing Analysis (Age) - data summary
data_summary = pd.DataFrame(
    [
        {
            "Age Ranges": "<10",
            "Total Count": 23,
            "Average Purchase Price": 3.35,
            "Total Purchase Value": 77.13,
            "Avg Total Purchase per Person": 00,
        },
        {
            "Age Ranges": "10-14",
            "Total Count": 28,
            "Average Purchase Price": 2.96,
            "Total Purchase Value": 82.78,
            "Avg Total Purchase per Person": 00,
        },
        {
            "Age Ranges": "15-19",
            "Total Count": 136,
            "Average Purchase Price": 3.04,
            "Total Purchase Value": 412.89,
            "Avg Total Purchase per Person": 00,
        },
        {
            "Age Ranges": "20-24",
            "Total Count": 365,
            "Average Purchase Price": 3.05,
            "Total Purchase Value": 1_114.06,
            "Avg Total Purchase per Person": 00,
        },
        {
            "Age Ranges": "25-29",
            "Total Count": 101,
            "Average Purchase Price": 2.90,
            "Total Purchase Value": 293.00,
            "Avg Total Purchase per Person": 00,
        },
        {
            "Age Ranges": "30-34",
            "Total Count": 73,
            "Average Purchase Price": 2.93,
            "Total Purchase Value": 214.00,
            "Avg Total Purchase per Person": 00,
        },
        {
            "Age Ranges": "35-39",
            "Total Count": 41,
            "Average Purchase Price": 3.60,
            "Total Purchase Value": 147.67,
            "Avg Total Purchase per Person": 00,
        },
        {
            "Age Ranges": "40+",
            "Total Count": 13,
            "Average Purchase Price": 2.94,
            "Total Purchase Value": 38.24,
            "Avg Total Purchase per Person": 00,
        },
    ]
)
data_summary
Age Ranges	Total Count	Average Purchase Price	Total Purchase Value	Avg Total Purchase per Person
0	<10	23	3.35	77.13	0
1	10-14	28	2.96	82.78	0
2	15-19	136	3.04	412.89	0
3	20-24	365	3.05	1114.06	0
4	25-29	101	2.90	293.00	0
5	30-34	73	2.93	214.00	0
6	35-39	41	3.60	147.67	0
7	40+	13	2.94	38.24	0
Top Spenders
​
Players_purchase_data = purchase_data.loc[
    :, ["SN", "Purchase ID", "Price"]
].drop_duplicates()
Players_purchase_data.sort_values("Price", ascending=False)[
    ["SN", "Purchase ID", "Price"]
]
SN	Purchase ID	Price
554	Dyally87	554	4.99
189	Hiasri33	189	4.99
110	Ririp86	110	4.94
246	Lirtilsa71	246	4.94
493	Chanirrasta87	493	4.94
...	...	...	...
586	Chanirra79	586	1.01
282	Aidai61	282	1.01
371	Eusurdeu49	371	1.01
63	Alo38	63	1.00
418	Marim28	418	1.00
780 rows × 3 columns

Most Popular Items
Unique_Items_purchase_data = purchase_data["Item ID"].value_counts().count()
Unique_Items_purchase_data
183
Unique_Items_purchase_data = purchase_data["Item ID"].value_counts()
Unique_Items_purchase_data.head()
178    12
82      9
108     9
145     9
92      8
Name: Item ID, dtype: int64
Unique_Items_purchase_data = pd.DataFrame(Unique_Items_purchase_data)
Unique_Items_purchase_data.head()
Item ID
178	12
82	9
108	9
145	9
92	8
Most Profitable Items¶
​
