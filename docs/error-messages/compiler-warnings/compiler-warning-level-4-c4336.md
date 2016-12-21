---
title: "컴파일러 경고 (수준 4) C4336 | Microsoft Docs"
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
  - "C4336"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4336"
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4336
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

상호 참조된 형식 라이브러리 'type\_lib1'을\(를\) 'type\_lib2'을\(를\) 가져오기 전에 가져오십시오.  
  
 형식 라이브러리가 [\#import](../../preprocessor/hash-import-directive-cpp.md) 지시문을 사용하여 참조되었습니다.  하지만 `#import`를 사용하여 참조되지 않은 다른 형식 라이브러리에 대한 참조가 이 형식 라이브러리에 포함되어 있습니다.  컴파일러에서 이 .tlb 파일을 찾았습니다.  
  
 다음과 같이 midl.exe를 사용하여 컴파일된 두 파일에서 만들어진 두 개의 형식 라이브러리가 디스크에 있다고 가정합니다.  
  
```  
// c4336a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library c4336aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C4336  
   {  
      one, two, three  
   };  
};  
```  
  
 두 번째 형식 라이브러리:  
  
```  
// c4336b.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4336bLib  
{  
   importlib ("c4336a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4336  
   {  
      enum E_C4336 e;  
   };  
};  
```  
  
 다음 샘플에서는 C4336 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4336.cpp  
// compile with: /W4 /LD  
// #import "C4336a.tlb"  
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve  
```