---
title: "__lzcnt16, __lzcnt, __lzcnt64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__lzcnt64"
  - "__lzcnt16"
  - "__lzcnt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__lzcnt 내장 함수"
  - "lzcnt 명령"
  - "lzcnt16 내장 함수"
  - "lzcnt 내장 함수"
  - "__lzcnt16 내장 함수"
  - "lzcnt64 내장 함수"
  - "__lzcnt64 내장 함수"
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# __lzcnt16, __lzcnt, __lzcnt64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 16\-, 32 비트 또는 64 비트 정수에 행간 수가 0을 카운트 합니다.  
  
## 구문  
  
```  
unsigned short __lzcnt16(  
   unsigned short value  
);  
unsigned int __lzcnt(  
   unsigned int value  
);  
unsigned __int64 __lzcnt64(  
   unsigned __int64 value  
);  
```  
  
#### 매개 변수  
 \[in\] `value`  
 16\-, 32 비트 또는 64 비트 부호 없는 정수 앞에 0을 스캔 합니다.  
  
## 반환 값  
 앞에 0 비트의 수는 `value` 매개 변수.  경우 `value` 0이 반환 값은 입력된 피연산자 \(16, 32, 64\)의 크기입니다.  대부분의 경우 중요 한 비트의 `value` 1 반환 값은 0입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__lzcnt16`|고급 비트 조작|  
|`__lzcnt`|고급 비트 조작|  
|`__lzcnt64`|64 비트 모드에서 고급 비트 조작 합니다.|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 각 이러한 내장 함수를 생성 하는 `lzcnt` 명령.  값의 크기는 해당 `lzcnt` 명령 반환 인수의 크기와 동일 합니다.  32 비트 모드에서 가지 않습니다 64 비트 범용 레지스터, 따라서 아니오 64 비트 `lzcnt`.  
  
 하드웨어 지원을 확인 하는 `lzcnt` 명령 호출을 `__cpuid` 내장 형식으로 `InfoType=0x80000001` 5 비트를 확인 하 고 `CPUInfo[2] (ECX)`.  이 비트 명령이 지원 되지 않으면 1, 0 그렇지 않으면 됩니다.  코드를 사용 하 여 내장이 지원 하지 않는 하드웨어에서 실행 하 여 경우는 `lzcnt` 명령의 결과 없는 예측 합니다.  
  
## 예제  
  
```  
// Compile this test with: /EHsc  
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
    usr = __lzcnt16(us[i]);  
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __lzcnt(ui[i]);  
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
  **\_\_lzcnt16\(0x0\) \= 16 \_\_lzcnt16\(0xff\) 8 \_\_lzcnt16\(0xffff\) \= 0 \_\_lzcnt\(0x0\) \= 32 \_\_lzcnt\(0xff\) \= 24 \_\_lzcnt\(0xffff\) \= 16 \_\_lzcnt\(0xffffffff\) \= 0 \=**   
## Microsoft 특정 끝  
 저작권 2007 고급 마이크로 장치, Inc의. 모든 권리는 유보 됩니다.  사용 권한에서 고급 마이크로 장치, Inc를 재현.  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)