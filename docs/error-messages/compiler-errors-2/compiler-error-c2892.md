---
title: "컴파일러 오류 C2892 | Microsoft Docs"
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
  - "C2892"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2892"
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2892
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지역 클래스는 멤버 템플릿을 가질 수 없습니다.  
  
 함수에 정의되지 않은 클래스에는 템플릿 멤버 함수를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2892 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2892.cpp  
int main() {  
   struct local {  
      template<class T>   // C2892  
      void f() {}  
   };  
}  
```