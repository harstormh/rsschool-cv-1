<html>
#Максим Свиридов# 
<h2> Номер тел.+37522222222 </h2>
<h3>О себе:</h3> Есть мысль о том что теории и практики в колледже котором я учусь, не хватит, для нахождения полноценной работы программистом. Участвую в этих курсах по совету друга. Я являюсь позитивным человеком и если я берусь за дело, то только обстоятельства из вне могут мне помешать его сделать. Надеюсь смогу влиться в этот процесс, ибо для меня самое сложное это начать разбираться. Думаю причиной этого является скудный теоретический и практический опыт. Есть не большой опыт писания кода в Delphi.<h3>
<h4>Пример кода: </h4>
'''
program Project11;  
uses  
SysUtils;  
type cheloveki = record  
name:string;  
age:integer;  
zp:extended;  
end;  
var  
v:string;  
i,j,count,n,min,p,i1,j1,d1,agez,voz,zarp:integer;  
f1,f2,f3:textfile;  
nl,nr,z,x:integer;  
count1,zpz:extended;  
f,b,nm:integer;  
s,e0,e1,e2:string;  
chel:array[1..4] of cheloveki;  

procedure vvod;  
begin  
count := 0;  
while count < 4 do  
begin  
count := count+1;  
writeln('Введите имя ',count,'-го сотрудника ');  
read(chel[count].name);  
writeln('Введите возраст ',count,'-го сотрудника ');  
read(chel[count].age);  
writeln('Введите зарплату ',count,'-го сотрудника ');  
readln(chel[count].zp);  
end;  
end;  

procedure sort1;  
begin  
for i := 1 to 4 do  
begin  
min:=i;  
for j := i+1 to 4 do  
if (chel[j].name<chel[min].name) then  
min:=j;  
s:=chel[i].name;{имя} agez:= chel[i].age;{возраст} zpz:= chel[i].zp; {зарплата}  
chel[i].name:=chel[min].name; {} chel[i].age:=chel[min].age; {} chel[i].zp:=chel[min].zp;  
chel[min].name:=s; {} chel[min].age:=agez; {} chel[min].zp:=zpz;  
end;  
writeln('Отсортированные имена: ');  
for i := 1 to 4 do  
begin  
e1:= floattostr(int(chel[i].zp));  
e2:= floattostr(frac(chel[i].zp));  
delete(e2,1,1);  
e0:=e1+e2;  
writeln(chel[i].name,' ', chel[i].age,' ',e0);  
end;  
readln;  
end;  

procedure sort2 (l,r:integer);  
begin  
nl:=l;  
nr:=r;  
z:=chel[(l+r) div 2].age;  
repeat  
while chel[nl].age < z do  
nl:=nl+1;  
while chel[nr].age > z do  
nr:=nr-1;  
if nl<=nr then  
begin  
s:=chel[nl].name; {} x:=chel[nl].age; {} zpz:= chel[nl].zp;  
chel[nl].name:=chel[nr].name; {} chel[nl].age:=chel[nr].age; {} chel[nl].zp:=chel[nr].zp;  
chel[nr].name:=s; {} chel[nr].age:=x; {} chel[nr].zp:=zpz;  
nl:=nl+1;  
nr:=nr-1;  
end;  
until nl>nr;  
if nr>l then  
begin  
sort2(l,nr);  
writeln('Отсортированный возраст: ');  
for p := 1 to 4 do  
begin  
e1:= floattostr(int(chel[p].zp));  
e2:= floattostr(frac(chel[p].zp));  
delete(e2,1,1);  
e0:=e1+e2;  
writeln(chel[p].name,' ', chel[p].age,' ',e0);  
end;  
readln;  
end;  
if nl<r then  
begin  
sort2(nl,r);  
writeln('Отсортированный возраст: ');  
for p := 1 to 4 do  
begin  
e1:= floattostr(int(chel[p].zp));  
e2:= floattostr(frac(chel[p].zp));  
delete(e2,1,1);  
e0:=e1+e2;  
writeln(chel[p].name,' ', chel[p].age,' ',e0);  
end;  
readln;  
end;  
end;  

procedure sort3;  
begin  
d1:=4;  
d1:=d1 div 2;  
while (d1>0) do  
begin  
for i1 := 1 to 4-d1 do  
begin  
j1:=i1;  
while((j1>0) and (chel[j1].zp>chel[j1+d1].zp)) do  
begin  
count1:=chel[j1].zp;  
chel[j1].zp:=chel[j1+d1].zp;  
chel[j1+d1].zp:=count1;  
j1:=j1-1;  
end;  
end;  
d1:=d1 div 2;  
end;  
writeln('Отсортированная зарплата: ');  
for i1 := 1 to 4 do  
begin  
e1:= floattostr(int(chel[i1].zp));  
e2:= floattostr(frac(chel[i1].zp));  
delete(e2,1,1);  
e0:=e1+e2;  
writeln(chel[i1].name,' ', chel[i1].age,' ',e0);  
end;  
readln;  
end;  

procedure vyvod1;  
begin  
assignfile(f1,'E:\delphi\1.txt');  
rewrite(f1);  
for i := 1 to 4 do  
begin  
e1:= floattostr(int(chel[i].zp));  
e2:= floattostr(frac(chel[i].zp));  
delete(e2,1,1);  
e0:=e1+e2;  
writeln(f1, chel[i].name,' ', chel[i].age,' ',e0);  
end;  
closefile(f1);  
end;  

procedure vyvod2;  
begin  
assignfile(f2,'E:\delphi\2.txt');  
rewrite(f2);  
for p := 1 to 4 do  
begin  
e1:= floattostr(int(chel[p].zp));  
e2:= floattostr(frac(chel[p].zp));  
delete(e2,1,1);  
e0:=e1+e2;  
writeln(f2,chel[p].name,' ', chel[p].age,' ',e0);  
end;  
closefile(f2);  
end;  

procedure vyvod3;  
begin  
assignfile(f3,'E:\delphi\3.txt');  
rewrite(f3);  
for i1 := 1 to 4 do  
begin  
e1:= floattostr(int(chel[i1].zp));  
e2:= floattostr(frac(chel[i1].zp));  
delete(e2,1,1);  
e0:=e1+e2;  
writeln(f3, chel[i1].name,' ', chel[i1].age,' ',e0);  
end;  
closefile(f3);  
end;  
begin  
writeln('Правила:');  
writeln('{Кол-во сотрудников: 4}');  
writeln('{Сотрудники этой организации не должны зарабатывать больше 9999,99}');  
vvod;  
sort1;  
vyvod1;  
sort2(1,2);  
vyvod2;  
sort3;  
vyvod3;  
readln;  
readln;  
end. 
''' 
</html>

