---
title: "_get_osfhandle | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_osfhandle
- _get_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: 14
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 314f57a38cdabb4257624550f6686075a5b61697
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="getosfhandle"></a>_get_osfhandle
지정된 파일 설명자와 연결된 운영 체제 파일 핸들을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fd`  
 기존 파일 설명자입니다.  
  
## <a name="return-value"></a>반환 값  
 `fd`가 올바른 경우 운영 체제 파일 핸들입니다. 그렇지 않으면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속 허용 된 경우이 함수는 반환 `INVALID_HANDLE_VALUE` (-1)을 설정 하 고 `errno` 를 `EBADF`, 잘못 된 파일 핸들을 나타내는 합니다.  
  
## <a name="remarks"></a>설명  
 `_get_osfhandle`을 사용하여 열린 파일을 닫으려면 `_close`를 호출합니다. 기본 핸들도 `_close`에 대한 호출에 의해 닫히므로 원래 핸들에 대해 Win32 함수 `CloseHandle`을 호출할 필요가 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_get_osfhandle`|\<io.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
