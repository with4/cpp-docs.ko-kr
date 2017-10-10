---
title: "컴파일러 오류 C2555 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 64f66bf80e8e4b6ba7477691cb9675cec347807d
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2555"></a>컴파일러 오류 C2555
'class1::function1': 재정의 가상 함수의 반환 형식 다르며 'class2::function2' 공변 (covariant)지 않습니다  
  
 가상 함수 및 파생된 재정의 함수는 있지만 다른 반환 형식은 동일한 매개 변수 목록이 있습니다. 파생된 클래스에서 재정의 함수 반환 형식에 의해서만 기본 클래스에는 가상 함수에서 다를 수 없습니다.  
  
 이 오류를 해결 하려면 가상 함수를 호출한 후 반환 값을 캐스팅 합니다.  
  
 이 오류는 /clr을 사용 하 여 컴파일할 경우에 발생할 수 있습니다.   예를 들어, Visual c + + 다음 C# 선언에 해당:  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 is  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 C2555에 자세한 내용은 기술 자료 문서 Q240862 참조 합니다.  
  
 다음 샘플에서는 C2555 오류가 생성 됩니다.  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```
