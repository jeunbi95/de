# Data Engineer

### 1
#### 총 내원일수 
-  select person_id, visit_start_date, visit_end_date, visit_end_date - visit_start_date::date+1 as coming_days from visit_occurrence;
#### 내원일수 최대최소
- select max(visit_end_date - visit_start_date::date+1) as max_coming_days, min(visit_end_date - visit_start_date::date+1) as min_coming_days  from visit_occurrence;

### 2
- select concept_name from concept where concept_id in (select distinct(condition_concept_id) from condition_occurrence) and concept_name  ~'[ABCDE]' and concept_name like '%heart%';

### 3
- create table drug_exposure_1891866 as select person_id, drug_concept_id, drug_exposure_start_date, drug_exposure_end_date, drug_exposure_end_date - drug_exposure_start_date::date as coming_days from drug_exposure order by coming_days desc;

### 4
문제자체가 이해가 안갑니다

### 5
- select count(person_id) 

from person 

where date_part('year', age(CURRENT_DATE, birth_datetime))::int >= 18 and 

person_id in (select person_id from condition_occurrence where condition_concept_id in (3191208,36684827,3194332,3193274,43531010,4130162,45766052, 45757474,4099651,4129519,4063043,4230254,4193704,4304377,201826,3194082,3192767)) and 

person_id in (select person_id from drug_exposure where drug_exposure_end_date-drug_exposure_start_date::date+1 >= 90);

### 6
패턴을 쿼리로 어떻게 골라내는지...?

#### 7
제공된 note는 메일에는 없고 어디에있는건가요 .....

