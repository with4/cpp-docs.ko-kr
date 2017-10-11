---
title: "컴파일러 오류 C3200 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3200
dev_langs:
- C++
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e4e1df5fb5c3da260ec5eba75d25e74207fbf8e2
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3200"></a>컴파일러 오류 C3200
'template': 템플릿 매개 변수 'parameter'에 대 한 잘못 된 템플릿 인수. 클래스 템플릿이 필요  
  
 클래스 템플릿을에 잘못 된 인수를 전달 합니다. 클래스 템플릿에서 매개 변수로 템플릿이 필요합니다. 다음 예제에서는 호출 `Y<int, int> aY` C3200를 생성 합니다. 첫 번째 매개 변수 수와 같은 해야 `Y<X, int> aY`합니다.  
  
```  
// C3200.cpp  
template<typename T>  
class X  
{  
};  
  
template<template<typename U> class T1, typename T2>  
class Y  
{  
};  
  
int main()  
{  
   Y<int, int> y;   // C3200  
}  
```
