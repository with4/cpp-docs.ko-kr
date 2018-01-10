---
title: "컴파일러 오류 C2460 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2460
dev_langs: C++
helpviewer_keywords: C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97ab5f3a2635bf25c01c2e54ba27c49447f1514a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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