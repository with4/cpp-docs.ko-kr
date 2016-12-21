---
title: "__stosw | Microsoft Docs"
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
  - "__stosw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stosw 명령"
  - "__stosw 내장 함수"
  - "rep stosw 명령"
ms.assetid: 7620fd1d-dba5-40e3-8e07-01aa68895133
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __stosw
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 된 저장소 문자열 명령 \(`rep stosw`\).  
  
## 구문  
  
```  
void __stosw(   
   unsigned short* Dest,   
   unsigned short Data,   
   size_t Count   
);  
```  
  
#### 매개 변수  
 \[out\] `Dest`  
 대상 작업입니다.  
  
 \[in\] `Data`  
 저장할 데이터입니다.  
  
 \[in\] `Count`  
 쓸 수 있는 단어의 블록의 길이입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__stosw`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 결과 단어입니다 `Data` 의 블록으로 쓰여집니다 `Count` 의 단어는 `Dest` 문자열입니다.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
// stosw.c  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__stosw)  
  
int main()  
{  
    unsigned short val = 128;  
    unsigned short a[100];  
    memset(a, 0, sizeof(a));  
    __stosw(a+10, val, 2);  
    printf_s("%u %u %u %u", a[9], a[10], a[11], a[12]);     
}  
```  
  
  **0 128 128 0**   
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)