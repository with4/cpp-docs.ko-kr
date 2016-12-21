---
title: "__stosb | Microsoft Docs"
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
  - "__stosb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep stosb 명령"
  - "__stosb 내장 함수"
  - "stosb 명령"
ms.assetid: 634589ed-2da3-439b-a381-a214d89bf10c
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __stosb
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 된 저장소 문자열 명령 \(`rep stosb`\).  
  
## 구문  
  
```  
void __stosb(   
   unsigned char* Dest,   
   unsigned char Data,   
   size_t Count   
);  
```  
  
#### 매개 변수  
 \[out\] `Dest`  
 대상 작업입니다.  
  
 \[in\] `Data`  
 저장할 데이터입니다.  
  
 \[in\] `Count`  
 쓸 바이트의 블록의 길이입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__stosb`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 결과 문자는 `Data` 의 블록으로 쓰여집니다 `Count` 바이트는 `Dest` 문자열입니다.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
// stosb.c  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__stosb)  
  
int main()  
{  
    unsigned char c = 0x40; /* '@' character */  
    unsigned char s[] = "*********************************";  
  
    printf_s("%s\n", s);  
    __stosb((unsigned char*)s+1, c, 6);  
    printf_s("%s\n", s);  
  
}  
```  
  
  **\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* \*@@@@@@\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\***   
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)