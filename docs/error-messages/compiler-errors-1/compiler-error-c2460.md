---
title: "컴파일러 오류 C2460 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 00e4015a0dae5054973ba72bb0e4f89c7443ae03
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2460"></a>컴파일러 오류 C2460
'identifier1': 사용 하 여 'identifier2'를 정의 중인  
  
 클래스 또는 구조체 (`identifier2`) 자체의 멤버로 선언 (`identifier1`). 클래스 및 구조체의 재귀 정의 허용 되지 않습니다.  
  
 다음 샘플에서는 C2460 오류가 생성 됩니다.  
  
```  
// C2460.cpp  
class C {  
   C aC;    // C2460  
};  
```  
  
 대신 클래스에 대 한 포인터 참조를 사용 합니다.  
  
```  
// C2460.cpp  
class C {  
   C * aC;    // OK  
};  
```
