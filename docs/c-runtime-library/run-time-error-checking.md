---
title: "런타임 오류 검사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: eb9db9ea42d50faa6e7a693c95795036e650a760
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="run-time-error-checking"></a>런타임 오류 검사
C 런타임 라이브러리에는 RTC(런타임 오류 검사)를 지원하는 함수가 포함되어 있습니다. 런타임 오류 검사를 사용하면 특정 런타임 오류 종류가 보고되도록 프로그램을 빌드할 수 있습니다. 오류가 보고되는 방법과 보고되는 오류 종류를 지정합니다. 자세한 내용은 [런타임 오류 검사](http://msdn.microsoft.com/Library/dc7b2f1e-5ff6-42e0-89b3-dc9dead83ee1)를 참조하세요.  
  
 프로그램에서 런타임 오류 검사가 수행되는 방법을 사용자 지정하려면 다음 함수를 사용하십시오.  
  
### <a name="run-time-error-checking-functions"></a>런타임 오류 검사 함수  
  
|함수|기능|  
|--------------|---------|  
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|런타임 오류 검사 형식에 대한 간단한 설명을 반환합니다.|  
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|런타임 오류 검사에서 발견될 수 있는 총 오류 수를 반환합니다.|  
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|런타임 오류 검사 보고를 위한 처리기로 함수를 지정합니다.|  
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|런타임 오류 검사에서 발견된 오류를 형식에 연결합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)   
 [/RTC(런타임 오류 검사)](../build/reference/rtc-run-time-error-checks.md)   
 [runtime_checks](../preprocessor/runtime-checks.md)   
 [RTC 샘플](http://msdn.microsoft.com/en-us/b3415b09-f6fd-43dc-8c02-9a910bc2574e)   
 [디버그 루틴](../c-runtime-library/debug-routines.md)
