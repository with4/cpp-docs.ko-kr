---
title: "컴파일러 경고 (수준 1) C4945 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4945"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4945"
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4945
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': 'assembly2'에서 기호를 가져올 수 없습니다. 'symbol'을\(를\) 다른 어셈블리 'assembly1'에서 이미 가져왔습니다.  
  
 다른 참조된 어셈블리에서 이미 가져온 기호를 참조된 어셈블리에서 다시 가져왔습니다.  어셈블리 중 하나를 참조하지 않거나 어셈블리 중 하나의 기호 이름을 변경하십시오.  
  
 다음 샘플에서는 C4945 경고가 발생하는 경우를 보여 줍니다. 첫 번째 코드 파일:  
  
```  
// C4945a.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 두 번째 코드 파일:  
  
```  
// C4945b.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 두 번째 코드 파일:  
  
```  
// C4945c.cpp  
// compile with: /clr /LD /W1  
#using "C4945a.dll"  
#using "C4945b.dll"   // C4945  
```