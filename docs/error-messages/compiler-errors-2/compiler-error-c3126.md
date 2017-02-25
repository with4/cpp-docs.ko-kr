---
title: "컴파일러 오류 C3126 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3126"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3126"
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3126
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'union' 공용 구조체를 관리되는 형식 'type' 내부에 정의할 수 없습니다.  
  
 공용 구조체를 관리되는 형식 내부에 정의할 수 없습니다.  
  
 다음 샘플에서는 C3126 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3126_2.cpp  
// compile with: /clr /c  
ref class Test  
{  
   union x  
   {   // C3126  
      int a;  
      int b;  
   };  
};  
```  
  
 다음 샘플에서는 C3126 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3126.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
  
__gc class Test  
{  
   union x  
   {   // C3126  
      int a;  
      int b;  
   };  
};  
```