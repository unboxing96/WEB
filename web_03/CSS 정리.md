# CSS 정리

## Box Model

> CSS로 표시하는 모든 것은 박스다.

### Extrinsic sizing vs Intrinsic sizing

- Extrinsic: 콘텐츠에 영향을 받지 않는 고정적인 박스
- Intrinsic: 콘텐츠의 크기에 따라 변하는 가변적인 박스

### 박스 모델의 영역

- Margin Box: border box 바깥의 나머지 공간
- Border Box: 시각적으로 확인할 수 있는 마지막 공간
- Padding Box: 콘텐츠를 둘러싸고 있는 공간
- Content Box: 콘텐츠 공간

### box-sizing

CSS의 기본적인 규칙은 Content Box를 기준으로 크기를 설정한다.
그러나 시각적으로 확인 가능한 Border Box를 기준으로 하는 것이, 보다 예측 가능
따라서 다음의 코드를 일반적으로 적용한다.
```css
* {
  /* border-box를 기준으로 배치 */
  box-sizing: border-box;
}
```

## Selector

> elements에 스타일을 적용하기 위해서는 '선택'을 해야한다.

### Selector의 구성
![CSS 구조](css_model.svg)

### Selector의 종류


- 범용 선택자: 모든 요소를 선택
```css
* {
  color: hotpink;
}
```

- tag 선택자
```css
p {
  color: hotpink;
}
```


- class 선택자
```css
.container {
  color: hotpink;
}
```


- id 선택자: 모든 요소를 선택
```css
#name {
  color: hotpink;
}
```


- attribute 선택자
```css
[data-type='primary'] {
  color: hotpink;
}
```


## The Cascade

> CSS은 순차적인 규칙에 의해 적용된다.

### Cascade Algorithm

1. 위치 및 표시 순서: CSS 파일에 나중에 작성되었을수록 우선순위.
2. 특이성: 가장 일치하는 CSS 선택자를 결정하는 알고리즘
3. 오리진: CSS가 나타나는 순서와 출처, 브라우저 스타일인지, 브라우저 확장 프로그램의 CSS인지, 작성한 CSS인지 여부
4. 중요도: 선택자 중요도에 따라 배열 (ex. !important 규칙은 최우선 순위)
