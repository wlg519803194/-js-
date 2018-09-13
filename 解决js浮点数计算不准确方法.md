采集于[https://blog.csdn.net/Lucky_LXG/article/details/71124375](https://blog.csdn.net/Lucky_LXG/article/details/71124375)


#### 乘法 ####
	function accMul(arg1,arg2) {
	 	var count=0,s1=arg1.toString(),s2=arg2.toString();   
	 	try{count+=s1.split(".")[1].length}catch(e){}      
	 	try{count+=s2.split(".")[1].length}catch(e){}
	 return Number(s1.replace(".",""))*Number(s2.replace(".",""))/Math.pow(10,count) 
	 }
	 Number.prototype.mul = function (arg){     
	 	return accMul(arg, this); 
	 }

1. 先把得到的浮点数转换成字符串，去掉字符串中的小数点，并且得到
   得到小数点后面的位数，把所有小数点的位数都加起来得到count
2. 再把去除小数点的数字做运算得到sum
3. 最后sum/10的count次方



#### 除法 ####

	 
	function FloatDiv(arg1,arg2){   
 
        var t1=0,t2=0,r1,r2;   
 
        try{t1=arg1.toString().split(".")[1].length}catch(e){}   
 
        try{t2=arg2.toString().split(".")[1].length}catch(e){}   
 
        with(Math){   
 
            r1=Number(arg1.toString().replace(".",""));
 
   
 
            r2=Number(arg2.toString().replace(".",""));   
 
            return (r1/r2)*pow(10,t2-t1);   
 
        }   
 
  	}


#### 减法 ####


	 
 	function FloatSub(arg1,arg2){  
 
      var r1,r2,m,n;  
 
      try{r1=arg1.toString().split(".")[1].length}catch(e){r1=0}  
 
      try{r2=arg2.toString().split(".")[1].length}catch(e){r2=0}  
 
      m=Math.pow(10,Math.max(r1,r2));  
 
      //动态控制精度长度  
 
      n=(r1>=r2)?r1:r2;  
 
      return ((arg1*m-arg2*m)/m).toFixed(n);  
 
  	}  

#### 加法 ####


	 
 	function FloatAdd(arg1,arg2){  
 
       var r1,r2,m;  
 
       try{r1=arg1.toString().split(".")[1].length}catch(e){r1=0}  
 
       try{r2=arg2.toString().split(".")[1].length}catch(e){r2=0}  
 
       m=Math.pow(10,Math.max(r1,r2));  
 
       return (arg1*m+arg2*m)/m;  
 
  	}  

 

 



