---
title: "컴파일러 경고 (수준 4) C4337 | Microsoft Docs"
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
  - "C4337"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4337"
ms.assetid: 70bc72d9-aac5-45cd-abd3-ebe42a05897b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4337
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'typelib1' 상호 참조된 형식 라이브러리\('typelib2'의\)를 자동으로 가져옵니다.  
  
 [\#import 지시문](../../preprocessor/hash-import-directive-cpp.md)의 auto\_search 특성으로 인해 형식 라이브러리를 암시적으로 가져옵니다.  
  
 다음과 같이 midl.exe를 사용하여 컴파일된 두 파일에서 만들어진 두 개의 형식 라이브러리가 디스크에 있다고 가정합니다.  
  
```  
// C4337a.idl  
[  
  uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12B)  
]  
library C4337aLib  
{  
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12C)]  
   enum E_C4337a  
   {  
      one = 0,  
      two = 1,  
      three = 2  
    };  
};  
```  
  
 그리고 두 번째 .idl 파일이 있다고 가정합니다.  
  
```  
// C4337b.idl  
[  
   uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12D)  
]  
  
library C4337bLib  
{  
   importlib("c4337a.tlb");  
  
   [uuid(F87070BA-C6D9-405C-A8E4-8CD9CA25C12E)]  
   struct S_C4337b  
   {  
      enum E_C4337a e;  
   };  
};  
```  
  
 다음 샘플에서는 C4337 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4337.cpp  
// compile with: /W4 /LD  
#import "c4337b.tlb" auto_search   // C4337  
// explicitly #import all type libraries to resolve  
// #import "C4337a.tlb"  
// #import "C4337b.tlb"  
```