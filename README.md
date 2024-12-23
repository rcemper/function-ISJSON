<p align="right"><img src="https://github.com/isc-at/CPIPE/blob/master/archived.jpg"/></p>

## function  to check string if JSON object     
It's also an example of a customized SystemFunction extension (ZZISJSON) in Caché & IRIS    
This time it is to be included in %ZLANGF00.mac    

A JSON string is mostly imported from file or over REST    
You rely on a clean and compatible structure. This is the check.   

__required:__    ZPretty.mac  
available here https://github.com/rcemper/ZPretty-1 
or included in this repo in ZZISJSON.xml for classic install
or on OEX: https://openexchange.intersystems.com/package/ZPretty   
or
```
USER>ZPM "install pretty-json"
```
__demo__
```
USER>set jsn="{'Name':'Li,Robert K.','SSN':'672-92-9664','DOB':'1975-01-12','Home':{'Street':'986 Washington Blvd','City':'Boston','State':'PA','Zip':'95802'},'Office':{'Street':'6012 First Place','City':'Reston','State':'MT','Zip':'77739'},'Spouse':{'Name':'Avery,Zelda H.','SSN':'323-13-7437','DOB':'1943-03-27','Home':{'Street':'196 Main Drive','City':'Youngstown','State':'WY','Zip':'53229'},'Office':{'Street':'4056 Franklin Court','City':'Bensonhurst','State':'IA','Zip':'27688'},'FavoriteColors':['Black'],'Age':77},'Age':45,'Title':'Associate Marketing Manager','Salary':10421}"
USER>ZWRITE jsn  
jsn="{'Name':'Li,Robert K.','SSN':'672-92-9664','DOB':'1975-01-12','Home':{'Street':'986 Washington Blvd','City':'Boston','State':'PA','Zip':'95802'},'Office':{'Street':'6012 First Place','City':'Reston','State':'MT','Zip':'77739'},'Spouse':{'Name':'Avery,Zelda H.','SSN':'323-13-7437','DOB':'1943-03-27','Home':{'Street':'196 Main Drive','City':'Youngstown','State':'WY','Zip':'53229'},'Office':{'Street':'4056 Franklin Court','City':'Bensonhurst','State':'IA','Zip':'27688'},'FavoriteColors':['Black'],'Age':77},'Age':45,'Title':'Associate Marketing Manager','Salary':10421}"

USER>if $ZZISJSON(jsn) write "OK"   
OK

USER>set is(1)=$ZZISJSON(jsn),is(2)=$ZZISJSON(jsn_",home:") zwrite is   
is(1)=1
is(2)=0

```

[Article in DC](https://community.intersystems.com/post/function-check-if-string-json-object)  
