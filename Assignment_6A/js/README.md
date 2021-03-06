# cart.js

cart.js는 장바구니를 조작하는 API를 담고 있는 전역변수 `cart`를 선언하는 스크립트입니다.
전역변수 `cart`는 다음과 같은 프로퍼티를 가지고 있습니다.

- `list`: 장바구니의 목록을 객체로 담아둔 배열. 후술할 `cart.read()` 메소드로 접근할 것을 권장합니다.

전역변수 `cart`는 다음과 같은 메소드를 가지고 있습니다.

- `write()`: `cart.list`의 변경된 사항을 `localStorage`에 저장합니다.
  `cart.list`의 직접적인 수정 후 이 메소드의 호출로 저장을 하는 것보다, 후술할 다른 메소드로 조작하는 것을 추천합니다.
- `read()`: `localStorage`에 저장되어 있는 장바구니 목록을 `cart.list`에 담고 리턴합니다.
- `add(item)`: 장바구니 목록에 물건을 추가합니다.
  같은 색상과 사이즈의 물건이 이미 존재할 경우, 해당 물건의 수량을 1개만큼 늘려줍니다.
- `remove(index)`: 장바구니 목록의 `index`번째 요소를 삭제합니다.
- `increase(index, count = 1)`: 장바구니 목록의 `index`번째 요소의 물건의 수량을 `count` 만큼 늘려줍니다.
- `decrease(index, count = 1)`: 장바구니 목록의 `index`번째 요소의 물건의 수량을 `count` 만큼 줄여줍니다.
  만약 변경된 수량이 0보다 작거나 같아질 경우, 해당 요소를 삭제할 것인지 질의 후에 수락하면 삭제, 거절하면 수량을 1로 설정합니다.
- `clear()`: 장바구니 목록을 초기화합니다.
