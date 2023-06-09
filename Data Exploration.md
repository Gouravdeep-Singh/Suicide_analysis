# 1. Total no. of suicides (1985-2016)
select sum(suicides_no) as total_suicides from master

![1](https://github.com/Gouravdeep-Singh/Suicide_analysis/assets/104523395/c4ec3385-9970-48f1-84db-999452ecd832)


# 2. Suicide per gender
select g.sex, sum(m.suicides_no) as suicides from master m inner join gender g on g.id=m.id group by g.sex

![2](https://github.com/Gouravdeep-Singh/Suicide_analysis/assets/104523395/27d2c667-cee3-4166-aa63-da59ef0f2a6a)

# 3. Suicide per age group
select age, sum(suicides_no) as suicides from master group by age

![3](https://github.com/Gouravdeep-Singh/Suicide_analysis/assets/104523395/df8ecfed-814b-45a8-b1f7-b86fa6fa58a2)

# 4. Suicide per age group and gender
select g.sex, m.age, sum(m.suicides_no) as suicides from master m inner join gender g
on g.id=m.id group by g.sex, m.age order by age 

![4](https://github.com/Gouravdeep-Singh/Suicide_analysis/assets/104523395/f5027ed2-5a92-4c3c-a47f-3730e96d9c19)

# 5. Top N countries per suicides
select c.nation, sum(m.suicides_no) as suicides from master m 
inner join country c on c.id=m.id group by c.nation order by suicides DESC limit 8

![1](https://github.com/Gouravdeep-Singh/Suicide_analysis/assets/104523395/43b6005e-c2bf-424a-be0a-94744f9be050)

# 6. Details of year with highest suicides
year: select year, sum(suicides_no) as suicides from master group by year order by suicides DESC limit 5

![1](https://github.com/Gouravdeep-Singh/Suicide_analysis/assets/104523395/3443ca4d-9e55-49e2-808f-170ea5edc28b)

Details: select m.year, g.sex, m.age, sum(m.suicides_no) as suicides from master m
inner join gender g on g.id=m.id where m.year=1999 group by g.sex,m.age order by suicides desc limit 1

![1](https://github.com/Gouravdeep-Singh/Suicide_analysis/assets/104523395/2d2243ab-950d-44d8-8650-ddc7e8e68aaa)



# 7. Details about country with highest suicides
country: select c.nation,m.year, sum(m.suicides_no) as suicides from master m inner join country c
on c.id=m.id group by c.nation,m.year order by suicides desc limit 1

![1](https://github.com/Gouravdeep-Singh/Suicide_analysis/assets/104523395/098ff17c-8545-4c55-9cdf-92c46643491d)

Deatils: select c.nation,m.year,g.sex, m.age,sum(m.suicides_no) as suicides from master m inner join country c
on c.id=m.id inner join gender g on c.id=g.id  group by c.nation,m.year,g.sex,m.age order by suicides desc limit 1

![1](https://github.com/Gouravdeep-Singh/Suicide_analysis/assets/104523395/c215c8b8-42b3-4000-9f72-780cc75e4867)






