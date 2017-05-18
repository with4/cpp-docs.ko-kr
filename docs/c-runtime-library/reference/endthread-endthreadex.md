---
title: "_endthread, _endthreadex | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _endthread
- _endthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
dev_langs:
- C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: e329acaad53c8990f335394bbcb8f0401d71c463
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex
스레드를 종료합니다. `_endthread` 는 `_beginthread` 로 만든 스레드를 종료하고  `_endthreadex` 는 `_beginthreadex`로 만든 스레드를 종료합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void _endthread( void );  
void _endthreadex(   
   unsigned retval   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `retval`  
 스레드 종료 코드입니다.  
  
## <a name="remarks"></a>설명  
 `_endthread` 또는 `_endthreadex` 를 명시적으로 호출하여 스레드를 종료할 수 있지만 스레드가 `_endthread` 또는 `_endthreadex` 에 매개 변수로 전달된 루틴에서 반환되면 `_beginthread` 또는 `_beginthreadex`는 자동으로 호출됩니다. `endthread` 또는 `_endthreadex` 에 대한 호출로 스레드를 종료하면 스레드에 할당된 리소스의 적절한 복구를 보장하는 데 도움이 됩니다.  
  
> [!NOTE]
>  Libcmt.lib로 연결된 실행 파일의 경우 런타임 시스템이 할당된 리소스를 회수하지 않도록 Win32 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) API를 호출하지 마세요. `_endthread` 및 `_endthreadex` 는 할당된 스레드 리소스를 회수한 다음 `ExitThread`를 호출합니다.  
  
 `_endthread`는 스레드 핸들을 자동으로 닫습니다. 이 동작은 Win32 `ExitThread` API와 다릅니다. 따라서 `_beginthread` 및 `_endthread`를 사용할 때는 Win32 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API를 호출해서 스레드 핸들을 명시적으로 닫지 마세요.  
  
 Win32 `ExitThread` API처럼 `_endthreadex` 는 스레드 핸들을 닫지 않습니다. 따라서 `_beginthreadex` 및 `_endthreadex`를 사용할 때는 Win32 `CloseHandle` API를 호출해서 스레드 핸들을 닫아야 합니다.  
  
> [!NOTE]
>  `_endthread` 및 `_endthreadex`는 호출되지 않은 스레드에서 C++ 소멸자가 보류되도록 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_endthread`|\<process.h>|  
|`_endthreadex`|\<process.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 다중 스레드 버전의 유일한 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
 [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md)에 대한 예를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)
