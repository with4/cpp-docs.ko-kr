---
title: "C++의 선언 지점 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "선언 시점"
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++의 선언 지점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

선언자 바로 뒤, 이니셜라이저 앞\(선택 사항\)에서 이름이 선언된다고 간주합니다.  선언자에 대한 자세한 내용은 [선언자](http://msdn.microsoft.com/ko-kr/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838)를 참조하세요.  
  
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
  
 선언 시점이 초기화 후일 경우 로컬 `dVar`이 전역 변수 `dVar`의 값인 7.0으로 초기화됩니다.  그러나 그런 경우는 아니므로 `dVar`이 정의되지 않은 값으로 초기화됩니다.  
  
## 참고 항목  
 [범위](../cpp/scope-visual-cpp.md)