---
title: "__stosd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__stosd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stosd 명령"
  - "rep stosd 명령"
  - "__stosd 내장 함수"
ms.assetid: 03104247-1cea-49f6-b6f8-287917bf5680
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# __stosd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 된 저장소 문자열 명령 \(`rep stosd`\).  
  
## 구문  
  
```  
void __stosd(   
   unsigned long* Dest,   
   unsigned long Data,   
   size_t Count   
);  
```  
  
#### 매개 변수  
 \[out\] `Dest`  
 대상 작업입니다.  
  
 \[in\] `Data`  
 저장할 데이터입니다.  
  
 \[in\] `Count`  
 쓸 더블 워드 개 블록의 길이입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__stosd`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 결과 더블 워드 `Data` 의 블록으로 쓰여집니다 `Count` 를 더블 워드 개 메모리 위치를 가리키는 여 `Dest`.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
// stosd.c  
// processor: x86, x64  
  
#include <stdio.h>  
#include <memory.h>  
#include <intrin.h>  
  
#pragma intrinsic(__stosd)  
  
int main()  
{  
    unsigned long val = 99999;  
    unsigned long a[10];  
  
    memset(a, 0, sizeof(a));  
    __stosd(a+1, val, 2);  
  
printf_s( "%u %u %u %u",  
              a[0], a[1], a[2], a[3]);   
}  
```  
  
  **0 99999 99999 0**   
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)