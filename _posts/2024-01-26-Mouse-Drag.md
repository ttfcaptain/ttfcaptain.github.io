---
title: Mouse Drag
author: min
date: 2024-01-26 15:12:00 +0900
categories: [Unity]
tags: [mouse,drag]
pin: false
mermaid: true
published: true
image:
  path: https://imgur.com/uaWj07U.jpg
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Move with mouse click.
---

# **Mouse Drag**

> ## **SUMMARY**  
마우스 클릭으로 오브젝트 이동하기.

`　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　`
## SETTING
#### Object 생성
- 드래그할 오브젝트 생성.

#### Collider 적용
- 생성한 오브젝트에 **Collider** component적용.

#### Script 작성
- 'MouseDrag' script 파일 생성/추가.

`　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　`
## EXPLAIN
마우스 드래그할 오브젝트를 생성한 후 **Collider** COMPONENT 를 추가함.  
(**OnMouseDown**, **OnMouseDrag** 메서드는 **Collider**에서 반응)

`　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　　`
## CODE
```c#
Vector3 _clickDistance;

void OnMouseDown()
{
  _clickDistance = TransMousPos - transform.position;
}

void OnMouseDrag()
{
  transform.position = TransMousPos - _clickDistance;
}

Vector3 TransMousPos
{
  get
    {
      return Camera.main.ScreenToWorldPoint(Input.mousePosition);
    }
}
```
