---
title: __ud2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __ud2
dev_langs: C++
helpviewer_keywords:
- UD2 instruction
- __ud2 intrinsic
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 699e575d283f830d94c123f7748f7fdaa6272ff5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ud2"></a>__ud2
**Microsoft 전용**  
  
 정의 되지 않은 명령을 생성 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __ud2();  
```  
  
## <a name="remarks"></a>설명  
 프로세서는 정의 되지 않은 명령을 실행 하는 경우 잘못 된 opcode 예외가 발생 합니다.  
  
 `__ud2` 함수는 동일는 `UD2` 컴퓨터, 명령 및 커널 모드 에서만 사용할 수 있습니다. 자세한 내용을 보려면 문서에 대 한 검색 "Intel 아키텍처 소프트웨어 개발자 설명서, 볼륨 2: 명령 집합 참조"에 [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) 사이트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__ud2`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
**Microsoft 전용 종료**  
  
## <a name="example"></a>예제  
 다음 예제에서는 예외가 발생 하는 정의 되지 않은 명령을 실행 합니다. 예외 처리기 하나에 0에서 반환 코드를 변경합니다.  
  
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
  
```Output  
Before __ud2(). Return code = 0.  
  In the exception handler.  
After __ud2().  Return code = 1.  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)