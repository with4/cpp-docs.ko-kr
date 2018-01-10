---
title: _purecall | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _purecall
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- purecall
- _purecall
dev_langs: C++
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ef2670188374dc7af5fa34c76df73c3d261efc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="purecall"></a>_purecall
기본 순수 가상 함수 호출 오류 처리기입니다. 순수 가상 구성원 함수를 호출하면 컴파일러가 이 함수를 호출하는 코드를 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
extern "C" int __cdecl _purecall();  
```  
  
## <a name="remarks"></a>설명  
 `_purecall` 함수는 Microsoft Visual C++ 컴파일러의 Microsoft 관련 구현 세부 정보입니다. 이 함수는 코드에서 직접 호출할 수는 없으며 공용 헤더 선언을 포함하지 않습니다. 하지만 C 런타임 라이브러리의 공용 내보내기이므로 이 문서에 포함되어 있습니다.  
  
 순수 가상 함수에 대한 호출은 구현이 없으므로 오류입니다. 순수 가상 함수를 호출하면 컴파일러는 `_purecall` 오류 처리기 함수를 호출하는 코드를 생성합니다. 기본적으로 `_purecall`은 프로그램을 종료합니다. 종료 전에 `_purecall` 함수는 `_purecall_handler` 함수(프로세스에 대해 설정된 경우)를 호출합니다. 순수 가상 함수 호출을 위해 고유한 오류 처리기 함수를 설치하여 디버깅 또는 보고용으로 이러한 호출을 catch할 수 있습니다. 고유한 오류 처리기를 사용하려면 `_purecall_handler` 서명이 포함된 함수를 만든 다음 [_set_purecall_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)를 사용하여 해당 함수를 현재 처리기로 지정합니다.  
  
## <a name="requirements"></a>요구 사항  
 `_purecall` 함수에는 헤더 선언이 없습니다. `_purecall_handler` typedef는 \<stdlib.h>에서 정의됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_get_purecall_handler, _set_purecall_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)