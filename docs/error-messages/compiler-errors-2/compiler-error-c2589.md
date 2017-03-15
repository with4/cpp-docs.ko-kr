---
title: "컴파일러 오류 C2589 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2589"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2589"
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2589
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : '::' 오른쪽에 잘못된 토큰이 있습니다.  
  
 클래스, 구조체 또는 공용 구조체 이름이 범위 결정 연산자\(이중 콜론\)의 왼쪽에 표시되는 경우 오른쪽의 토큰은 클래스, 구조체 또는 공용 구조체 멤버여야 합니다.  그렇지 않은 경우에는 오른쪽에 전역 식별자가 표시될 수 있습니다.  
  
 범위 결정 연산자는 오버로드할 수 없습니다.  
  
 다음 샘플에서는 C2589 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2589.cpp  
void Test(){}  
class A {};  
void operator :: ();   // C2589  
  
int main() {  
   ::Test();  
}  
```