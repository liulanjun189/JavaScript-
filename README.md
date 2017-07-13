# JavaScript-
学习JavaScript的部分练习整理————1

//在控制台打印九九乘法口诀
for (var i = 0; i <=9; i++) {
  	for (var j =1,str=" "; j <=i; j++) {
  		str+=i+"*"+j+"="+i*j+" ";
  		
  	}
  	console.log(str);
  }
//用*号打印直角三角形
 for (var i = 0; i <=9; i++) {
  	for (var j =1,str=" "; j <=i; j++) {
  		str+="*"+" ";
  		
  	}
  	console.log(str);
  }
//用*号打印等腰三角形
for (var i = 0; i <9; i++) {
  	var str=" ";
  	for (var j =0; j <9-i; j++) {
  		str+=" ";
  		
  	}
  	for (var k = 0; k < 9-j; k++) {
  			str=str+"*"+" ";
  		}
  		
  	console.log(str);
  }
//冒泡排序
var str=[6,5,1,0,2,4];
for (var i = 0; i < str.length-1; i++) {
	for (var j = 0; j < str.length-i; j++) {
		   if(str[j]>str[j+1]){
		   		str[j+1]=str[j]+str[j+1];
		   		str[j]=str[j+1]-str[j];
		   		str[j+1]=str[j+1]-str[j];

		   }
	}
}
console.log(str);
//仿写验证码
	var chars=[];
	for (var i = 48; i <=57; i++) {
		chars.push(String.fromCharCode(i));
	}
	for (var j = 65; j <=90; j++) {
		chars.push(String.fromCharCode(j));
	}
	for (var k = 97; k <=122; k++) {
		chars.push(String.fromCharCode(k));
	}
	function getCode(){
		var code=[];
		while(code.length<4){
			var i=Math.floor(Math.random()*chars.length);
			code.push(chars[i]);
		}
		return code.join("");
	}
	var code=getCode();
	while(true){
		var input=prompt("请输入验证码"+code);
		if(input.toLowerCase()!=code.toLowerCase()){
			console.log("您的输入有误，请重新验证");
			code=getCode();
		}else{
			document.write("验证成功！");
			break;
		}
	}
//数组去重
var str=[1,1,1,2,1,3,2,4,3,5,4,5];
 var newstr=[];
for (var i = 0,res="1"; i < str.length; i++) {
	for(var key in str){
			if(newstr[key]==str[i]){
				res="2";
				break;
			}
	}
		if(res=="1"){
				newstr[newstr.length]=str[i];
			}
			res="1";
}
//indexOf重写
var arr=[1,2,3,4,5];
if(Array.prototype.indexOF==undefined){
	Array.prototype.indexOF=function(elem,start){
			start===undefined && (start=0);
			for (var i = 0; i < this.length; i++) {
				if(this[i]===elem){
					return i;
				}
			}
			return -1;
	};
}
