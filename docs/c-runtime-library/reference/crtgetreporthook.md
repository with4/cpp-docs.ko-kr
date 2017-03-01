---
title: "_CrtGetReportHook | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtGetReportHook
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
- CrtGetReportHook
- _CrtGetReportHook
dev_langs:
- C++
helpviewer_keywords:
- CrtGetReportHook function
- _CrtGetReportHook function
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7f70ab172614c6bc3d4462f31f8a17590ddaab55
ms.lasthandoff: 02/24/2017

---
# <a name="crtgetreporthook"></a>_CrtGetReportHook
디버그 보고 프로세스에서 C 런타임에 클라이언트 정의 보고 함수를 연결하기 위해 해당 함수를 검색합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
_CRT_REPORT_HOOK _CrtGetReportHook( void );  
```  
  
## <a name="return-value"></a>반환 값  
 현재 클라이언트 정의 보고 함수를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_CrtGetReportHook`를 사용하면 응용 프로그램이 C 런타임 디버그 라이브러리 보고 프로세스에서 현재 보고 함수를 검색할 수 있습니다.  
  
 다른 후크 가능 런타임 함수를 사용하고 고유한 클라이언트 정의 후크 함수를 작성하는 방법에 대한 자세한 내용은 [디버그 후크 함수 작성](/visualstudio/debugger/debug-hook-function-writing)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_CrtGetReportHook`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="example"></a>예제  
 `_CrtSetReportHook`를 사용하는 방법에 대한 샘플은 [report 샘플: C 런타임 디버깅 보고서 함수](http://msdn.microsoft.com/en-us/f6e08c30-6bd9-459a-830a-56deec0d2051)를 참조하세요.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md)
