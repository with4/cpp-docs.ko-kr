---
title: "오류 처리(CRT) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.errors
dev_langs: C++
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 176e744423441711715cc32b355278db20491e8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="error-handling-crt"></a>오류 처리(CRT)
이러한 루틴을 사용하여 프로그램 오류를 처리합니다.  
  
### <a name="error-handling-routines"></a>오류 처리 루틴  
  
|루틴|기능|  
|-------------|---------|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 매크로|런타임 라이브러리의 디버그 및 릴리스 버전 모두에서 사용할 수 있는 프로그래밍 논리 오류 테스트입니다.|  
|[_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로|`assert`와 유사하지만 런타임 라이브러리의 디버그 버전에서만 사용할 수 있습니다.|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|오류 표시기를 다시 설정합니다. `rewind`를 호출하거나 스트림을 닫으면 오류 표시기도 다시 설정됩니다.|  
|[_eof](../c-runtime-library/reference/eof.md)|하위 수준 I/O에서 파일 끝을 검사합니다.|  
|[feof](../c-runtime-library/reference/feof.md)|파일 끝에 대한 테스트입니다. `_read`가 0을 반환할 때 파일 끝도 표시됩니다.|  
|[ferror](../c-runtime-library/reference/ferror.md)|스트림 I/O 오류에 대한 테스트입니다.|  
|[_RPT, _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) 매크로|`printf`와 유사하지만 런타임 라이브러리의 디버그 버전에서만 사용할 수 있는 보고서를 생성합니다.|  
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|C 런타임이 프로그램을 종료할 오류에 대한 오류 메시지를 기록하는 기본 위치가 아닌 위치를 결정하도록 `__error_mode`를 수정합니다.|  
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|순수 가상 함수 호출에 필요한 처리기를 설정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)