---
title: "_CIlog10 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CIlog10
apilocation:
- msvcr100.dll
- msvcr120.dll
- msvcr80.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- CIlog10
- _CIlog10
dev_langs: C++
helpviewer_keywords:
- _CIlog10 intrinsic
- CIlog10 intrinsic
ms.assetid: 05d7fcaa-3cff-4cc5-8d44-015e7cacba24
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36d2d21a9c533cc569fbe72ee5213d542a4ad618
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cilog10"></a>_CIlog10
스택의 상위 값에 대해 `log10` 작업을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __cdecl _CIlog10();  
```  
  
## <a name="remarks"></a>설명  
 이 버전의 `log10` 함수는 컴파일러가 이해할 수 있는 특별한 호출 규칙을 가집니다. 이 함수는 복사본이 생성되지 않도록 하며 레지스터 할당을 돕기 때문에 실행 속도를 높입니다.  
  
 결과 값이 스택의 맨 위에 푸시됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** x86  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)