---
title: 컴파일러 오류 C2970 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2970
dev_langs:
- C++
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0775f9d771b2c9497b3dc731e26c6a3b4e6ab30c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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