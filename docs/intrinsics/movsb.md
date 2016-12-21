---
title: "__movsb | Microsoft Docs"
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
  - "__movsb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "movsb 명령"
  - "rep movsb 명령"
  - "__movsb 내장 함수"
ms.assetid: ba5469f6-f797-4cd2-bee8-74c7666c26d4
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __movsb
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 이동 문자열이 생성 \(`rep movsb`\) 명령.  
  
## 구문  
  
```  
void __movsb(   
   unsigned char* Destination,   
   unsigned const char* Source,   
   size_t Count   
);  
```  
  
#### 매개 변수  
 \[out\] `Destination`  
 대상 복사본에 대 한 포인터입니다.  
  
 \[in\] `Source`  
 원본 복사본에 대 한 포인터입니다.  
  
 \[in\] `Count`  
 복사할 바이트 수입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__movsb`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 따라서 첫 번째 `Count` 바이트 수로를 가리키는 `Source` 복사 되는 `Destination` 문자열.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
// movsb.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__movsb)  
  
int main()  
{  
    unsigned char s1[100];  
    unsigned char s2[100] = "A big black dog.";  
    __movsb(s1, s2, 100);  
  
    printf_s("%s %s", s1, s2);  
}  
```  
  
  **큰 검정 강아지입니다.**  
 **큰 검정 강아지입니다.**   
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)