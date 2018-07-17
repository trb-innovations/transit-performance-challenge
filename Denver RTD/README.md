## Rolling Assets Technical Break Down and Operational Data Set

[_Gemechisa.ayana@rtd-denver.com_](mailto:Gemechisa.ayana@rtd-denver.com)

_07/09/2018_

The data set is for fleets break downs (technical symptom cause) and operational customers count on a route and trip level. There are five types of data set of breakdown and operational trip information

1. **[Break down information](https://github.com/trb-innovations/transit-performance-challenge/blob/master/Denver%20RTD/Fleets%20Technical%20Breakdown0117to0618.csv)** – Has the duration of the breakdown, on the route name, date time stamp with the technical symptom codes. (Fleets technical breakdown0117to0618.csv)

    **Meta Data**
    
    The provided data set for Break down information is from Q1 2017 to Q2, 2018 and has 5,354 rows.

    |Column\_name     |       Column\_type    |    Column\_desc|
    |-------------------|-----------------------|------------------|
    |DATETIME\_OCCURED|DATE|Incident Date|
    |INC\_ID  | Number | Incident ID (PK)|
    |VEHICLE\_ID  |VARCHAR2 (20)|  Vehicle Side Number = _NOM\_VEHICLE.ID_|
    |ROUTE  | VARCHAR2 | Route or Line Name _= NOM\_LINE.CODE_|
    |DELAY\_MINUTES |  Number | Lost service minutes|
    |SYMPTOM\_SYMPTOM | VARCHAR2 (20) | Symptom Codes|
    |DESCRIPTION |VARCHAR2 (200)| Description of the incident|

    **Sample Data**

    DATETIME\_OCCURRED,INC\_ID,VEHICLE\_ID,ROUTE,DELAY\_MINUTES,SYMP\_SYMPTOM,DESCRIPTION

    6/29/2018 5:05:00 PM,2468682,LRV269,101,33,3100,OP ADVISED FRICTION BRAKE C-TRUCKý KEY OUT/UP DIDN`T CLEARý ADVISED TO CUT C TRUCK CONFIRMED IN A CAB. OP ADVISED AND CONFIRMED CUT OUT 7 TIMES. ADVISED ON LOCATION OF C TRUCK ROTA

    6/29/2018 6:53:00 PM,2468614,LRV263,101,3,3122,LRV263 ADA RAMP BY DOOR 4ý LATCH WOULD NOT RELEASE RAMP FROM WALL EASILY. OP LEFT RAMP DOWN UNTIL PULL IN.   CAB B

    6/29/2018 4:08:00 PM,2468525,1534,P,19,0505,WOULDN?T START// TRADED CALLED CCS WILL PROB BE LATE

    6/29/2018 1:36:00 PM,2468424,6154,51,29,0022,STOP ENGINE LIGHT; -29 MIN

    6/29/2018 12:10:00 PM,2468389,6063,45,10,1030,BUS WILL NOT GO/NO LEAKS/ASKED HIM TO TURN BUS OFF FOR 30 SEC AND RESTART/IT STARTED TO MOVE AGAIN///1220 BUS BROKE DOWN AGAIN/THIS TIME HE SAID THE RAMP LIGHT IS ON/I ASKED HIM TO



2.  **[Trip Information](https://github.com/trb-innovations/transit-performance-challenge/tree/master/Denver%20RTD/Vehicle%20Trip)** – Has Information about the Vehicle trips, all trips performed by Vehicle during a day.

    **Meta Data**

    The dataset for the the Q1 2018 Vehicle trips (split into 6 smaller files) contains the following columns:

    |Column\_name     |       Column\_type    |    Column\_desc|
    |-------------------|-----------------------|------------------|
    |OPD\_DATE        |        DATE    |                    Operational Date|
    |VEHICLE\_ID       |         Number |               ID of the vehicle|
    |MASTER\_ID         |       Number   |             ID of the master-vehicle in case of coupled vehicles|
    |EVENT\_NO           |     Number     |           ID of the event|
    |EVENT\_NO\_COURSE    |    Number|
    |METERS              |  Number    |            Odometer at the time of the event
    |ACT\_DEP\_TIME      |          Number|                Actual start time of the trip
    |NOM\_DEP\_TIME |       Number         |       Scheduled (Nominal) start time of the trip
    |NOM\_END\_TIME  |      Number          |      Scheduled (Nominal) end time of the trip
    |ACT\_END\_TIME   |             Number   |             Actual end time of the trip
    |LINE\_ID          |              Number  |              ID of the line
    |COURSE\_ID         |       Number         |       ID of the course
    |TRIP\_ID            |            Number    |            ID of the trip
    |PATTERN\_ID          |      Number          |      ID of the pattern
    |PATTERN\_DIRECTION    |    VARCHAR2          |      Direction on Pattern
    |TRIP\_TYPE |               Number |               differentiate between service journeys and dead runs
    |BLOCK\_ID   |             Number   |             ID of the block
    |TIME\_GRP\_ID|                Number|                ID of the time group
    |TRIP\_CODE    |            Number    |            Code of the trip

    **Sample Data**
    OPD\_DATE,VEHICLE\_ID,MASTER\_ID,EVENT\_NO,EVENT\_NO\_COURSE,METERS,ACT\_DEP\_TIME,NOM\_DEP\_TIME,NOM\_END\_TIME,ACT\_END\_TIME,LINE\_ID,COURSE\_ID,TRIP\_ID,PATTERN\_ID,PATTERN\_DIRECTION,TRIP\_TYPE,BLOCK\_ID,TIME\_GRP\_ID,TRIP\_CODE

    3/31/2018,4308988,,1499194019,1499193951,0,91629,91620,93840,97195,4342329,2154,8949275,92798040,W-Bound,0,2154,9050721,111687574

    3/31/2018,4308988,,1499194010,1499193951,0,88209,88200,90420,90326,4342329,2154,8949273,860435638,E-Bound,0,2154,9050337,111687476

    3/31/2018,4308988,,1499194000,1499193951,0,84428,84420,86640,86689,4342329,2154,8949272,92798040,W-Bound,0,2154,9050732,111687578

    3/31/2018,4308988,,1499193991,1499193951,0,81025,81000,83220,83108,4342329,2154,8949270,860435638,E-Bound,0,2154,9050341,111687480

    3/31/2018,4308988,,1499193982,1499193951,0,77253,77220,79440,79560,4342329,2154,8949269,92798040,W-Bound,0,2154,9050736,111687582

    3/31/2018,4308988,,1499193973,1499193951,0,73824,73800,76020,75953,4342329,2154,8949267,860435638,E-Bound,0,2154,9050345,111687484

    3/31/2018,4308988,,1499193961,1499193951,0,70154,70020,72240,72713,4342329,2154,8949266,92798040,W-Bound,0,2154,9050751,111687586

    3/31/2018,4308988,,1499193952,1499193951,0,66617,66600,68820,68749,4342329,2154,8949264,860435638,E-Bound,0,2154,9050349,111687488

    3/31/2018,4308986,,1498063487,1498063441,0,89828,89820,92040,92422,4342329,2153,8949235,92798040,W-Bound,0,2153,9050729,111687575

    3/31/2018,4308986,,1498063478,1498063441,0,86480,86400,88620,88558,4342329,2153,8949233,860435638,E-Bound,0,2153,9050338,111687477

    3/31/2018,4308986,,1498063469,1498063441,0,82628,82620,84840,84890,4342329,2153,8949232,92798040,W-Bound,0,2153,9050733,111687579

    3/31/2018,4308986,,1498063460,1498063441,0,79209,79200,81420,81324,4342329,2153,8949072,860435638,E-Bound,0,2153,9050342,111687481

    3/31/2018,4308986,,1498063451,1498063441,0,75427,75420,77640,77744,4342329,2153,8949071,92798040,W-Bound,0,2153,9050737,111687583

    3/31/2018,4308986,,1498063442,1498063441,0,72018,72000,74220,74172,4342329,2153,8949069,860435638,E-Bound,0,2153,9050346,111687485

    3/31/2018,4308986,,1498063432,1498063301,0,68227,68220,70440,70498,4342329,2157,8949673,92798040,W-Bound,0,2157,9050752,111687587

    3/31/2018,4308986,,1498063423,1498063301,0,64883,64800,67020,67025,4342329,2157,8949671,860435638,E-Bound,0,2157,9050350,111687489

    3/31/2018,4308986,,1498063414,1498063301,0,61926,61920,64140,64171,4342329,2157,8949670,92798040,W-Bound,0,2157,9050818,111687621

    3/31/2018,4308986,,1498063405,1498063301,0,58506,58500,60720,60607,4342329,2157,8949668,860435638,E-Bound,0,2157,9050501,111687520

    3/31/2018,4308986,,1498063396,1498063301,0,55626,55620,57840,57838,4342329,2157,8949667,92798040,W-Bound,0,2157,9050759,111687594

    3/31/2018,4308986,,1498063387,1498063301,0,52206,52200,54420,54340,4342329,2157,8949665,860435638,E-Bound,0,2157,9050373,111687496


3. **[Vehicle Trip Passenger](https://github.com/trb-innovations/transit-performance-challenge/tree/master/Denver%20RTD/Vehicle%20Trip%20Passenger)** – Lists of all trips performed by vehicles during a day with passenger information.

    The dataset for the the Q1 2018 Vehicle trip passenger (split into 6 smaller files) contains trip detail, route name and Vehicle Side Number can be found from **Vehicle Trip** using an event number, id from **nom\_vehicle** and Route name using &#39;Code&#39; from **Nom\_Line** respectively.

    |Column\_name     |       Column\_type    |    Column\_desc|
    |-------------------|-----------------------|------------------|
    |OPD\_DATE         |       DATE      |                  Operational Date|
    |VEHICLE\_ID        |        Number   |             ID of the vehicle (fk) nom\_vehicle. Vehicle\_ID|
    |MASTER\_ID          |      Number     |           ID of the master-vehicle for coupled vehicles (fk) nom\_vehicle. Vehicle\_ID|
    |EVENT\_NO  |              Number       |         Unique ID of the event (pk)|
    |EVENT\_NO\_COURSE|        Number        |        Event Course|
    |METERS            |    Number            |    Odometer at the time of the event|
    |ACT\_DEP\_TIME     |           Number     |           Actual start time of the trip|
    |NOM\_DEP\_TIME      |  Number              |  Scheduled (Nominal) start time of the trip|
    |NOM\_END\_TIME       | Number               | Scheduled (Nominal) end time of the trip|
    |ACT\_END\_TIME        |        Number        |        Actual end time of the trip|
    |LINE\_ID               |         Number       |         ID of the line (fk) nom\_line.Line\_id|
    |COURSE\_ID              |  Number              |  ID of the course|
    |TRIP\_ID                 |       Number         |       ID of the trip (fk) nom\_trip. Trip\_ID|
    |PATTERN\_ID               | Number               | ID of the pattern (fk) nom\_pattern.Pattern\_ID|
    |PATTERN\_DIRECTION|        VARCHAR2               | Direction on Pattern|
    |TRIP\_TYPE         |       Number              |  differentiate between service journeys and dead runs|
    |BLOCK\_ID           |     Number                |ID of the block (fk) p\_nom|
    |TIME\_GRP\_ID        |        Number             |   ID of the time group (fk) p\_nom|
    |TRIP\_CODE            |    Number  |              Code of the trip|
    |DATA\_SOURCE           |     NUMBER |               Indicator for the source of the data and validation module processing|
    |IS\_ADDITIONAL\_TRIP|        NUMBER|                FLAG|
    |PASSENGER\_IN        |        NUMBER|                Number of boarding passengers|
    |PASSENGER\_OUT        |        NUMBER|                Number of alighting passengers|
    |PASSENGER\_AVG         |       NUMBER |               Average number of passengers on board|

    **Sample Data**
    OPD\_DATE,VEHICLE\_ID,MASTER\_ID,EVENT\_NO,EVENT\_NO\_COURSE,METERS,ACT\_DEP\_TIME,NOM\_DEP\_TIME,NOM\_END\_TIME,ACT\_END\_TIME,LINE\_ID,COURSE\_ID,TRIP\_ID,PATTERN\_ID,PATTERN\_DIRECTION,TRIP\_TYPE,HIGHWAY\_TYPE,PATTERN\_QUALITY,BLOCK\_ID,PASSENGER\_DATA,TIME\_GRP\_ID,TRIP\_CODE,DRIVER\_ID,DATA\_SOURCE,IS\_ADDITIONAL\_TRIP,PASSENGER\_IN,PASSENGER\_OUT,PASSENGER\_AVG
    
    1/5/2017,9317,,1044821982,1044821636,179072,76156,75660,78360,78345,83,1741,6121931,653785005,E-Bound,0,,94,1741,1,6426385,110494354,15769,4,0.000000000000000,9,9,4.18864986446739
    
    1/5/2017,9354,,1045100696,1045100617,133061,34695,34680,36060,35941,1000560,1071,6114213,239682211,S-Bound,0,,100,1071,1,6414950,110482918,18547,4,0.000000000000000,33,33,29.0044359622427
    
    1/5/2017,6286,,1044953804,1044953213,177040,50782,50760,54600,54714,121,1639,6113103,328162651,N-Bound,0,,100,1639,1,6415143,110483154,21661,4,0.000000000000000,18,18,4.73303708129504
    
    1/5/2017,9349,,1045100127,1045100126,175,20601,21360,22980,23181,4447227,1142,6438881,217788578,,2,,100,1142,1,6438644,953879569,19936,4,0.000000000000000,0,0,0
    
    1/5/2017,1000000,,1046338929,1046338787,0,40410,40440,42720,42995,103,103,6129298,397899170,E-Bound,0,,100,103,1,6413274,110481265,,4,0.000000000000000,19,19,11.0821770110632
    
    1/5/2017,1000007,,1046339213,1046339209,0,66824,66824,-1,66924,101,0,,156150115,N-Bound,0,,66,0,1,,0,,4,0.000000000000000,2,2,0
    
    1/5/2017,9380,,1044961138,1044960795,149116,51865,51660,56400,56566,1000589,1661,6129192,622405341,E-Bound,0,,100,1661,1,6417551,110485500,21594,4,0.000000000000000,67,67,17.0843175177976
    
    1/5/2017,9375,,1044823984,1044823966,61177,52927,52800,56100,56466,83,1757,6110261,276631208,E-Bound,0,,80,1757,1,6426377,110494368,20337,4,0.000000000000000,24,24,9.26221285986558
    
    1/5/2017,9379,,1044824621,1044824620,78269,56021,56040,59040,56021,1000589,1765,6443539,135792705,,2,,50,1765,1,6443468,956623836,14006,4,0.000000000000000,0,0,0
    
    1/5/2017,9389,,1044825313,1044825303,343,16526,16200,18900,19188,1000589,1637,6115641,973960365,W-Bound,0,,100,1637,1,6417713,110485542,17792,4,0.000000000000000,8,8,3.35917670896875
    
    1/5/2017,6289,,1045095672,1045095371,89664,29112,29100,35400,35604,21,1648,6116854,824610992,W-Bound,0,,100,1648,1,6419557,110487501,17860,4,0.000000000000000,23,23,2.67012303103738
    
    1/5/2017,9390,,1044961813,1044961807,13225,20089,20100,20940,20799,1000586,1074,6128212,266493530,N-Bound,0,,100,1074,1,6409788,110478038,15138,4,0.000000000000000,7,7,6.89315393747527

4. **[Nom\_Line](Nom_Line.csv)** – Lists of all line definitions, aka RTD Routes

    |Column\_name     |       Column\_type    |    Column\_desc|
    |-------------------|-----------------------|------------------|
    |Line\_ID |               Number   |             Unique ID|
    |CODE     |           VARCHAR2      |          Line Code or Route name|
    |VALID\_FROM|        DATE            |            Date the line is valid from (inclusive)|
    |VALID\_UNTIL|        DATE            |            Date of last day the line is valid (exclusive)|
    |SNAME        |        VARCHAR2        |        Line Short Name|
    |LNAME         |       VARCHAR2         |       Line Long Name|

    **Sample Data**
    
    ID,CODE,VALID\_FROM,VALID\_UNTIL,SNAME,LNAME

    1000496,MDCR,1/1/1970,1/1/2036,682,Meridian call-n-Ride

    1000497,NICR,1/1/1970,1/1/2036,683,North Inverness call-n-Ride

    30,30,1/1/1970,1/1/2036,30,South Federal Blvd

5. **[Nom\_Vehicles](Nom_Vehicles.csv)** – Lists of all Revenue fleets

    |Column\_name     |       Column\_type    |    Column\_desc|
    |-------------------|-----------------------|------------------|
    |ID     |           Number      |          Unique Vehicle ID|
    |CODE       |            VARCHAR2|                Vehicle Side Number|
    |VEHICLE\_CLASS |       VARCHAR   |             Type of the fleet|

    **Sample Data**

    ID,CODE,VEHICLE\_CLASS

    1606,1606,BUS

    1631,1631,BUS

    1633,1633,BUS

    1635,1635,BUS

    1000000,LRV101,LRV

    1000001,LRV103,LRV
