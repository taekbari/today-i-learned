# DAY04
## Review  
레이아웃 만들 때 가로정렬하는 방법.
1.  `flex box`
2.  `inline-block`
3.  `float`

`inline-block`을 사용해서 가로정렬을 할 때 발생하는 문제 중 하나인 공백 해결하는 추가적인 방법.  
> 부모 속성에 `font-size: 0`으로 설정하고  
> 자식 요소들에는 `font-size` 재설정하는 방법.
> 공백역시 문자이기 때문에 크기가 0으로 변경되어서 공백이 사라지게 됨.  
> 참조 사이트 : [1분코딩](https://www.facebook.com/1mincoding/?fref=ts) "float 대신 inline-block으로 컬럼 레이아웃 만들기."

---

## Main Menu 만들기.

### 그레디언트 (gradient) 적용하기.
`linear-gradient()` 함수는 선형 컬러 그레디언트를 나타나는 image를 생성한다.  
`CSS gradient`는 `CSS color`가 아닌 크기가 없는 이미지이다. 즉, 미리 정해진 또는 우선시되는 크기나 비율이 없다. 실제적인 크기는 그레디언트가 적용되는 요소에 맞추어진다.  

#### `linear-gradient` 설정.  
1. 방향 또는 각도.  
 * 기본값은 위에서 아래.
 * 도착 지점만 **to** 를 사용하여 지정.  
 * 또는 `45deg`와 같이 원하는 각도를 선택할 수도 있다.  
2. 색상 선택.  
 * 시작과 종료 색상은 필수적으로 선택해야 한다.  
 * 중간에 원하는 색상을 추가적으로 설정할 수 있다.  
3. 색상점 위치 지정하기.  
 * 그레디언트 축에서 색상점의 위치를 지정할 수 있다.  
 * `%` 또는 길이값 (`px`)

```css
.background{
  background-image: linear-gradient(to bottom, #f2a430 0%,#e8932c 30%,#e8932c 70%,#f2a430 100%);
}

.background{
  background-image: linear-gradient(45deg, #00f 0%, #444dcb 50%, #fff 100%);
}
```

### 배경 이미지 설정.
배경을 이미지로 설정할 경우 사용되는 속성값.
```css
.background{
  background-image: url(images/validation_icon.png);
  background-repeat: no-repeat;
  background-position: 100px 5px;
  background-size: 30px 30px;
}
```
여기서 주의해야할 사항은 `background-position`이다.  
`background-position` 값을 `px`로 설정할 경우, 설정한 픽셀의 위치에 이미지의 시작지점이 위치하게 된다. 하지만 `%`로 설정할 경우, 부모와 선택한 이미지 각각 설정한 값의 위치를 찾게 되고, 부모의 위치 값 위에 선택한 이미지의 위치 값을  겹쳐놓게 된다.

배경 이미지를 설정해 줄 경우, 네트워크 등이 문제로 인해서 배경 이미지가 로딩되지 못했을 때를 대비해서 `background-color` 설정해주는 것이 좋다.  

---
### 참고 문서  
* [linear-gradient - CSS | MDN - Mozilla Developer Network](https://developer.mozilla.org/ko/docs/Web/CSS/linear-gradient)  
* [[css3] gradient (linear-gradient) 사용법 :: 지구별 안내서](http://aboooks.tistory.com/362)
