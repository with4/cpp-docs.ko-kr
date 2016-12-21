---
title: "__movsd | Microsoft Docs"
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
  - "__movsd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rep movsd 명령"
  - "__movsd 내장 함수"
  - "movsd 명령"
ms.assetid: eb5cccf3-aa76-47f0-b9fc-eeca38fd943f
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __movsd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 이동 문자열이 생성 \(`rep movsd`\) 명령.  
  
## 구문  
  
```  
void __movsd(   
   unsigned long* Dest,   
   unsigned long* Source,   
   size_t Count   
);  
```  
  
#### 매개 변수  
 \[out\] `Dest`  
 대상 작업입니다.  
  
 \[in\] `Source`  
 소스 작업입니다.  
  
 \[in\] `Count`  
 복사할 더블 워드 개 개수입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__movsd`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 따라서 첫 번째 `Count` 더블 워드 개 여를 가리키는 `Source` 복사 되는 `Dest` 문자열.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
// movsd.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__movsd)  
  
int main()  
{  
    unsigned long a1[10];  
    unsigned long a2[10] = {950, 850, 750, 650, 550, 450, 350,  
                            250, 150, 50};  
    __movsd(a1, a2, 10);  
  
    for (int i = 0; i < 10; i++)  
        printf_s("%d ", a1[i]);  
    printf_s("\n");  
}  
```  
  
  **950 850 750 650 550 450 350 250 150 50**    
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)