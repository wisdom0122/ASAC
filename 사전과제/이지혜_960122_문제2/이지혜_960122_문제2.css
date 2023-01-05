<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>지혜의 음료자판기</title>
<style>
button {
    height: 40px;
}
#money > button {
    width: 100px;
    height: 100px;
	border-radius: 100%;
    background-color: transparent;
}
#calc {
    height: 40px;
    text-align: right;
}
#menu > button {

    width: 100px;
    height: 100px;
    background-color: transparent;

}

#screen {
    width: 235px;
    border: 0px;
    text-align: right;
}
#spend {
    height: 40px;
    text-align: right;
}
#menu {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
#money {
    display:grid;
    grid-template-columns: 1fr 1fr 1fr;
}

.layout {
    width:350px;
    height:700px;
    border: 2px solid black;
}

</style>
<script>
 
var inputSum = 0;    // 투입액 합계
var productSum = 0;    // 상품 합계

var obj = function(name, count, price){    // 상품 Object
    this.name = name;
    this.count = count;
    this.price = price;
};
 
// obj의 배열이더라도 type 은 var다
var objArr = [];    // 상품들의 배열
 
/* 돈 투입 */
function func1(btn){
    var f1 = document.querySelector('#calc');
    inputSum += Number(btn.innerHTML);
    f1.setAttribute('value', inputSum);

    if (inputSum > 10000) {
        inputSum = 10000
        f1.setAttribute('value', inputSum);
    }
};
 
/* 스크린 출력 */
function printScreen(name){    // 출력할 상품의 이름을 넘김
    var sc = document.querySelector('#screen');
    var str='';
    for( var i in objArr ){    // 상품 배열 중에서
        if(objArr[i].name==name){    // 선택된 이름만 출력
            // 상품 정보를 담은 텍스트 생성
            var text = document.createTextNode(objArr[i].name+' '+objArr[i].count+' '+objArr[i].price);
            // h6 태그가 있으면(=기존 상품의 정보가 있으면) 만들지 않고, 없으면 만듦
            if( document.getElementById(name) ){    // 기존 상품을 담은 h6 이 있으면
                var h = document.getElementById(name);    // 기존 상품을 담은 h6 태그를
                sc.removeChild(h);                        // 삭제한다
            }
            var h = document.createElement('h6');    // 상품 정보를 담을 h6 태그를 새로 만든다
            h.setAttribute("id", name);    // h6 태그에 상품 이름으로 id부여 -> 다시 찾기 위함
 
            h.appendChild(text);    // 만든 태그에 상품 정보 텍스트 넣는다
        }
    }
    sc.appendChild(h);    // 출력할 부분에 태그 넣는다
    return;
} 
 
/* 지출액 계산 */
function func2(x){    // x: 선택된 button
    var btn = x.querySelector('span');    // span은 금액 부분을 담고있다
    var f2 = document.querySelector('#spend');    // 지출 총액을 출력할 부분
    productSum += Number(btn.innerHTML);    // 금액 부분만 빼냄
    f2.setAttribute('value', productSum);    // 지출 총액 출력
    
    var str = x.innerHTML;    // 상품 설명
    var name = str.substring(0, str.indexOf('<'));    // 상품 설명에서 이름만 추출
    var price = Number(btn.innerHTML);    // 금액 부분
    
    if(objArr.length==0){    // 상품을 담은 배열이 존재하지 않는다면
        objArr.push(new obj(name, 1, price));    // 새로 넣는다
        printScreen(name); return;    // 출력 함수 호출
    }
    else{                        // 상품을 담은 배열이 있다면
        for(var i in objArr){    // 배열에서
            if(objArr[i].name == name){    // 선택한 상품이 배열에 존재하는지 확인
                objArr[i].count += 1;    // 있으면 갯수와 가격만 올림
                objArr[i].price += price;
                printScreen(name); return;    // 출력 함수 호출
            }
        }        
        objArr.push(new obj(name, 1, price));    // 선택한 상품이 배열에 없다면 새로 넣음
        printScreen(name);    // 출력 함수 호출
    }
    
};

 
 
</script>
</head>
<br>
<div class="layout">
 

<div id="menu">
    <div>
        <button onclick="func2(this)">사이다<br></button>
        <p>500원</p>
    </div>
    <div>
        <button onclick="func2(this)">콜라<br></button>
        <p>1000원</p>
    </div>
    <div>
        <button onclick="func2(this)">비타민음료<br></button>
        <p>300원</p>
    </div>
</div>

</br>
</br>

<div id="money">
    <button onclick="func1(this)">100</button>
    <button onclick="func1(this)">500</button>
    <button onclick="func1(this)">1000</button>
</div>
    
<div id="screen"></div>
<br>
투입액<input id="calc" type="text" name="result" value="0원">
지출액<input id="spend" type="text" value="">
<button onclick="calc()">계산</button>
<br>
거스름<input id="change" type="text" value="">
</div>
</body>
</html>
