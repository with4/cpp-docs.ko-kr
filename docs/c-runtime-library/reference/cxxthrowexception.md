---
title: "_CxxThrowException | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CxxThrowException
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
apitype: DLLExport
f1_keywords:
- CxxThrowException
- _CxxThrowException
dev_langs:
- C++
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5cfe894dc20e77bf34067c16fddd74432c522bda
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="cxxthrowexception"></a>_CxxThrowException
예외 레코드를 작성하고 런타임 환경을 호출하여 예외 처리를 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
extern "C" void __stdcall _CxxThrowException(  
   void* pExceptionObject  
   _ThrowInfo* pThrowInfo  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `pExceptionObject`  
 예외를 생성한 개체입니다.  
  
 [in] `pThrowInfo`  
 예외를 처리하는 데 필요한 정보입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 컴파일러에서 예외를 처리하는 데 사용하는 컴파일러 전용 파일에 포함됩니다. 코드에서 직접 메서드를 호출하면 안 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **소스:** Throw.cpp  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)
