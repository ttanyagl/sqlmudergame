# sqlmudergame
_The detective gave you the crime scene report, but you somehow lost it. You vaguely remember that the crime was a ​murder​ that occurred sometime on ​Jan.15, 2018​ and that it took place in ​SQL City​. Start by retrieving the corresponding crime scene report from the police department’s database._

**Get the info about the murder**
```
select *
from crime_scene_report
where type="murder" and date=20180115 and city="SQL City"
```



![Image](https://user-images.githubusercontent.com/137061913/247024465-4fd53cc7-a9bd-4b96-bf37-371948a0ce44.png)


 

**Info from the 1st witness**
```
select *
from interview inter
join person pr on pr.id=inter.person_id
where pr.address_street_name="Northwestern Dr"
order by pr.address_number desc
limit 1
```



![Image](https://user-images.githubusercontent.com/137061913/247024697-3fcad275-fccf-463d-bec4-b7b290ca8b19.png)



**Info from the 2nd witness**
```
select *
from interview inter
join person pr on pr.id=inter.person_id
where pr.address_street_name="Franklin Ave" and pr.name like "%Annabel%"
```

![Image](https://user-images.githubusercontent.com/137061913/247024831-1dc6aa7d-f214-4125-821e-0ea2d415efdc.png)


**Murder's name**
```
select mem.name
from get_fit_now_member mem
join person pr on pr.id=mem.person_id
join drivers_license dr on dr.id=pr.license_id
join get_fit_now_check_in ch on ch.membership_id=mem.id
where mem.membership_status="gold" and dr.plate_number like "%H42W%" and ch.check_in_date=20180109
```



![Image](https://user-images.githubusercontent.com/137061913/247026074-abe87d2d-ee30-47ab-bb7a-ca36da4ede2e.png)

```
INSERT INTO solution VALUES (1, 'Jeremy Bowers');
        
        SELECT value FROM solution;
```



![Image](https://user-images.githubusercontent.com/137061913/247026284-d4de8f0b-5bdc-4ff8-9e9b-bc38a748a056.png)





**Let's find out who's the "real" villain**
```
_select *
from interview inter
join person pr on pr.id=inter.person_id
where name="Jeremy Bowers"_
```

```
select *
from person pr
join drivers_license dr on dr.id=pr.license_id
join facebook_event_checkin ch on ch.person_id=pr.id
where dr.gender="female" and dr.hair_color="red" and dr.car_make="Tesla" and dr.car_model="Model S" and dr.height between 65 and 67 and ch.event_name="SQL Symphony Concert"
```


<!-- Failed to upload "image.png" -->
```

INSERT INTO solution VALUES (1, 'Miranda Priestly');
        
        SELECT value FROM solution;
```



![Image](https://user-images.githubusercontent.com/137061913/247026979-125cdd6f-5335-4372-b3f4-4df1ba990dd6.png)
