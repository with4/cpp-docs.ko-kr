---
title: 컴파일러 오류 C2695 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2695
dev_langs:
- C++
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67dc97688dddde37323f25b96bd8bbc596660e2f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231219"
---
# <a name="compiler-error-c2695"></a>컴파일러 오류 C2695
'function1': 재정의 가상 함수에서 'function2' 점만 다른 호출 규칙  
  
 파생된 클래스에서 함수의 서명이 기본 클래스의 함수를 재정의 하 고 호출 규칙을 변경할 수 없습니다.  
  
 다음 샘플에서는 C2695 오류가 생성 됩니다.  
  
```  
// C2695.cpp  
class C {  
   virtual void __fastcall func();  
};  
  
class D : public C {  
   virtual void __clrcall func();   // C2695  
};  
```