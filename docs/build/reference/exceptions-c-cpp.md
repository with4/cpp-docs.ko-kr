---
title: 예외 (C/c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
dev_langs:
- C++
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 819f9424b2439cc49517afe54d62a8ed4f06d22d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="exceptions-cc"></a>예외(C/C++)
오류가 발생 한 경우 두 개의 예외 코드를 늘릴 수 있습니다.  
  
-   에 대 한는 **LoadLibrary** 실패  
  
-   에 대 한는 **GetProcAddress** 실패  
  
 예외 정보는 다음과 같습니다.  
  
```  
//  
// Exception information  
//  
#define FACILITY_VISUALCPP  ((LONG)0x6d)  
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)  
```  
  
 발생 한 예외 코드는 표준 VcppException (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) 및 (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND) VcppException 값입니다. 예외에 대 한 포인터를 전달 된 **DelayLoadInfo** 하 여 검색할 수 있는 LPDWORD 값에는 구조 **GetExceptionInformation** 에 [EXCEPTION_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082) 구조 [0] ExceptionInformation 필드입니다.  
  
 또한 grAttrs 필드에 잘못 된 비트가 설정 되는 경우 예외 ERROR_INVALID_PARAMETER throw 됩니다. 이 예외는, 예 모든 용도 치명적입니다.  
  
 참조 [구조체 및 상수 정의](../../build/reference/structure-and-constant-definitions.md) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [오류 처리 및 알림](../../build/reference/error-handling-and-notification.md)