---
title: "fp_contract | Microsoft Docs"
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
  - "vc-pragma.fp_contract"
  - "fp_contract_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fp_contract pragma"
  - "pragma, fp_contract"
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
caps.latest.revision: 12
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fp_contract
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

부동 소수점 축약 발생 여부를 결정합니다.  
  
## 구문  
  
```  
#pragma fp_contract [ON | OFF]  
```  
  
## 설명  
 `fp_contract`는 기본적으로 사용하도록 설정되어 있습니다.  
  
 부동 소수점 동작에 대한 자세한 내용은 [\/fp\(부동 소수점 동작 지정\)](../build/reference/fp-specify-floating-point-behavior.md)를 참조하십시오.  
  
 다른 부동 소수점 pragma는 다음과 같습니다.  
  
-   [fenv\_access](../preprocessor/fenv-access.md)  
  
-   [float\_control](../preprocessor/float-control.md)  
  
## 예제  
 이 샘플에서 생성된 코드에서는 Itanium 프로세서에 대해 **fma**\(Fused Multiply Add\) 명령을 사용하지 않습니다.  `#pragma fp_contract (off)`를 주석으로 처리할 경우 생성된 코드는 **fma** 명령을 사용합니다.  
  
```  
// pragma_directive_fp_contract.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>  
  
#pragma fp_contract (off)   
  
int main() {  
   double z, b, t;  
  
   for (int i = 0; i < 10; i++) {  
      b = i * 5.5;  
      t = i * 56.025;  
      _set_controlfp(_PC_24, _MCW_PC);  
  
      z = t * i + b;  
      printf_s ("out=%.15e\n", z);  
   }  
}  
```  
  
  **out\=0.000000000000000e\+000**  
**out\=6.152500152587891e\+001**  
**out\=2.351000061035156e\+002**  
**out\=5.207249755859375e\+002**  
**out\=9.184000244140625e\+002**  
**out\=1.428125000000000e\+003**  
**out\=2.049899902343750e\+003**  
**out\=2.783724853515625e\+003**  
**out\=3.629600097656250e\+003**  
**out\=4.587524902343750e\+003**   
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)