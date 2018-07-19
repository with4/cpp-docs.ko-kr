---
title: 컴파일러 오류 C2460 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4220be654f93ecd79d196efc14657ca7346411f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197782"
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