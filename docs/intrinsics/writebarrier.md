---
title: "_WriteBarrier | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_WriteBarrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_WriteBarrier 내장 함수"
  - "WriteBarrier 내장 함수"
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _WriteBarrier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 호출 시점 전체에서 메모리 액세스 작업을 다시 정렬할 수 있는 컴파일러 최적화를 제한합니다.  
  
> [!CAUTION]
>  `_ReadBarrier`, `_WriteBarrier` 및 `_ReadWriteBarrier` 컴파일러 내장 함수 및 `MemoryBarrier` 매크로는 모두 더 이상 사용되지 않으므로 사용하면 안 됩니다.  스레드 간 통신의 경우 [C\+\+ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)에 정의된 [atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md) 및 [std::atomic\<T\>](../standard-library/atomic.md)와 같은 메커니즘을 사용합니다.  하드웨어 액세스의 경우 [volatile](../cpp/volatile-cpp.md) 키워드와 함께 [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러 옵션을 사용합니다.  
  
## 구문  
  
```  
void _WriteBarrier(void);  
```  
  
## 요구 사항  
  
|내장 함수|아키텍처|  
|-----------|----------|  
|`_WriteBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 `_WriteBarrier` 내장 함수는 호출 시점 전체에서 메모리 액세스 작업을 제거 또는 다시 정렬할 수 있는 컴파일러 최적화를 제한합니다.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [\_ReadBarrier](../intrinsics/readbarrier.md)   
 [\_ReadWriteBarrier](../intrinsics/readwritebarrier.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)