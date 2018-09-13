
#### 用乘法原理 ####
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


