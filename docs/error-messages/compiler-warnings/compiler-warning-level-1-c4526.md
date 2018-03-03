---
title: "컴파일러 경고 (수준 1) C4526 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4526
dev_langs:
- C++
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a74d7d2e2c745a4c8e29736c1e3a7fc38892d5f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4526"></a>컴파일러 경고(수준 1) C4526
'function': 정적 멤버 함수는 가상 함수를 재정의할 수 없습니다 ' 무시 되는 가상 function'override 가상 함수는 숨겨집니다.  
  
 정적 멤버 함수는 가상 및 정적 멤버 함수를 사용 하면 가상 함수를 재정의 하는 조건을 충족 합니다.  
  
 다음 코드에서는 C4526 오류가 생성 됩니다.  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 다음은 가능한 해결 방법입니다.  
  
-   함수를 기본 클래스 가상 함수를 재정의 하려고, static 지정자를 제거 합니다.  
  
-   함수는 정적 멤버 함수 원래, 이름을 기본 클래스 가상 함수와 함께 충돌 하지 않도록 합니다.