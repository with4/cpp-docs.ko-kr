---
title: "_findclose | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _findclose
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
- _findclose
- findclose
dev_langs:
- C++
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b1f79ea7e5c39c4de7ba25699729864688ababf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="findclose"></a>_findclose
지정된 검색 핸들을 닫고 연결된 리소스를 해제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _findclose(   
   intptr_t handle   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `handle`  
 `_findfirst`에 대한 이전 호출에서 반환된 핸들을 검색합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `_findclose`가 0을 반환합니다. 그렇지 않으면-1을 반환 하 고 설정 `errno` 를 `ENOENT`, 나타내는 더 이상 일치 하는 파일을 찾을 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_findclose`|\<io.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [시스템 호출](../../c-runtime-library/system-calls.md)   
 [파일 이름 검색 함수](../../c-runtime-library/filename-search-functions.md)