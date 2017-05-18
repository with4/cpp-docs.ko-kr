---
title: _putenv, _wputenv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _putenv
- _wputenv
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
dev_langs:
- C++
helpviewer_keywords:
- _putenv function
- environment variables, deleting
- putenv function
- tputenv function
- environment variables, creating
- wputenv function
- _wputenv function
- _tputenv function
- environment variables, modifying
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: d91f7b780c8f17fbe1e12a195b6a7cf2eaad3d2f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="putenv-wputenv"></a>_putenv, _wputenv
환경 변수를 생성, 수정 또는 제거합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)를 참조하세요.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int _putenv(  
   const char *envstring   
);  
int _wputenv(  
   const wchar_t *envstring   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `envstring`  
 환경 문자열 정의입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 0 또는 오류 발생 시도-1을 반환 합니다.  
  
## <a name="remarks"></a>주의  
 `_putenv` 함수는 새 환경 변수를 추가하거나 기존 환경 변수의 값을 수정합니다. 환경 변수는 프로세스가 실행되는 환경을 정의합니다(예: 프로그램에 연결할 라이브러리의 기본 검색 경로). `_wputenv`은 `_putenv`의 와이드 문자 버전이며, `envstring`에 대한 `_wputenv` 인수는 와이드 문자열입니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tputenv`|`_putenv`|`_putenv`|`_wputenv`|  
  
 `envstring` 인수는 `varname=string` 형식 문자열에 대한 포인터여야 합니다. 여기서 `varname`은 추가하거나 수정할 환경 변수의 이름이고 `string`은 변수의 값입니다. `varname`이 이미 환경의 일부이면 해당 값이 `string`으로 바뀌고, 그렇지 않으면 새로운 `varname` 변수 및 해당 `string` 값이 환경에 추가됩니다. 빈 `string`을 지정하여, 즉 `varname=`만 지정하여 환경에서 변수를 제거할 수 있습니다.  
  
 `_putenv` 및 `_wputenv`는 현재 프로세스에 로컬인 환경에만 영향을 줍니다. 명령 수준 환경을 수정하는 데 사용할 수 없습니다. 즉, 이러한 함수는 운영 체제가 프로세스에 대해 만드는 환경 세그먼트가 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조에서만 작동합니다. 현재 프로세스가 종료되면 환경이 호출 프로세스의 수준(대부분의 경우 운영 체제 수준)으로 되돌아갑니다. 그러나 수정된 환경을 `_spawn`, `_exec` 또는 `system`에 의해 생성되는 모든 새 프로세스에 전달할 수 있으며, 이러한 새 프로세스는 `_putenv` 및 `_wputenv`에 의해 추가되는 모든 새 항목을 가져옵니다.  
  
 환경 항목은 직접 변경하는 대신 `_putenv` 또는 `_wputenv`를 사용하여 변경하세요. 특히 `_environ[]` 전역 배열의 요소를 직접 해제하면 잘못된 메모리가 처리될 수 있습니다.  
  
 `getenv` 및 `_putenv`는 전역 변수 `_environ`을 사용하여 환경 테이블에 액세스하고, `_wgetenv` 및 `_wputenv`는 `_wenviron`을 사용합니다. `_putenv`및 `_wputenv` 의 값이 변경 `_environ` 및 `_wenviron`, 따라서 무효화는 `_envp` 인수를 `main` 및 `_wenvp` 인수를 `wmain`합니다. 따라서 `_environ` 또는 `_wenviron`을 사용하여 환경 정보에 액세스하는 것이 더 안전합니다. `_putenv` 및 `_wputenv`와 전역 변수의 관계에 대한 자세한 내용은 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)을 참조하세요.  
  
> [!NOTE]
>  함수의 `_putenv` 및 `_getenv` 패밀리는 스레드로부터 안전하지 않습니다. `_getenv`는 `_putenv`가 문자열을 수정하는 동안 문자열 포인터를 반환할 수 있으므로 임의의 오류를 발생시킵니다. 이러한 함수에 대한 호출은 동기화해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_putenv`|\<stdlib.h>|  
|`_wputenv`|\<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 `_putenv` 사용 방법에 대한 샘플은 [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)
