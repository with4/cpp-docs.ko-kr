---
title: 컴파일러 오류 C2555 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d2d1a710177e2c8c72b0afeff662dddf1c22ef5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230588"
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