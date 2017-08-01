---
title: ___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ___mb_cur_max_l_func
- __p___mb_cur_max
- ___mb_cur_max_func
- __mb_cur_max
apilocation:
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
- __mb_cur_max
dev_langs:
- C++
helpviewer_keywords:
- __mb_cur_max
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 2aebb94a30c40446f2e892eb5c8ca024c616e15e
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="mbcurmaxfunc-mbcurmaxlfunc-pmbcurmax-mbcurmax"></a>___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max
내부 CRT 함수입니다. 현재 또는 지정된 로캘에 대한 멀티바이트 문자의 최대 바이트 수를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
int ___mb_cur_max_func(void);  
int ___mb_cur_max_l_func(_locale_t locale);  
int * __p___mb_cur_max(void);  
#define __mb_cur_max (___mb_cur_max_func())  
```  
  
#### <a name="parameters"></a>매개 변수  
 로캘(locale)  
 결과를 검색할 로캘 구조입니다. 이 값이 null이면 현재 스레드 로컬이 사용됩니다.  
  
## <a name="return-value"></a>반환 값  
 현재 스레드 로컬 또는 지정된 로컬에 대한 멀티바이트 문자의 최대 바이트 수입니다.  
  
## <a name="remarks"></a>설명  
 CRT가 스레드 로컬 저장소에서 [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md) 매크로의 현재 값을 검색하는 데 사용하는 내부 함수입니다. 사용자 코드에서는 이식성을 위해 `MB_CUR_MAX` 매크로를 사용하는 것이 좋습니다.  
  
 `__mb_cur_max` 매크로는 `___mb_cur_max_func()` 함수를 호출하는 편리한 방법입니다. `__p___mb_cur_max` 함수는 Visual C++ 5.0 및 이전 버전과의 호환성을 위해 정의되었습니다.  
  
 내부 CRT 함수는 구현과 관련되어 있으며 각 릴리스 시 변경될 수 있습니다. 따라서 사용자 코드에는 사용하지 않는 것이 좋습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<ctype.h>, \<stdlib.h>|  
  
## <a name="see-also"></a>참고 항목  
 [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)
