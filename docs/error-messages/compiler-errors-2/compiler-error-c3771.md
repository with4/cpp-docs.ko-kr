---
title: "컴파일러 오류 C3771 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3771"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3771"
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C3771
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"identifier": 가장 가까운 네임스페이스 범위에서 friend 선언을 찾을 수 없습니다.  
  
 현재 네임스페이스 내에서 지정된 템플릿 *identifier*에 대한 클래스 템플릿 선언을 찾을 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   템플릿 식별자에 대한 클래스 템플릿 선언이 현재 네임스페이스에 정의되어 있는지 또는 템플릿 식별자가 정규화된 이름인지 확인합니다.  
  
## 예제  
 다음 코드 예제에서는 `NA` 네임스페이스의 클래스 템플릿 및 함수를 선언하지만 `NB` 네임스페이스의 friend 함수 템플릿을 선언하려고 합니다.  
  
```  
// C3771.cpp // compile with: /c namespace NA { template<class T> class A { void aFunction(T t) {}; }; } // using namespace NA; namespace NB { class X { template<class T> friend void A<T>::aFunction(T); // C3771 // try the following line instead //      template<class T> friend void NA::A<T>::aFunction(T); // or try "using namespace NA;" instead. }; }  
```  
  
## 참고 항목  
 [템플릿 지정](../Topic/Template%20Specifications.md)