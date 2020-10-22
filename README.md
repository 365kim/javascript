# 하우투 in JS

### :rocket: 알파벳순, 오름차순 정렬하기
- `arr.sort();`

  ```js
  let strArr = ["b", "a", "c"];
  console.log(strArr.sort());
  // [a, b, c]
  ```
- `arr.sort((a, b) => a - b);`

  ```js
  let numArr = [19, 9, 29];
  console.log(numArr.sort());
  // [19, 29, 9]
  console.log(numArr.sort((a, b)=> a - b));
  // [9, 19, 29]
  ```
<br>

### :rocket: 배열의 최댓값 구하기
- `Math.max(...numArr);`

  ```js
  let numArr = [3, 6, 5];
  console.log(Math.max(numArr));
  // NaN
  console.log(Math.max(...numArr));
  // 6
  ```
<br>

### :rocket: 배열의 n번째로 큰 수 구하기
- `numArr.sort((a, b) => b - a)[n];`

  ```js
  let numArr = [1, 2, 3, 4, 5];
  console.log(numArr.sort((a, b) => b - a)[1]);
  // 4
  ```
<br>

### :rocket: 숫자형 자릿수 구하기
- `num.toString().length;`

  ```js
  let num = 1004;
  console.log(num.toString());
  // 1004
  console.log(num.toString().length);
  // 4
  ```
<br>

### :rocket: 진수변환
- 문자열 => 숫자 `parseInt(str, base);`

  ```js
  console.log(parseInt("1111", 2));
  // 15
  console.log(parseInt("f", 16));
  // 15
  console.log(parseInt("1111", 10));
  // 1111
  ```
- 숫자 => 문자열 `num.toString(base);`

  ```js
  console.log((15).toString(2)); // 숫자 => 문자열
  // "1111"
  console.log(+(15).toString(2)); // 숫자 => 숫자
  // 1111
  console.log((15).toString(16));
  // "f"
  console.log((+"15").toString(16)); // 문자열 => 문자열
  // "f"
  ```
<br>

### :rocket: a의 b승 구하기
- `Math.pow(base, exponent);`

  ```js
  console.log(Math.pow(4, 2));
  // 16
  console.log(Math.pow("4", "2"));
  // 16
  console.log(Math.pow(4, 0.5));
  // 2
  ```
<br>

### :rocket: 문자열 길이 채우기
- `str.padStart(n, c);`

  ```js
  console.log("f".padStart(3));
  // "  f"
  console.log("f".padStart(3, "0"));
  // "00f"
  console.log("f".padStart(3, "abcde"));
  // "abf"
  console.log("f".padEnd(3, "0"));
  // "f00"
  ```
<br>

### :rocket: 변수 여러개 한 번에 초기화하기
- `let [a, b] = [1, 2]`

  ```js
  let [a, b, c, d] = [3, 6, 5, "kim"];
  console.log(a); // 3
  console.log(b); // 6
  console.log(c); // 5
  console.log(d); // kim
  ```
- :point_right: `[a,b] === [1,2]` 와 같은 비교는 할 수 없음
<br>

### :rocket: 배열의 요소 자료형 바꾸기
- 숫자요소 -> 문자요소 `arrNum.map((v) => v.toString());`

  ```js
  let arrNum = [3, 6, 5];
  console.log(arrNum.map((v) => v.toString()));
  // [ '3', '6', '5' ]
  ```
- 문자요소 -> 숫자요소 `strNum.map((v) => +v);` 

  ```js
  let strNum = ["3", "6", "5"];
  console.log(strNum.map((v) => +v));
  // [ 3, 6, 5 ]
  ```
<br>

### :rocket: 객체를 배열로 바꾸기
- `Object.entries(obj);`

  ```js
  const obj = {
    1: "breakfast",
    2: "lunch",
    3: "dinner",
  };

  console.log(Object.keys(obj));
  // [ '1', '2', '3' ]
  console.log(Object.values(obj));
  // [ 'breakfast', 'lunch', 'dinner' ]
  console.log(Object.entries(obj));
  // [ [ '1', 'breakfast' ], [ '2', 'lunch' ], [ '3', 'dinner' ] ]
  ```
<br>

### :rocket: n개의 빈 배열을 가진 배열 선언하기
- `new Array(n).fill().map(() => []);`

  ```js
  console.log(new Array(5).fill().map(() => []));
  /// [ [], [], [], [], [] ]
  ```
<br>

### :rocket: 서로 동일한 배열인지 확인하기
- `길이 동일 && 값 동일`

  ```js
  let arr1 = [3, 6, 5, "kim"];
  let arr2 = [3, 6, 5, "kim"];
  console.log(arr1.length === arr2.length && arr1.every((v, i) => v === arr2[i]));
  // true
  ```
<br>

### :rocket: 배열 순서 뒤집기
- `array.reverse();`

  ```js
  console.log([1, 2, 3].reverse());
  // [ 3, 2, 1 ]
  ```
<br>

### :rocket: 문자열 순서 뒤집기
- `[...str].reverse().join("");`

  ```js
  console.log([..."365kim"]);
  // [ '3', '6', '5', 'k', 'i', 'm' ]

  console.log([..."365kim"].reverse());
  // ['m', 'i', 'k', '5', '6', '3']

  console.log([..."365kim"].reverse().join());
  // m,i,k,5,6,3

  console.log([..."365kim"].reverse().join(""));
  // mik563
  ```
- `str.split("").reverse().join("");`

  ```js
  console.log("365kim".split());
  // [ '365kim' ]
  
  console.log("365kim".split(""));
  // [ '3', '6', '5', 'k', 'i', 'm' ]

  console.log("365kim".split("").reverse());
  // ['m', 'i', 'k', '5', '6', '3']

  console.log("365kim".split("").reverse().join());
  // m,i,k,5,6,3

  console.log("365kim".split("").reverse().join(""));
  // mik563
  ```
<br>

### :rocket: 행열 전환하기
  ```js
  let arr = [
    ["1", "365kim", "Seoul"],
    ["2", "247lee", "Incheon"],
  ];
  let [rowLen, colLen] = [arr.length, arr[0].length];
  let newArr = new Array(colLen).fill().map(() => []);
  for (let i = 0; i < rowLen; i++) {
    for (let j = 0; j < colLen; j++) {
      newArr[j].push(arr[i][j]);
    }
  }
  console.log(newArr);
  /*
  [
    ["1", "2"],
    ["365kim", "247lee"],
    ["Seoul", "Incheon"],
  ];
  */
  ```
<br>

### :rocket: 숫자형 변수, 배열로 필요한 숫자 배열 재구성하기
- `[].concat(a, str.slice(n, m));`

  ```js
  let num = 3;
  let str = [4, 6, 5, 5];
  console.log([].concat(num));
  // [ 3 ]
  console.log([].concat(num, str.slice(1, 3)));
  // [ 3, 6, 5 ]

  ```
<br>

### :rocket: 연속된 순열 배열 만들기
- `new Array(n).fill().map((v, i) => i);`

  ```js
  console.log(new Array(5).fill().map((v, i) => i + 1));
  /// [ 1, 2, 3, 4, 5 ]
  ```
<br>

### :rocket: 연속된 문자열 만들기
- `new Array(n).fill().map((v, i) => String.fromCharCode(ascii));`

  ```js
  console.log(new Array(5).fill().map((v, i) => String.fromCharCode(65 + i)));
  // [ 'A', 'B', 'C', 'D', 'E' ]
  console.log(new Array(5).fill().map((v, i) => String.fromCharCode(97 + i)));
  // [ 'a', 'b', 'c', 'd', 'e' ]
  ```
<br>

### :rocket: 대소문자 변환
- `str.toUpperCase()` `str.toLowerCase()`

  ```js
  console.log("365kim".toUpperCase());
  // 365KIM
  console.log("365KIM".toLowerCase());
  // 365kim
  ```
<br>

### :rocket: 숫자만, 대문자만, 소문자만 골라내기
- `n.charCodeAt(0)`

  ```js
  let n = "3";
  console.log(n.charCodeAt(0) >= 48 && n.charCodeAt(0) <= 57);
  // true
  ```
- `a === a.toUpperCase()`

  ```js
  let a = "K";
  console.log(a === a.toUpperCase());
  // true
  console.log(a.charCodeAt(0) >= 65 && a.charCodeAt(0) <= 90);
  // true
  ```
- `a === a.toLowerCase()`

  ```js
  let b = "i";
  console.log(b === b.toLowerCase());
  // true
  console.log(b.charCodeAt(0) >= 97 && b.charCodeAt(0) <= 122);
  // true
<br>

### :rocket: 문자열에서 a <=> b 교체하기
- `str.replace(/a/gi, "?").replace(/b)/gi, "a").replace(/\?/gi, "b");`

  ```js
  console.log(")365kim(");
  // )365kim(
  console.log(")365kim(".replace(/\(/gi, "a")); // g: global, i: case-insensitive
  // )365kima
  console.log(")365kim(".replace(/\(/gi, "a").replace(/\)/gi, "("));
  // (365kima
  console.log(")365kim(".replace(/\(/gi, "a").replace(/\)/gi, "(").replace(/a/gi, ")"));
  // (365kim)
  ```
<br>

### :rocket: 배열에서 중복되지 않은 요소 개수 세기
- `new Set(array.size);`

  ```js
  console.log(new Set([1, 1, 2]));
  // Set { 1, 2 }
  console.log(new Set([1, 1, 2]).size);
  // 2
  console.log(new Set([1, 1, 2]).add(3));
  // Set { 1, 2, 3 }
  console.log(new Set([1, 1, 2]).add(3).size);
  // 3
  ```
<br>

### :rocket: 배열에서 키워드 빈도 구하기
- `str.match(/키워드/g).length;`

  ```js
    let arr = ["반대", "기권", "찬성", "찬성"];
    console.log(arr.join());
    // 반대,기권,찬성,찬성
    console.log(arr.join().match(/찬성/g));
    // [ '찬성', '찬성' ]
    console.log(arr.join().match(/찬성/g).length);
    // 2
<br>

### :rocket: 배열에서 빈도에 따라 객체만들고 최대값 찾기
- `new Set(array.size);`

  ```js
  let arr = ["반대", "기권", "찬성", "찬성", "무효", "반대", "찬성", "찬성", "찬성", "반대"];
  let board = {};
  arr.forEach((v) => (board[v] = board[v] === undefined ? 1 : ++board[v]));
  console.log(board);
  // { '찬성': 5, '무효': 1, '반대': 3, '기권': 1 }
  let major = Object.keys(board).reduce((acc, cur) =>
    board[acc] >= board[cur] ? acc : cur
  );
  console.log(major, board[major]);
  //찬성 5
  ```
<br>

### :rocket: 1차원 배열에서 특정 요소만 삭제하기
- `array.splice(array.indexOf(target), 1)`

  ```js
  let array = ["365", "js", "kim"];
  let i = array.indexOf("js");
  console.log(i);
  // 1
  console.log(array.splice(i, 1));
  // [ 'js' ]
  console.log(array);
  // [ '365', 'kim' ]
  ```
<br>

### :rocket: 2차원 배열에서 특정 요소만 삭제하기
- `array.splice(array.findIndex(list) => f(list))`

  ```js
  let array = [  [3, 6, 5],  ["j", "s"],  ["k", "i", "m"], ];
  let i = array.findIndex((list) => list[0] === "j" && list[1] === "s");
  console.log(i);
  // 1
  console.log(array.splice(i, 1));
  // [ [ 'j', 's' ] ]
  console.log(array);
  // [ [ 3, 6, 5 ], [ 'k', 'i', 'm' ] ]
  ```
- :point_right: `indexOf(["j", "s"])`로는 찾을 수 없음.
<br>

### :rocket: 깊은 복사
- `clone = JSON.parse(JSON.stringify(original));`
<br>

### :rocket: 콤마찍기
- 내장함수 `n.toLocaleString()`

  ```js
  console.log((123456789).toLocaleString());
  // 123,456,789
  ```
  
- 재귀함수 `putComma(s.slice(0, len-3)) + "," s.slice(len-3)`
  
  ```js
  const putComma = (s) => {
    if (s.length <= 3) {
      return s;
    } else {
      return putComma(s.slice(0, s.length - 3)) + "," + s.slice(s.length - 3);
    }
  };

  console.log(putComma("123456789"));
  // "123,456,789"
  ```

<br>


### :rocket: map으로 모든 부분집합 만들기
  ```js
  const powerset = (arr) =>
    arr.reduce(
      (subsets, value) => subsets.concat(subsets.map((set) => [...set, value])),
      [[]]
    );
  console.log(powerset([0, 1, 2]));
  /*
  [
    [],       [ 0 ],
    [ 1 ],    [ 0, 1 ],
    [ 2 ],    [ 0, 2 ],
    [ 1, 2 ], [ 0, 1, 2 ]
  ]
  */
  ```
<br>

### :rocket: 비트연산으로 모든 부분집합 만들기
  ```js
    const powerSet = (n) => {
      let comb = [];
      for (let i = 0; i < 1 << n; i++) { // 000...0부터 111...1까지
        let item = "";
        for (let j = 0; j < n; j++) {
          if ((i & (1 << j)) !== 0) { // And연산
            item += j;
          }
        }
        combination.push(item);
      }
    }
  ```
<br>

### :rocket: 대문자는 소문자로, 소문자는 대문자로
  ```js
  const swapUpperWithLower = (str) => {
    let res = "";
    for (let i = 0; i < str.length; i++) {
      res +=
        str[i].toUpperCase() === str[i]
          ? str[i].toLowerCase()
          : str[i].toUpperCase();
    }
    return res;
  };
  ```
<br>

### :rocket: 소수판별
  ```js
  const isPrime = (n) => {
    let sqrtN = Math.sqrt(n);
    for (let i = 2; i <= sqrtN; i++)
      if (n % i === 0) {
        return false;
      }
    return n > 1;
  };
  ```
<br>

### :rocket: 요일판별
  ```js
  const daysEn = ["SUN", "MON", "TUE", "WED", "THU", "FRI", "SAT"];
  const daysKo = ["일", "월", "화", "수", "목", "금", "토"];

  const dateToDay = (y, m, d) => {
    let theDate = new Date(`${y}-${m}-${d}`);
    console.log(theDate);
    // 2020-10-15T00:00:00.000Z

    let theDay = theDate.getDay();
    console.log(theDay);
    // 4 (0부터 시작)

    let theDayEn = daysEn[theDay];
    let theDayKo = daysKo[theDay];
    console.log(theDayEn);
    // THU
    console.log(theDayKo);
    // 목
  };

  dateToDay(2020, 10, 15);
  ```
<br>

### :rocket: 계산기
  ```js
  const operate = (a, b, op) => {
    switch (op) {
      case "+":
        return a + b;
      case "-":
        return a - b;
      case "*":
        return a * b;
      case "/":
        return a / b;
    }
  }
  ```
<br>

### :rocket: 버블정렬
  ```js
  const bubbleSort = (arr) => {
    let res = arr.slice(); // 깊은 복사

    for (let i = 0; i < res.length - 1; i++) {
      for (let j = 0; j < res.length - i; j++) {
        if (res[j] > res[j + 1]) {
          let temp = res[j];
          res[j] = res[j + 1];
          res[j + 1] = temp;
        }
      }
    }
    return res;
  };
  ```
  ```js
  const betterBubbleSort = (arr) => {
    let len = arr.length - 1;
    let swapped;
    do {
      swapped = false;

      for (let i = 0; i < len; i++) {
        if (arr[i] > arr[i + 1]) {
          let temp = arr[i];
          arr[i] = arr[i + 1];
          arr[i + 1] = temp;
          swapped = true;
        }
      }
    } while (swapped);
    return arr;
  };
  ```

### :rocket: 추가예정
- `prototype`

  ```js
  example
  ```
  
