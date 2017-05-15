---
title: _splitpath, _wsplitpath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsplitpath
- _splitpath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
dev_langs:
- C++
helpviewer_keywords:
- _splitpath function
- pathnames
- wsplitpath function
- splitpath function
- _wsplitpath function
- tsplitpath function
- path names
- _tsplitpath function
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
caps.latest.revision: 18
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: bbd6a163df9daf8e699f3ecf52325786fe89d8ea
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="splitpath-wsplitpath"></a>_splitpath, _wsplitpath
경로 이름을 구성 요소로 분해합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
void _splitpath(  
   const char *path,  
   char *drive,  
   char *dir,  
   char *fname,  
   char *ext   
);  
void _wsplitpath(  
   const wchar_t *path,  
   wchar_t *drive,  
   wchar_t *dir,  
   wchar_t *fname,  
   wchar_t *ext   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `path`  
 전체 경로입니다.  
  
 `drive`  
 뒤에 콜론(`:`)이 붙은 드라이브 문자입니다. 드라이브 문자가 필요하지 않은 경우 이 매개 변수에 대해 `NULL`을 전달할 수 있습니다.  
  
 `dir`  
 후행 슬래시를 포함한 디렉터리 경로입니다. 슬래시(`/`), 백슬래시(`\`) 또는 두 슬래시를 모두 사용할 수 있습니다. 디렉터리 경로가 필요하지 않은 경우 이 매개 변수에 대해 `NULL`을 전달할 수 있습니다.  
  
 `fname`  
 기본 파일 이름(확장명 없음)입니다. 파일 이름이 필요하지 않은 경우 이 매개 변수에 대해 `NULL`을 전달할 수 있습니다.  
  
 `ext`  
 선행 마침표(`.`)를 포함한 파일 이름 확장명입니다. 파일 이름 확장명이 필요하지 않은 경우 이 매개 변수에 대해 `NULL`을 전달할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `_splitpath` 함수는 경로를 4개 구성 요소로 분해합니다. `_splitpath`는 현재 사용 중인 멀티바이트 코드 페이지에 따라 멀티바이트 문자 시퀀스를 인식하며 멀티바이트 문자열 인수를 자동으로 적절히 처리합니다. `_wsplitpath`는 `_splitpath`의 와이드 문자 버전이며, `_wsplitpath`에 대한 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.  
  
 **보안 정보** 이러한 함수는 버퍼 오버런 문제로 인해 발생하는 잠재적인 위협을 일으킵니다. 버퍼 오버런 문제는 자주 사용되는 시스템 공격 방법으로, 불필요한 권한 상승을 초래합니다. 자세한 내용은 [버퍼 오버런 방지](http://msdn.microsoft.com/library/windows/desktop/ms717795)를 참조하세요. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath`|`_splitpath`|`_splitpath`|`_wsplitpath`|  
  
 전체 경로의 각 구성 요소는 별도의 버퍼에 저장됩니다. 매니페스트 상수 `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME` 및 `_MAX_EXT`(STDLIB.H에 정의됨)는 각 파일 구성 요소의 최대 크기를 지정합니다. 해당 매니페스트 상수보다 큰 파일 구성 요소가 있으면 힙이 손상됩니다.  
  
 버퍼 오버런 가능성을 방지하려면 각 버퍼가 해당하는 매니페스트 상수만큼 커야 합니다.  
  
 다음 표에는 매니페스트 상수의 값이 나와 있습니다.  
  
|이름|값|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 전체 경로에 파일 이름 등의 구성 요소가 포함되어 있지 않으면 `_splitpath`는 해당 버퍼에 빈 문자열을 할당합니다.  
  
 필요하지 않은 `path` 이외의 매개 변수에 대해 `NULL`을 `_splitpath`에 전달할 수 있습니다.  
  
 `path`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno`는 `EINVAL`로 설정되고 함수는 `EINVAL`을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_splitpath`|\<stdlib.h>|  
|`_wsplitpath`|\<stdlib.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)
