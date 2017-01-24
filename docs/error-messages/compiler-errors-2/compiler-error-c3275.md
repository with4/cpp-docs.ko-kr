---
title: "컴파일러 오류 C3275 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3275"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3275"
ms.assetid: 5752680f-7d3e-4c42-ba9c-845e09d32e7a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3275
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'enum member': 한정자 없이 이 기호를 사용할 수 없습니다.  
  
 관리 코드를 사용하고 두 개 이상의 열거형에 같은 이름의 식별자가 있는 경우 식별자에 대한 참조를 명시적으로 한정해야 합니다.  
  
 C3275 오류는 **\/clr:oldSyntax**를 사용해서만 도달할 수 있습니다.  
  
 다음 샘플에서는 C3275가 생성될 수 있는 두 가지 경우를 보여 줍니다.  
  
```  
// C3275.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __value enum Jewelry { necklace, brooch, pin, ring, earring }; __value enum Phone { busy, ring, disconnect }; int main() { Phone p = ring;   // C3275 // try the following line instead // Phone p = Phone::ring; Console::Out->Write(ring);   // C3275 // try the following line instead // Console::Out->Write(Phone::ring); }  
```