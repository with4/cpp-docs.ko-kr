---
title: "_CrtSetAllocHook | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtSetAllocHook
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
f1_keywords:
- _CrtSetAllocHook
- CrtSetAllocHook
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: fa03fb135907d9f516544f5f4b202c9f4e779fc3
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="crtsetallochook"></a>_CrtSetAllocHook
클라이언트 정의 할당 함수를 C 런타임 디버그 메모리 할당 프로세스에 연결함으로써 설치합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
_CRT_ALLOC_HOOK _CrtSetAllocHook(  
   _CRT_ALLOC_HOOK allocHook   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `allocHook`  
 C 런타임 디버그 메모리 할당 프로세스에 연결할 새로운 클라이언트 정의 할당 함수입니다.  
  
## <a name="return-value"></a>반환 값  
 이전에 정의된 할당 후크 함수를 반환하거나 `allocHook`가 `NULL`인 경우 `NULL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_CrtSetAllocHook`를 사용하면 응용 프로그램이 고유한 할당 함수를 C 런타임 디버그 라이브러리 메모리 할당 프로세스에 연결할 수 있습니다. 결과적으로 메모리 블록을 할당, 재할당 또는 해제하기 위해 디버그 할당 함수를 호출할 때마다 응용 프로그램의 후크 함수 호출이 트리거됩니다. `_CrtSetAllocHook`는 응용 프로그램에서 메모리 부족 상황을 처리하는 방식을 테스트하기 위한 쉬운 방법, 할당 패턴을 검사하는 기능 및 향후 분석을 위해 할당 정보를 기록할 기회를 응용 프로그램에 제공합니다. [_DEBUG](../../c-runtime-library/debug.md)가 정의되지 않은 경우 전처리 중 `_CrtSetAllocHook` 호출이 제거됩니다.  
  
 `_CrtSetAllocHook` 함수는 `allocHook`에 지정된 새로운 클라이언트 정의 할당 함수를 설치하고 이전에 정의된 후크 함수를 반환합니다. 다음 예제에서는 클라이언트 정의 할당 후크가 어떻게 프로토타입화되어야 하는지 보여 줍니다.  
  
```  
int YourAllocHook( int allocType, void *userData, size_t size, int   
blockType, long requestNumber, const unsigned char *filename, int   
lineNumber);  
```  
  
 `allocType` 인수는 할당의 후크 함수에 대한 호출을 트리거한 할당 작업의 형식`(_HOOK_ALLOC`, `_HOOK_REALLOC` 및 `_HOOK_FREE`)을 지정합니다. 트리거 할당 형식이 `_HOOK_FREE`인 경우 `userData`는 해제하려는 메모리 블록의 사용자 데이터 섹션에 대한 포인터입니다. 하지만 트리거 할당 형식이 `_HOOK_ALLOC` 또는 `_HOOK_REALLOC`인 경우 메모리 블록이 아직 할당되지 않았으므로 `userData`는 `NULL`입니다.  
  
 `size`는 메모리 블록의 크기를 바이트 단위로 지정하고, `blockType`은 메모리 블록의 형식을 나타내며, `requestNumber`는 메모리 블록의 개체 할당 순서 번호이고, 사용 가능한 경우 `filename` 및 `lineNumber`는 트리거 할당 작업이 시작된 소스 파일 이름 및 줄 번호를 지정합니다.  
  
 후크 함수에서 프로세스가 완료되면 후크 함수는 부울 값을 반환해야 합니다. 이를 통해 기본 C 런타임 할당 프로세스에 계속 진행하는 방식을 알려 줍니다. 후크 함수가 호출되지 않은 것처럼 후크 함수에서 기본 할당 프로세스를 계속 진행하려는 경우 후크 함수가 `TRUE`를 반환해야 합니다. 이렇게 하면 원래 트리거 할당 작업이 실행됩니다. 이 구현을 사용하여, 후크 함수는 현재 할당 작업 또는 디버그 힙의 상태를 방해하지 않고 향후 분석을 위해 할당 정보를 수집하고 저장할 수 있습니다.  
  
 트리거 할당 작업이 호출되어 실패한 것처럼 후크 함수에서 기본 할당 프로세스를 계속 진행하려는 경우 후크 함수가 `FALSE`를 반환해야 합니다. 이 구현을 사용하여, 후크 함수는 다양한 메모리 조건 및 디버그 힙 상태를 시뮬레이트하여 응용 프로그램에서 각 상황을 처리하는 방법을 테스트할 수 있습니다.  
  
 후크 함수를 지우려면 `_CrtSetAllocHook`에 `NULL`을 전달합니다.  
  
 `_CrtSetAllocHook`를 다른 메모리 관리 함수와 함께 사용할 수 있는 방법 또는 고유한 클라이언트 정의 후크 함수를 작성하는 방법에 대한 자세한 내용은 [디버그 후크 함수 작성](/visualstudio/debugger/debug-hook-function-writing)을 참조하세요.  
  
> [!NOTE]
>  `_CrtSetAllocHook`는 `/clr:pure`에서 지원되지 않습니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_CrtSetAllocHook`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="example"></a>예제  
 `_CrtSetAllocHook`를 사용하는 방법에 대한 샘플은 [crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_CrtGetAllocHook](../../c-runtime-library/reference/crtgetallochook.md)
