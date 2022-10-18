create database trecsol;

use trecsol;

create table info(
id int auto_increment primary key not null,
name varchar(250),
salary int
);

delimiter //
create procedure show1()
begin
select * from info;
end
//
delimiter ;

call show1;


delimiter //

create procedure insert_data(name varchar(250), salary int)
begin
insert into info (name ,salary)values (name ,salary);
end

// delimiter ;

call insert_data(("waseem"),(25000));
call insert_data(("waqas"),(28000));
call insert_data(("anabya"),(20000));
call insert_data(("akhtar"),(18000));
call insert_data(("muneeb"),(15000));
call insert_data(("shehzad"),(5000));
call insert_data(("laiq"),(25000));
call insert_data(("shahroon"),(5000));
call insert_data(("sajid"),(15000));
call insert_data(("mushtaq"),(5000));
call insert_data(("muneeb"),(22000));
call insert_data(("sameer"),(7000));
call insert_data(("adnan"),(12000));
call insert_data(("mukhtar"),(15000));
call insert_data(("laiba"),(5000));
call insert_data(("sonia"),(5000));
call insert_data(("naveed"),(7000));
call insert_data(("faizan"),(22000));
call insert_data(("sameer"),(7000));
call insert_data(("umair"),(17000));
call insert_data(("ahsan"),(5000));
call insert_data(("afnan"),(7000));
call insert_data(("haider"),(18000));

call show1;


select name , salary ,
case
when salary<= 20000  and  salary>=25000 then "seniors"
when salary<= 10000  and  salary>=19000 then "freshiers"
when salary<= 100  and  salary>=9000 then "inters"
else "optional" end as "positions" from info;
