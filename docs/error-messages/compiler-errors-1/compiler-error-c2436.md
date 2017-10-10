---
title: "컴파일러 오류 C2436 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2436
dev_langs:
- C++
helpviewer_keywords:
- C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ca7f9a160675009e1462b1e7c5c1b110180e10c5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2436"></a>컴파일러 오류 C2436
'identifier': 멤버 함수 또는 생성자 이니셜라이저 목록에서 중첩된 클래스  
  
 멤버 함수 또는 생성자 이니셜라이저 목록에는 지역 클래스를 초기화할 수 없습니다.  
  
 다음 샘플에서는 C2436 오류가 생성 됩니다.  
  
```  
// C2436.cpp  
struct S{  
   int f();  
   struct Inner{  
      int i;  
   };  
   S():f(10), Inner(0){}   // C2436  
};  
```
