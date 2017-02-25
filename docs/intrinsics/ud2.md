---
title: "__ud2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__ud2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UD2 명령"
  - "__ud2 내장 함수"
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __ud2
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 정의 되지 않은 명령으로 생성합니다.  
  
## 구문  
  
```  
void __ud2();  
```  
  
## 설명  
 정의 되지 않은 명령 실행 하는 경우 프로세서가 잘못 된 opcode 예외가 발생 합니다.  
  
 `__ud2` 함수는 해당 하는 `UD2` 명령, 가공 및 커널 모드 에서만 사용할 수 있습니다.  문서에 대 한 자세한 내용은 검색 "인텔 아키텍처 소프트웨어 개발자 설명서 볼륨 2: 명령 세트 참조,"에 [인텔사](http://go.microsoft.com/fwlink/?LinkId=127) 사이트.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__ud2`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 예제  
 다음 예제에서는 예외가 발생 하는 정의 되지 않은 명령을 실행 합니다.  예외 처리기는 다음 반환 코드 0 하나에서 변경합니다.  
  
```  
// __ud2_intrinsic.cpp  
#include <stdio.h>  
#include <intrin.h>  
#include <excpt.h>  
// compile with /EHa  
  
int main() {  
  
// Initialize the return code to 0.  
 int ret = 0;  
  
// Attempt to execute an undefined instruction.  
  printf("Before __ud2(). Return code = %d.\n", ret);  
  __try {   
  __ud2();   
  }  
  
// Catch any exceptions and set the return code to 1.  
  __except(EXCEPTION_EXECUTE_HANDLER){  
  printf("  In the exception handler.\n");  
  ret = 1;  
  }  
  
// Report the value of the return code.   
  printf("After __ud2().  Return code = %d.\n", ret);  
  return ret;  
}  
```  
  
  **전에 \_\_ud2\(\).**  
 **반환 코드 \= 0.**  
 **예외 처리기에서.**  
 **후 \_\_ud2\(\).**  
 **반환 코드 \= 1.**   
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)