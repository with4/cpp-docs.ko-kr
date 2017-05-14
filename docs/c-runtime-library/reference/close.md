---
title: "_close | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _close
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
- _close
dev_langs:
- C++
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
caps.latest.revision: 12
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 9dab323afc6c70e81592119e0cec2775c239d87f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="close"></a>_close
파일을 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _close(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fd`  
 열려 있는 파일을 참조하는 파일 설명자입니다.  
  
## <a name="return-value"></a>반환 값  
 파일을 성공적으로 닫은 경우 `_close`는 0을 반환합니다. 반환 값-1의 오류를 나타냅니다.  
  
## <a name="remarks"></a>설명  
 `_close` 함수는 `fd`와 연결된 파일을 닫습니다.  
  
 파일 설명자와 기본 OS 파일 핸들을 닫습니다. 따라서 파일이 원래 Win32 함수 `CreateFile`을 사용하여 열리고 `_open_osfhandle`을 사용하여 파일 설명자로 변환된 경우 `CloseHandle`을 호출할 필요가 없습니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `fd`가 잘못된 파일 설명자인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속 실행하도록 허용된 경우 함수가 -1을 반환하며, `errno`가 `EBADF`로 설정됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_close`|\<io.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [_open](../../c-runtime-library/reference/open-wopen.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_unlink, _wunlink](../../c-runtime-library/reference/unlink-wunlink.md)
