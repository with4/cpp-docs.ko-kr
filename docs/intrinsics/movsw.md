---
title: "__movsw | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__movsw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "movsw 명령"
  - "rep movsw 명령"
  - "__movsw 내장 함수"
ms.assetid: db402ad5-7f0e-449a-b0b0-eea9928d6435
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __movsw
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 이동 문자열이 생성 \(`rep movsw`\) 명령.  
  
## 구문  
  
```  
void __movsw(   
   unsigned short* Dest,   
   unsigned short* Source,   
   size_t Count   
);  
```  
  
#### 매개 변수  
 \[out\] `Dest`  
 대상 작업입니다.  
  
 \[in\] `Source`  
 소스 작업입니다.  
  
 \[in\] `Count`  
 복사 하려면 단어 개수입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__movsw`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 따라서 첫 번째 `Count` 단어 여를 가리키는 `Source` 복사 되는 `Dest` 문자열.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
// movsw.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__movsw)  
  
int main()  
{  
    unsigned short s1[10];  
    unsigned short s2[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
    __movsw(s1, s2, 10);  
  
    for (int i = 0; i < 10; i++)  
        printf_s("%d ", s1[i]);  
    printf_s("\n");  
}  
```  
  
  **0 1 2 3 4 5 6 7 8 9**    
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)