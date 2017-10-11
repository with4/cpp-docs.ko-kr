---
title: "컴파일러 오류 C2535 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2535
dev_langs:
- C++
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0af3ce8f0f3fe89d8e2f120f1b9b16383f11ef6a
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2535"></a>컴파일러 오류 C2535
'identifier': 이미 정의 된 또는 선언 된 멤버 함수  
  
 여러 개 정의 또는 오버 로드 된 함수의 선언에 동일한 형식 매개 변수 목록을 사용 하 여이 오류를 일으킬 수 있습니다.  
  
 Dispose 함수로 인해 c 2535가 발생 하는 경우 참조 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) 자세한 정보에 대 한 합니다.  
  
 ATL 프로젝트를 컴파일하는 경우 기술 자료 문서를 Q241852를 참조 하십시오.  
  
 다음 샘플에서는 C2535 오류가 생성 됩니다.  
  
```  
// C2535.cpp  
// compile with: /c  
class C {  
public:  
   void func();   // forward declaration  
   void func() {}   // C2535  
};  
```
