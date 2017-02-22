---
title: "__segmentlimit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__segmentlimit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__segmentlimit 내장 함수"
  - "lsl 명령"
ms.assetid: d0bc3630-90cb-4185-8667-686fd41e23d4
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# __segmentlimit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 하는 `lsl` \(로드 세그먼트 제한을\) 명령.  
  
## 구문  
  
```  
unsigned long __segmentlimit(   
   unsigned long a   
);  
```  
  
#### 매개 변수  
 \[in\] `a`  
 세그먼트 선택기를 지정 하는 상수입니다.  
  
## 반환 값  
 세그먼트 제한을 지정한 세그먼트 선택기의 `a,` 선택기는 현재 사용 권한 수준에서 유효 하 고 표시 되는.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__segmentlimit`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 세그먼트 제한을 검색할 수 없는 경우이 명령은 실패 합니다.  오류가 발생 하면이 명령 ZF 플래그를 지우고 반환 값이 정의 되지 않았습니다.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 예제  
  
```  
#include <stdio.h>  
  
#ifdef _M_IX86  
typedef unsigned int READETYPE;  
#else  
typedef unsigned __int64 READETYPE;  
#endif  
  
#define EFLAGS_ZF      0x00000040  
#define KGDT_R3_DATA    0x0020  
#define RPL_MASK        0x3  
  
extern "C"  
{  
unsigned long __segmentlimit (unsigned long);  
READETYPE __readeflags();  
}  
  
#pragma intrinsic(__readeflags)  
#pragma intrinsic(__segmentlimit)  
  
int main(void)  
{  
   const unsigned long initsl = 0xbaadbabe;  
   READETYPE eflags = 0;  
   unsigned long sl = initsl;  
  
   printf("Before: segment limit =0x%x eflags =0x%x\n", sl, eflags);  
   sl = __segmentlimit(KGDT_R3_DATA + RPL_MASK);  
  
   eflags = __readeflags();  
  
   printf("After: segment limit =0x%x eflags =0x%x eflags.zf = %s\n", sl, eflags, (eflags & EFLAGS_ZF) ? "set" : "clear");  
  
   // If ZF is set, the call to lsl succeeded; if ZF is clear, the call failed.  
   printf("%s\n", eflags & EFLAGS_ZF ? "Success!": "Fail!");  
  
   // You can verify the value of sl to make sure that the instruction wrote to it  
   printf("sl was %s\n", (sl == initsl) ? "unchanged" : "changed");  
  
   return 0;  
}  
```  
  
  **이전: 세그먼트 제한을 0xbaadbabe eflags \= \= 0x0 후: 세그먼트 제한을 0xffffffff eflags \= 0x256 eflags.zf \= \= 설정 성공\!**  
 **sl 변경 되었습니다.**   
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)