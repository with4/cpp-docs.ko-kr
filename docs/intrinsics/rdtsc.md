---
title: "__rdtsc | Microsoft Docs"
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
  - "__rdtsc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__rdtsc 내장 함수"
  - "rdtsc 명령"
  - "타임스탬프 카운터 읽기 명령"
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __rdtsc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 하는 `rdtsc` 프로세서 시간 스탬프를 반환 하는 명령입니다.  마지막 재설정 이후 클록 주기 수를 프로세서 시간 스탬프를 기록합니다.  
  
## 구문  
  
```  
unsigned __int64 __rdtsc();  
```  
  
## 반환 값  
 틱 수를 나타내는 64 비트 부호 없는 정수입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__rdtsc`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 루틴은만 내장로 사용할 수 있습니다.  
  
 이전 버전의 해석은 TSC 값이 생성 되는 하드웨어와 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  자세한 내용은 하드웨어 설명서를 참조 하십시오.  
  
## 예제  
  
```  
// rdtsc.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__rdtsc)  
  
int main()  
{  
    unsigned __int64 i;  
    i = __rdtsc();  
    printf_s("%I64d ticks\n", i);  
}  
```  
  
  **3363423610155519 틱**   
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)