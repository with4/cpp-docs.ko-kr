---
title: "컴파일러 오류 C2356 | Microsoft Docs"
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
  - "C2356"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2356"
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2356
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

초기화 세그먼트는 번역 단위 동안 바뀌지 않아야 합니다.  
  
 가능한 원인  
  
-   `#pragma init_seg` 앞에 세그먼트 초기화 코드가 왔습니다.  
  
-   `#pragma init_seg` 앞에 다른 `#pragma init_seg`가 왔습니다.  
  
 이 오류를 해결하려면 세그먼트 초기화 코드를 모듈 시작 부분으로 이동합니다.  여러 영역을 초기화해야 하는 경우에는 이 영역들을 별개의 모듈로 이동하십시오.  
  
 다음 샘플에서는 C2356 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```