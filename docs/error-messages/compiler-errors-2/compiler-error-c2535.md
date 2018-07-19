---
title: 컴파일러 오류 C2535 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2535
dev_langs:
- C++
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1dc791cd7782cc758aa51b0c61d87a79570c13c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229562"
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