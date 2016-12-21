---
title: "컴파일러 경고 (수준 2) C4150 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4150"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4150"
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4150
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

불완전한 형식 'type'에 대한 포인터를 삭제했습니다. 소멸자가 호출되지 않습니다.  
  
 **delete** 연산자가 호출되어, 선언되었지만 정의되지 않은 형식을 삭제했으므로 컴파일러가 소멸자를 찾을 수 없습니다.  
  
 다음 샘플에서는 C4150 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4150.cpp  
// compile with: /W2  
class  IncClass;  
  
void NoDestruct( IncClass* pIncClass )  
{  
   delete pIncClass;  
} // C4150, define class to resolve  
  
int main()  
{  
}  
```