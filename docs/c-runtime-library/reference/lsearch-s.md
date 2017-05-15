---
title: "_lsearch_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lsearch_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _lsearch_s
- lsearch_s
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
caps.latest.revision: 17
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
ms.openlocfilehash: 4969a12a821040c007a43248dc15927ee9f6ab40
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="lsearchs"></a>_lsearch_s
값에 대한 선형 검색을 수행합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_lsearch](../../c-runtime-library/reference/lsearch.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
void *_lsearch_s(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `key`  
 검색할 개체입니다.  
  
 `base`  
 검색할 배열의 기준에 대한 포인터입니다.  
  
 `num`  
 요소의 수입니다.  
  
 `size`  
 각 배열 요소의 크기(바이트)입니다.  
  
 `compare`  
 비교 루틴에 대한 포인터입니다. 두 번째 매개 변수는 검색할 키에 대한 포인터입니다. 세 번째 매개 변수는 키와 비교할 배열 요소에 대한 포인터입니다.  
  
 `context`  
 비교 함수에서 액세스할 수 있는 개체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `key`가 있으면 `_lsearch_s`는 `base`에서 `key`와 일치하는 배열의 요소에 대한 포인터를 반환합니다. `key`가 없으면 `_lsearch_s`는 배열의 끝에서 새로 추가된 항목에 대한 포인터를 반환합니다.  
  
 함수에 잘못된 매개 변수를 전달하면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `errno`는 `EINVAL`로 설정되고 함수는 `NULL`을 반환합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`key`|`base`|`compare`|`num`|`size`|`errno`|  
|-----------|------------|---------------|-----------|------------|-------------|  
|`NULL`|모두|모두|모두|모두|`EINVAL`|  
|모두|`NULL`|모두|!= 0|모두|`EINVAL`|  
|모두|모두|모두|any|0|`EINVAL`|  
|any|모두|`NULL`|an|모두|`EINVAL`|  
  
## <a name="remarks"></a>설명  
 `_lsearch_s` 함수는 각각 `width` 바이트인 `num` 요소의 배열에서 `key` 값에 대해 선형 검색을 수행합니다. `bsearch_s`와 달리 `_lsearch_s`에서는 배열을 정렬할 필요가 없습니다. `key`가 없는 경우 `_lsearch_s`는 배열의 끝에 추가하고 `num`을 늘립니다.  
  
 `compare` 함수는 두 배열 요소를 비교하여 해당 관계를 지정하는 값을 반환하는 사용자가 제공한 루틴에 대한 포인터입니다. 또한 `compare` 함수는 컨텍스트에 대한 포인터를 첫 번째 인수로 사용합니다. `_lsearch_s`는 검색 중에 `compare`를 한 번 이상 호출하며 각 호출에서 두 배열 요소에 대한 포인터를 전달합니다. `compare`는 요소를 비교한 다음 0이 아닌 값(요소가 다르다는 의미) 또는 0(요소가 동일하다는 의미)을 반환합니다.  
  
 `context` 포인터는 검색된 데이터 구조가 개체의 일부이며 `compare` 함수가 개체의 멤버에 액세스해야 하는 경우에 유용할 수 있습니다. 예를 들어 `compare` 함수는 void 포인터를 적절한 개체 형식으로 캐스팅하고 해당 개체의 멤버에 액세스할 수 있습니다. `context` 포인터를 추가하면 정적 변수를 사용하여 `compare` 함수에 데이터를 제공할 경우 발생하는 재진입 버그를 추가 컨텍스트로 방지할 수 있으므로 `_lsearch_s`의 보안이 강화됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_lsearch_s`|\<search.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)
