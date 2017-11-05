# Solving-the-problem-of-set-elements

Solving the problem of set elements

求集合元素问题（1,2x+1,3X+1类)

某集合Ａ中的元素有以下特征：


(1)数1是A中的元素

(2)如果X是A中的元素,则2x+1,3x+1也是A中的元素

(3)除了条件(1),(2)以外的所有元素均不是A中的元素

[参考程序1]

uses crt,dos;

var a:array[1..10000]of longint;

    b:array[1..10000]of boolean;
    
    times,n,m,long,i:longint;
    
    hour1,minute1,second1,sec1001:word;
    
   hour2,minute2,second2,sec1002:word;
   
begin

     write('N=');readln(n);
     
{    gettime(hour1,minute1,second1,sec1001);

     times:=minute1*60+second1;
     
     writeln(minute1,':',second1);}
     
     fillchar(b,sizeof(b),0);
     
     
     a[1]:=1;m:=2;long:=1;
     
     while long<=n do begin
     
           for i:=1 to long do
           
               if (a[i]*2=m-1) or (a[i]*3=m-1) then
               
                 if not b[m] then begin
                 
                  inc(long);a[long]:=m;b[m]:=true;break;
                  
               end;
               
           inc(m);
           
     end;
     
{     gettime(hour2,minute2,second2,sec1002);

     times:=minute2*60+second2-times;
     
     writeln(minute2,':',second2);
     
     writeln('Ok! Uses Time: ',times);}
     
     for i:=1 to n do write(a[i],' ');
     
readln;

end.

[参考程序2]

uses crt;

const n=10000;

var a:array[1..n] of longint;

    i,j,k,l,y:longint;
    
begin

     clrscr;
     
     fillchar(a,sizeof(a),0);
     
     i:=1;j:=1;
     
     
     a[i]:=1;
     
     repeat
     
           y:=2*a[i]+1;
           
           k:=j;
           
           while y〈a[k] do begin
           
                 a[k+1]:=a[k];
                 
                 k:=k-1;
                 
           end;
           
           if y>a[k] then begin
           
              a[k+1]:=y;j:=j+1;
              
              end
              
           else for l:=k+1 to j do a[l]:=a[l+1];
           
           j:=j+1;
           
           a[j]:=3*a[i]+1;
           
           inc(i);
           
     until k>=n;
     
     for i:=1 to n do begin
     
         write(a[i],' ');
         
         if (i mod 10 =0 ) or (i=n) then writeln
         
     end;
     
end.

[参考程序3]

uses crt;


var a:array[1..10000]of longint;

    n,i,one,another,long,s,x,y:longint;
    
begin

     write('n=');readln(n);
     
     a[1]:=1;long:=1;one:=1;another:=1;
     
     while longy then begin s:=y;inc(another);end
     
                   else begin s:=x;inc(one);inc(another);end;
                   
           inc(long);a[long]:=s;
           
     end;
     
     for i:=1 to n do write(a[i],' ');
     
end.

[参考程序4]

var n:integer;

    top,x:longint;
    
function init(x:longint):boolean;

begin

     if x=1 then init:=true
     
        else if((x-1)mod 2=0)and(init((x-1)div 2))
        
                     or((x-1)mod 3=0)and(init((x-1)div 3))then
                     
             init:=true
             
             else init:=false;
             
end;

begin

     write('input n:');
     
     readln(n);
     
     x:=0;
     
     top:=0;
     
     while top< n do begin
     
           x:=x+1;
           
           if init(x) then
           
              top:=top+1;
              
              write(x:8);
              
           end;
           
     write('output end.');
     
     readln
     
end.
