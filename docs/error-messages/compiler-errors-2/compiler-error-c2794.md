---
title: 컴파일러 오류 C2794 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2794
dev_langs:
- C++
helpviewer_keywords:
- C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2cee2ce072f3dfe106434443ba28047cf7b58284
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2794"></a>컴파일러 오류 C2794
'function': 클래스는 직접 또는 간접 기본 클래스의 'class'의 구성원이 아닙니다  
  
 사용 하려는 [super](../../cpp/super.md) 존재 하지 않는 멤버 함수를 호출 합니다.  
  
 다음 샘플에서는 C2794  
  
```  
// C2794.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::f();  // C2794  
   }  
};  
```