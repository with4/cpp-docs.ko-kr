---
title: "_rotr8, _rotr16 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_rotr16"
  - "_rotr8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_rotr16 내장"
  - "_rotr8 내장"
ms.assetid: dfbd2c82-82b4-427a-ad52-51609027ebff
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _rotr8, _rotr16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 입력 값을 지정된 비트 위치 수만큼 LSB\(최하위 비트\) 오른쪽으로 회전합니다.  
  
## 구문  
  
```  
unsigned char _rotr8(     unsigned char value,     unsigned char shift  ); unsigned short _rotr16(     unsigned short value,     unsigned char shift  );  
```  
  
#### 매개 변수  
 \[in\] `value`  
 회전할 값입니다.  
  
 \[in\] `shift`  
 회전할 비트 수입니다.  
  
## 반환 값  
 순환된 값입니다.  
  
## 요구 사항  
  
|내장 함수|아키텍처|  
|-----------|----------|  
|`_rotr8`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_rotr16`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 오른쪽 시프트 작업과는 달리 오른쪽 회전을 실행할 때는 최소값에 속하는 하위 비트가 상위 비트 위치로 이동됩니다.  
  
## 예제  
  
```  
// rotr.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_rotr8, _rotr16)  
  
int main()  
{  
    unsigned char c = 'A', c1, c2;  
  
    for (int i = 0; i < 8; i++)  
    {  
       printf_s("Rotating 0x%x right by %d bits gives 0x%x\n", c,  
                i, _rotr8(c, i));  
    }  
  
    unsigned short s = 0x12;  
    int nBit = 10;  
  
    printf_s("Rotating unsigned short 0x%x right by %d bits "  
             "gives 0x%x\n",  
            s, nBit, _rotr16(s, nBit));  
}  
```  
  
  **0x41을 오른쪽으로 0비트 회전한 결과는 0x41입니다.**  
**0x41을 오른쪽으로 1비트 회전한 결과는 0xa0입니다.**  
**0x41을 오른쪽으로 2비트 회전한 결과는 0x50입니다.**  
**0x41을 오른쪽으로 3비트 회전한 결과는 0x28입니다.**  
**0x41을 오른쪽으로 4비트 회전한 결과는 0x14입니다.**  
**0x41을 오른쪽으로 5비트 회전한 결과는 0xa입니다.**  
**0x41을 오른쪽으로 6비트 회전한 결과는 0x5입니다.**  
**0x41을 오른쪽으로 7비트 회전한 결과는 0x82입니다.**  
**부호 없는 정수\(short\) 0x12를 오른쪽으로 10비트 회전한 결과는 0x480입니다.**   
## Microsoft 전용 종료  
  
## 참고 항목  
 [\_rotl8, \_rotl16](../intrinsics/rotl8-rotl16.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)