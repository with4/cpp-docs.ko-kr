---
title: "_ReadBarrier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ReadBarrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReadBarrier 내장 함수"
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _ReadBarrier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 호출 시점 전체에서 메모리 액세스 작업을 다시 정렬할 수 있는 컴파일러 최적화를 제한합니다.  
  
> [!CAUTION]
>  `_ReadBarrier`, `_WriteBarrier` 및 `_ReadWriteBarrier` 컴파일러 내장 함수 및 `MemoryBarrier` 매크로는 모두 더 이상 사용되지 않으므로 사용하면 안 됩니다.  스레드 간 통신의 경우 [C\+\+ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)에 정의된 [atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md) 및 [std::atomic\<T\>](../standard-library/atomic.md)와 같은 메커니즘을 사용합니다.  하드웨어 액세스의 경우 [volatile](../cpp/volatile-cpp.md) 키워드와 함께 [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러 옵션을 사용합니다.  
  
## 구문  
  
```  
void _ReadBarrier(void);  
```  
  
## 요구 사항  
  
|내장 함수|아키텍처|  
|-----------|----------|  
|`_ReadBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 `_ReadBarrier` 내장 함수는 호출 시점 전체에서 메모리 액세스 작업을 제거 또는 다시 정렬할 수 있는 컴파일러 최적화를 제한합니다.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)