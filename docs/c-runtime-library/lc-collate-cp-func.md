---
title: ___lc_collate_cp_func | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ___lc_collate_cp_func
apilocation:
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- ___lc_collate_cp_func
dev_langs:
- C++
helpviewer_keywords:
- ___lc_collate_cp_func
ms.assetid: 46ccc084-7ac9-4e5d-9138-e12cb5845615
caps.latest.revision: 4
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
ms.openlocfilehash: cb388e675a4caf966555add2c321eb780e89251d
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="lccollatecpfunc"></a>___lc_collate_cp_func
내부 CRT 함수입니다. 스레드의 현재 데이터 정렬 코드 페이지를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## <a name="return-value"></a>반환 값  
 스레드의 현재 데이터 정렬 코드 페이지입니다.  
  
## <a name="remarks"></a>설명  
 `___lc_collate_cp_func`는 다른 CRT 함수가 CRT 데이터의 스레드 로컬 저장소에서 현재 데이터 정렬 코드 페이지를 가져오기 위해 사용하는 내부 CRT 함수입니다. [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) 함수를 사용하면 이 정보를 사용할 수 있습니다.  
  
 내부 CRT 함수는 구현과 관련되어 있으며 각 릴리스 시 변경될 수 있습니다. 따라서 사용자 코드에는 사용하지 않는 것이 좋습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`___lc_collate_cp_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>참고 항목  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)
