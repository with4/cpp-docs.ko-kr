---
title: "__popcnt16, __popcnt, __popcnt64 | Microsoft Docs"
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
  - "__popcnt64"
  - "__popcnt"
  - "__popcnt16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "popcnt 명령"
  - "__popcnt16"
  - "__popcnt64"
  - "__popcnt"
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __popcnt16, __popcnt, __popcnt64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 1의 개수 \(인구 카운트\) 비트에서 16 비트, 32 비트 또는 64 바이트 부호 없는 정수입니다.  
  
## 구문  
  
```  
unsigned short __popcnt16(  
   unsigned short value  
);  
unsigned int __popcnt(  
   unsigned int value  
);  
unsigned __int64 __popcnt64(  
   unsigned __int64 value  
);  
```  
  
#### 매개 변수  
 \[in\] `value`  
 16\-, 32\-, 또는 우리는 인구 수를 64 비트 부호 없는 정수입니다.  
  
## 반환 값  
 하나의 비트에는 `value` 매개 변수.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__popcnt16`|고급 비트 조작|  
|`__popcnt`|고급 비트 조작|  
|`__popcnt64`|64 비트 모드에서 고급 비트 조작 합니다.|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 각 이러한 내장 함수를 생성 하는 `popcnt` 명령.  값의 크기는 해당 `popcnt` 명령 반환 인수의 크기와 동일 합니다.  32 비트 모드에서 가지 않습니다 64 비트 범용 레지스터, 따라서 아니오 64 비트 `popcnt`.  
  
 하드웨어 지원을 확인 하는 `popcnt` 명령, 호출의 `__cpuid` 내장 형식으로 `InfoType=0x00000001` 의 23 비트를 확인 하 고 `CPUInfo[2] (ECX)`.  그렇지 않으면이 비트 명령을 지 원하는 경우, 1과 0입니다.  코드를 사용 하 여 내장이 지원 하지 않는 하드웨어에서 실행 하 여 경우는 `popcnt` 명령의 결과 없는 예측 합니다.  
  
## 예제  
  
```  
#include <iostream>   
#include <intrin.h>   
using namespace std;   
  
int main()   
{  
  unsigned short us[3] = {0, 0xFF, 0xFFFF};  
  unsigned short usr;  
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};  
  unsigned int   uir;  
  
  for (int i=0; i<3; i++) {  
    usr = __popcnt16(us[i]);  
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __popcnt(ui[i]);  
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
  **\_\_popcnt16\(0x0\) \= 0 \_\_popcnt16\(0xff\) 8 \_\_popcnt16\(0xffff\) \= \= 16 \_\_popcnt\(0x0\) 0 \_\_popcnt\(0xff\) \= 8 \_\_oopcnt\(0xffff\) \= 16 \_\_popcnt\(0xffffffff\) \= \= 32**   
## Microsoft 특정 끝  
 저작권 2007 고급 마이크로 장치, Inc의. 모든 권리는 유보 됩니다.  사용 권한에서 고급 마이크로 장치, Inc를 재현.  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)