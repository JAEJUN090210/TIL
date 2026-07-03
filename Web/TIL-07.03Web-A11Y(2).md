# TIL - 07.03 / Web - A11Y (2)

## Summary

- **웹 접근성(A11Y)은 시맨틱 HTML을 우선 사용하고, 필요한 경우 ARIA를 활용하여 보조기기가 UI를 올바르게 이해하도록 만드는 것이 핵심이다.**

------

## Body

- **Semantic HTML**
  - 요소의 의미를 나타내는 HTML 태그 사용
  - 스크린 리더와 검색 엔진이 구조를 쉽게 이해 가능
  - 대표 태그
    - `<header>`
    - `<nav>`
    - `<main>`
    - `<section>`
    - `<article>`
    - `<aside>`
    - `<footer>`
    - `<button>`
- **ARIA (Accessible Rich Internet Applications)**
  - HTML만으로 표현하기 어려운 접근성 정보를 제공
  - 동적인 UI에서 주로 사용
  - 대표 속성
    - `aria-label`
    - `aria-labelledby`
    - `aria-describedby`
    - `aria-hidden`
    - `aria-expanded`
    - `aria-live`
- **ARIA 사용 원칙**
  - HTML 태그로 해결 가능한 경우 ARIA를 사용하지 않는다.
  - 필요한 경우에만 최소한으로 사용한다.
  - 잘못된 ARIA 속성은 접근성을 오히려 저하시킬 수 있다.
- **시맨틱 HTML 우선 원칙**
  - `<button>` 대신 `<div>`를 클릭 버튼으로 사용하지 않는다.
  - `<a>`는 이동, `<button>`은 동작 수행에 사용한다.
  - 기본 HTML 요소가 제공하는 접근성을 최대한 활용한다.

------

## (+)

- 스크린 리더 지원 향상
- 키보드 접근성 개선
- SEO 향상
- 유지보수성과 코드 가독성 향상

------

## (-)

- ARIA를 잘못 사용하면 접근성이 오히려 나빠질 수 있음
- 시맨틱 태그를 무시하면 보조기기에서 올바르게 해석되지 않음
- 커스텀 UI 개발 시 추가적인 접근성 고려가 필요