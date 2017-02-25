---
title: "_InterlockedAddLargeStatistic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedAddLargeStatistic"
  - "_InterlockedAddLargeStatistic_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedAddLargeStatistic 내장 함수"
  - "InterlockedAddLargeStatistic 내장 함수"
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _InterlockedAddLargeStatistic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 64 비트 값의 첫 번째 피연산자는 연동된 추가 수행 합니다.  
  
## 구문  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### 매개 변수  
 \[in, out\]`Addend`  
 작업을 추가 하려면 첫 번째 피연산자에 대 한 포인터입니다.  가리키는 값 추가의 결과로 대체 됩니다.  
  
 \[in\] `Value`  
 두 번째 피연산자입니다. 첫 번째 피연산자에 추가할 값입니다.  
  
## 반환 값  
 두 번째 피연산자의 값입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`_InterlockedAddLargeStatistic`|x86|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 별도 두 잠긴된 지침으로 구현 되기 때문에 내장 원자 아닙니다.  다른 스레드에서 내장이 실행 중에 발생 하는 원자 64 비트 읽기 읽고에 일관성 없는 값을 발생할 수 있습니다.  
  
 이 함수는 읽기\-쓰기 장벽으로 동작합니다.  자세한 내용은  [\_ReadWriteBarrier](../intrinsics/readwritebarrier.md).  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [x86 컴파일러와 충돌](../build/conflicts-with-the-x86-compiler.md)