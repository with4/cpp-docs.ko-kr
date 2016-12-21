---
title: "컴파일러 경고 (수준 2) C4948 | Microsoft Docs"
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
  - "C4948"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4948"
ms.assetid: d006cb17-754a-4c70-ba7f-c3200e2cd8fa
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4948
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'accessor'의 반환 형식이 해당 setter의 마지막 매개 변수 형식과 일치하지 않습니다.  
  
 컴파일러에서 인덱싱된 속성에 대해 가져오는 데이터 형식과 설정되는 데이터 형식이 서로 일치하지 않음을 발견했습니다.  
  
 C4948은 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C4948 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4948.cpp  
// compile with: /clr:oldSyntax /LD /W2  
  
__gc class MyClass  
{  
   int prop __nogc [2];  
   public:  
  
      __property int get_P(int i)  
      // try the following line instead  
      // __property char get_P(int i)  
      {  
         return prop[i];  
      }  
  
      __property void set_P(int i, char c)  
      {  
         prop[i] = c;  
      }  
};   // C4948  
```