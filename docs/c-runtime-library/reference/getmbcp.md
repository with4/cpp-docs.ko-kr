---
title: "_getmbcp | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getmbcp
- getmbcp
dev_langs:
- C++
helpviewer_keywords:
- code pages, determining current
- _getmbcp function
- getmbcp function
ms.assetid: 2db202d4-5c3d-4871-a0b8-ceb0b79ee7bb
caps.latest.revision: 13
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: cb47fa5dcddba6564e17d9a98a5d0279c0431be7
ms.lasthandoff: 02/24/2017

---
# <a name="getmbcp"></a>_getmbcp
현재 코드 페이지를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _getmbcp( void );  
```  
  
## <a name="return-value"></a>반환 값  
 현재 멀티바이트 코드 페이지를 반환합니다. 반환 값 0은 싱글바이트 코드 페이지를 사용 중임을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_getmbcp`|\<mbctype.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)
