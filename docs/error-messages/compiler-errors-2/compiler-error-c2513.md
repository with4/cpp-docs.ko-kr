---
title: "컴파일러 오류 C2513 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2513
dev_langs:
- C++
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 62c55a1a6eb093d4ef6921f6d0f8b7c50683ff8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2513"></a>컴파일러 오류 C2513
'type': '=' 앞에 선언 된 변수가 없음을  
  
 형식 지정자와 변수 식별자 선언에 표시 됩니다.  
  
 다음 샘플에서는 C2513 오류가 생성 됩니다.  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 이 오류는 Visual Studio.NET 2003 컴파일러 규칙 작업의 결과로 생성 될 수 없습니다: 더 이상 사용할 수 없습니다. 형식 정의를 초기화 합니다. 형식 정의 초기화 하는 표준에서 허용 되지 않는 하 고 이제 컴파일러 오류를 생성 합니다.  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 삭제 하는 대신 것 `typedef` 집합체 이니셜라이저 목록에 있지만이 사용 하 여 변수를 정의할 수 있으므로 권장 되지 않습니다 유형으로 동일한 이름을 가진 변수를 만듭니다 하 고 숨길 형식 이름입니다.