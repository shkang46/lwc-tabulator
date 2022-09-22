# Tabulator in LWC

http://tabulator.info/

![Screenshot 2022-09-22 at 15 32 57](https://user-images.githubusercontent.com/73949610/191674873-a72f1491-b168-4c25-8498-0f38251bec95.JPG)

## Issue

#### Rating 타입에서 svg가 표시되지 않는 문제
- svg에 대한 viewbox attribute를 만들 때, setAttribute('viewBox', ...)가 attribute name을 lower case로 변환하기 때문에 제대로 인식할 수 없음
```js
// 이 코드를
star.setAttribute("viewBox", "0 0 512 512");

// 이렇게 바꿔야함
const attrNodeViewBox = document.createAttributeNS(null, 'viewBox');
attrNodeViewBox.value = '0 0 512 512';
star.setAttributeNodeNS(attrNodeViewBox);

// 두 군데 있음
```

