---
title: "컴파일러 오류 C2970 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2970
dev_langs:
- C++
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fc125b400a718805af2ee0829100c056fffa29a3
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2970"></a>컴파일러 오류 C2970
'class': 템플릿 매개 변수 'param': 'arg': 내부 링크가 있는 개체를 포함 하는 식을 비형식 인수로 사용할 수 없습니다  
  
 템플릿 인수로 이름 또는 정적 변수의 주소를 사용할 수 없습니다. 템플릿 클래스 컴파일 타임에 계산 될 수 있는 const 값이 필요 합니다.  
  
 다음 샘플에서는 C2970 오류가 생성 됩니다.  
  
```  
// C2970.cpp  
// compile with: /c  
static int si;  
// could declare nonstatic to resolve all errors  
// int si;  
  
template <int i>   
class X {};  
  
template <int *pi>   
class Y {};  
  
X<si> anX;   // C2970 cannot use static variable in templates  
  
// this would also work  
const int i = 10;  
X<i> anX2;  
```
