# 1. Total no. of suicides (1985-2016)
select sum(suicides_no) as total_suicides from master

![1](https://github.com/Gouravdeep-Singh/Suicide_analysis/assets/104523395/c4ec3385-9970-48f1-84db-999452ecd832)


# 2. Suicide per gender
select g.sex, sum(m.suicides_no) as suicides from master m inner join gender g on g.id=m.id group by g.sex

