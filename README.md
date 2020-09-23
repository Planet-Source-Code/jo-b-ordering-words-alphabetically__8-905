<div align="center">

## Ordering Words Alphabetically


</div>

### Description

This code shows how we can alphabetically order an array of words. I think it's pretty easy to understand. I also attached a 'counter' so we can track how many msecs the procedure will take. I added a function that will 'transform' all string to lower case as well as removing accented characters. This way we're sure the order will be correct.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Jo B](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/jo-b.md)
**Level**          |Intermediate
**User Rating**    |5.0 (20 globes from 4 users)
**Compatibility**  |PHP 3\.0, PHP 4\.0
**Category**       |[Algorithims](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/algorithims__8-29.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/jo-b-ordering-words-alphabetically__8-905/archive/master.zip)





### Source Code

```
<?php
function chgString($string) {
return strtolower(strtr($string,
"ŠŒŽšœžŸ¥µÀÁÂÃÄÅÆÇÈÉÊËÌÍÎÏÐÑÒÓÔÕÖØÙÚÛÜÝßàáâãäåæçèéêëìíîïðñòóôõöøùúûüýÿ",
"SOZsozYYuAAAAAAACEEEEIIIIDNOOOOOOUUUUYsaaaaaaaceeeeiiiionoooooouuuuyy"));
}
//if $order != 'ASC' result will be 'DESC'
 $order="ASC";
//You can add as many as you want
 $str[0]="john";
 $str[1]="bettencourt";
 $str[2]="francis";
 $str[3]="susan";
 $str[4]="mary";
 $total=count($str);
 $a=1;
 while($a<$total+1){
 	$i=0;
 	while($i<$total+1){
 		if (strcmp(chgString($flag),chgString($str[$i]))<0){
 		$flagid=$i;
 		$flag=$str[$i];
 		}
 	$i++;
 	}
 if ($order=="ASC"){
 $strfinal = $str[$flagid]."<BR>".$strfinal;
 }else{
 $strfinal = $strfinal."<BR>".$str[$flagid];
 }
 $str[$flagid]="";
 $flag="";
 $a++;
 }
 //the result is helded in var $strfinal
 $timeEnd=microtime();
 $deltatime=($timeEnd-$timeStart);
 $esttime=($deltatime*10000)/$total;
 echo "<B>Alphabetical Result:</B><BR>$strfinal</B><BR>Done in $deltatime msecs";
 echo "<BR>The estimated time for performing this operation on 10000 words is aprox: $esttime ms (can vary depending on the words size)";
 ?>
```

