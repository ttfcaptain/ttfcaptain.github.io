---
title: Mouse Drag
author: Min
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

# Mouse Drag

## **Summary**
> 마우스 클릭으로 오브젝트 이동하기.
## **Explain**
### Object 생성
### Collider 적용
### `MouseDrag` script 작성
## **Setting**
## **Code**
```c#s
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
	get {
			return Camera.main.ScreenToWorldPoint(Input.mousePosition);
		}
}
```
