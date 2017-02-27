---
title: "_heapadd | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _heapadd
apilocation:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- heapadd
- _heapadd
dev_langs:
- C++
helpviewer_keywords:
- _heapadd function
- memory, adding to heaps
- heaps, adding memory
- heapadd function
ms.assetid: 4d691fe2-2763-49f4-afb1-62738b7cd3ff
caps.latest.revision: 11
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4d2f5694ad2f06bf78307783d8f24c34bb0849df

---
# <a name="heapadd"></a>_heapadd
힙에 메모리를 추가합니다.  
  
> [!IMPORTANT]
>  이 함수는 사용되지 않습니다. Visual Studio 2015부터 CRT에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _heapadd(   
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `memblock`  
 힙 메모리에 대한 포인터입니다.  
  
 `size`  
 추가할 메모리 크기(바이트)입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `_heapadd` 에서 0을 반환합니다. 그렇지 않으면 함수에서 –1을 반환하고 `errno` 를 `ENOSYS`로 설정합니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 Visual C++ 버전 4.0부터 새 디버깅 기능을 지원하기 위해 기본 힙 구조가 C 런타임 라이브러리로 이동되었습니다. 따라서 `_heapadd` 는 Win32 API를 기반으로 하는 플랫폼에서 더 이상 지원되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_heapadd`|\<malloc.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../c-runtime-library/memory-allocation.md)   
 [free](../c-runtime-library/reference/free.md)   
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../c-runtime-library/reference/heapmin.md)   
 [_heapset](../c-runtime-library/heapset.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [malloc](../c-runtime-library/reference/malloc.md)   
 [realloc](../c-runtime-library/reference/realloc.md)


<!--HONumber=Feb17_HO4-->


