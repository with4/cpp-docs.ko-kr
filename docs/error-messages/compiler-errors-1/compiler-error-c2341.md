---
title: "컴파일러 오류 C2341 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2341"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2341"
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2341
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'section name' : 세그먼트를 사용하려면 먼저 \#pragma data\_seg, code\_seg 또는 section을 사용하여 세그먼트를 정의해야 합니다.  
  
 [allocate](../../cpp/allocate.md) 문은 [code\_seg](../../preprocessor/code-seg.md), [data\_seg](../../preprocessor/data-seg.md) 또는 [section](../../preprocessor/section.md) pragma가 아직 정의하지 않은 세그먼트를 참조합니다.  
  
 다음 샘플에서는 C2341 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2341.cpp  
// compile with: /c  
__declspec(allocate(".test"))   // C2341  
int j = 1;  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2341b.cpp  
// compile with: /c  
#pragma data_seg(".test")  
__declspec(allocate(".test"))  
int j = 1;  
```