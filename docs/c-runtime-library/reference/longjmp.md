---
title: "longjmp | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: longjmp
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords: longjmp
dev_langs: C++
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 25023a1bfa0854d628931d5de9a852cae1d88ba5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="longjmp"></a>longjmp
스택 환경 및 실행 로캘을 복원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      void longjmp(  
   jmp_buf env,  
   int value   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `env`  
 환경이 저장되는 변수입니다.  
  
 *value*  
 `setjmp` 호출에 대해 반환되는 값입니다.  
  
## <a name="remarks"></a>설명  
 `longjmp` 함수는 `env`에 의해 `setjmp`에서 이전에 저장된 스택 환경 및 실행 로캘을 복원합니다. `setjmp` 및 `longjmp`는 로캘이 아닌 `goto`를 실행하는 방법을 제공합니다. 이는 일반적으로 표준 호출 및 반환 규칙을 사용하지 않고 이전에 호출된 루틴에서 오류 처리 또는 복구 코드에 실행 제어를 전달하는 데 사용됩니다.  
  
 `setjmp`에 대한 호출은 현재 스택 환경을 `env`에 저장합니다. `longjmp`에 대한 후속 호출은 저장된 환경을 복원하고 컨트롤을 해당 `setjmp` 호출 바로 다음에 오는 포인터로 반환합니다. *value*가 `setjmp` 호출에 의해 반환된 것처럼 실행이 다시 시작됩니다. 컨트롤을 받는 루틴에 액세스할 수 있는 모든 변수 값(레지스터 변수 제외)은 `longjmp`가 호출될 때 가지고 있던 값을 포함합니다. 레지스터 변수 값은 예측할 수 없습니다. `setjmp`에서 반환되는 값은 0이 아니어야 합니다. *value*가 0으로 전달되는 경우 값 1은 실제 반환에서 대체됩니다.  
  
 `longjmp`를 호출한 함수가 반환되기 전에 `setjmp`를 호출합니다. 그렇지 않으면 결과를 예측할 수 없습니다.  
  
 `longjmp`를 사용할 때 다음 제한 사항을 준수하십시오.  
  
-   레지스터 변수 값이 그대로 유지된다고 가정하지 마십시오. `setjmp`를 호출하는 루틴의 레지스터 변수 값은 `longjmp`가 실행된 이후 적절한 값으로 복원되지 않을 수 있습니다.  
  
-   부동 소수점 예외로 인해 인터럽트가 발생하지 않는 한 `longjmp`를 사용하여 컨트롤을 인터럽트 처리 루틴 외부로 전달하지 마십시오. 이 경우 먼저 `longjmp`을 호출하여 부동 소수점 연산 패키지를 다시 초기화하는 경우 프로그램은 `_fpreset`를 통해 인터럽트 처리기에서 반환될 수 있습니다.  
  
     **참고** C++ 프로그램에서 `setjmp` 및 `longjmp`를 사용할 때는 주의하세요. 이러한 함수는 C++ 개체 의미 체계를 지원하지 않기 때문에 C++ 예외 처리 메커니즘을 사용하는 것이 보다 안전합니다.  
  
 자세한 내용은 [setjmp 및 longjmp 사용](../../cpp/using-setjmp-longjmp.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`longjmp`|\<setjmp.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
 [_fpreset](../../c-runtime-library/reference/fpreset.md)에 대한 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [setjmp](../../c-runtime-library/reference/setjmp.md)