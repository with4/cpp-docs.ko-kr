---
title: "C + +의 선언 위치 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64c1fa1d6d8feb4b869957101bb4b37f125d0f8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="point-of-declaration-in-c"></a>C++의 선언 지점
선언자 바로 뒤, 이니셜라이저 앞(선택 사항)에서 이름이 선언된다고 간주합니다. (선언 자에 대 한 자세한 내용은 참조 하십시오. [선언 및 정의](declarations-and-definitions-cpp.md).)  
  
 다음 예제를 고려해 보세요.  
  
```  
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 선언 시점 되었으면 *후* 를 초기화 하는 다음의 로컬 `dVar` 7.0, 전역 변수의 값으로 초기화는 `dVar`합니다. 그러나 그런 경우는 아니므로 `dVar`이 정의되지 않은 값으로 초기화됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [범위](../cpp/scope-visual-cpp.md)