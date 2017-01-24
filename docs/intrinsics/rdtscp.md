---
title: "__rdtscp | Microsoft Docs"
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
  - "__rdtscp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rdtscp 내장 함수"
  - "__rdtscp 내장 함수"
  - "rdtscp 명령"
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __rdtscp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 하는 `rdtscp` 명령을 씁니다 `TSC_AUX[31:0`\] 메모리 및 64 비트 시간 스탬프 카운터 반환 합니다 \(`TSC)` 결과.  
  
## 구문  
  
```  
unsigned __int64 __rdtscp(  
   unsigned int * Aux  
);  
```  
  
#### 매개 변수  
 \[out\] `Aux`  
 시스템별 레지스터의 내용을 포함 하는 위치에 대 한 포인터 `TSC_AUX[31:0]`.  
  
## 반환 값  
 64 비트 부호 없는 정수 틱 수입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__rdtscp`|AMD NPT 제품군 0Fh 또는 이후 버전|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 내장이 생성 하는 `rdtscp` 명령.  이 명령에 대 한 하드웨어 지원을 확인 하려면 호출을 `__cpuid` 내장 형식으로 `InfoType=0x80000001` 의 27 비트를 확인 하 고 `CPUInfo[3] (EDX)`.  그렇지 않으면이 비트 명령을 지 원하는 경우, 1과 0입니다.  코드를 사용 하 여 내장이 지원 하지 않는 하드웨어에서 실행 하 여 경우는 `rdtscp` 명령의 결과 없는 예측 합니다.  
  
> [!CAUTION]
>  달리 `rdtsc`, `rdtscp` 직렬화 명령이 있습니다. 그럼에도 불구 하 고 컴파일러 코드가 주위를 이동할 수 있습니다 내장.  
  
 이전 버전의 해석은 TSC 값이 생성 되는 하드웨어와 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  자세한 내용은 하드웨어 설명서를 참조 하십시오.  
  
 값의 의미 `TSC_AUX[31:0]` 운영 체제에 따라 다릅니다.  
  
## 예제  
  
```  
#include <intrin.h>   
#include <stdio.h>  
int main()   
{  
 unsigned __int64 i;  
 unsigned int ui;  
 i = __rdtscp(&ui);  
 printf_s("%I64d ticks\n", i);  
 printf_s("TSC_AUX was %x\n", ui);  
}  
```  
  
  **3363423610155519 틱 했습니다 0**   
## Microsoft 특정 끝  
 저작권 2007 고급 마이크로 장치, Inc의. 모든 권리는 유보 됩니다.  사용 권한에서 고급 마이크로 장치, Inc를 재현.  
  
## 참고 항목  
 [\_\_rdtsc](../intrinsics/rdtsc.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)