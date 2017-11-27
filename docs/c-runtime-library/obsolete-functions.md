---
title: "사용되지 않는 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_wctype
- _loaddll
- _unloaddll
- _getdllprocaddr
- _seterrormode
- _beep
- _sleep
- _getsystime
- corecrt_wctype/is_wctype
- process/_loaddll
- process/_unloaddll
- process/_getdllprocaddr
- stdlib/_seterrormode
- stdlib/_beep
- stdlib/_sleep
- time/_getsystime
- time/_setsystime
dev_langs: C++
helpviewer_keywords:
- obsolete functions
- _beep function
- _sleep function
- _seterrormode function
ms.assetid: 8e14c2d4-1481-4240-8586-47eb43db02b0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8a8811703234f2c4e23dab6ad2b99b1aae316c04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="obsolete-functions"></a>사용되지 않는 함수
특정 라이브러리 함수는 더 이상 사용되지 않으며 최신의 동등한 함수를 포함합니다. 이러한 함수는 업데이트된 버전으로 변경하는 것이 좋습니다. 사용되지 않는 기타 함수가 CRT에서 제거되었습니다. 이 항목에서는 사용되지 않는 함수 및 특정 버전의 Visual Studio에서 제거된 함수 목록을 보여 줍니다.  
  
## <a name="deprecated-as-obsolete-in-visual-studio-2015"></a>Visual Studio 2015에서 더 이상 사용되지 않음  
  
|사용되지 않는 함수|대체|  
|-----------------------|-----------------|  
|`is_wctype`|[iswctype](../c-runtime-library/reference/isctype-iswctype-isctype-l-iswctype-l.md)|  
|`_loaddll`|[LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187), [LoadLibraryEx](http://go.microsoft.com/fwlink/p/?LinkID=236091)또는 [LoadPackagedLibrary](https://msdn.microsoft.com/library/windows/desktop/hh447159\(v=vs.85\).aspx)|  
|`_unloaddll`|[FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)|  
|`_getdllprocaddr`|[GetProcAddress](../build/getprocaddress.md)|  
|`_seterrormode`|[SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkID=255242)|  
|`_beep`|[Beep](https://msdn.microsoft.com/library/windows/desktop/ms679277\(v=vs.85\).aspx)|  
|`_sleep`|[Sleep](https://msdn.microsoft.com/library/windows/desktop/ms686298\(v=vs.85\).aspx)|  
|`_getsystime`|[GetLocalTime](https://msdn.microsoft.com/library/windows/desktop/ms724338\(v=vs.85\).aspx)|  
|`_setsystime`|[SetLocalTime](https://msdn.microsoft.com/library/windows/desktop/ms724936\(v=vs.85\).aspx)|  
  
## <a name="removed-from-the-crt-in-visual-studio-2015"></a>Visual Studio 2015의 CRT에서 제거됨  
  
|사용되지 않는 함수|대체|  
|-----------------------|-----------------|  
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md)|[_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|  
|[gets, _getws](../c-runtime-library/gets-getws.md)|[gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|  
|[_get_output_format](../c-runtime-library/get-output-format.md)|없음|  
|[_heapadd](../c-runtime-library/heapadd.md)|없음|  
|[_heapset](../c-runtime-library/heapset.md)|없음|  
|[inp, inpw](../c-runtime-library/inp-inpw.md)|없음|  
|[_inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)|없음|  
|[outp, outpw](../c-runtime-library/outp-outpw.md)|없음|  
|[_outp, _outpw, _outpd](../c-runtime-library/outp-outpw-outpd.md)|없음|  
|[_set_output_format](../c-runtime-library/set-output-format.md)|없음|  
  
## <a name="removed-from-the-crt-in-earlier-versions-of-visual-studio"></a>이전 Visual Studio 버전의 CRT에서 제거됨  
 [_lock](../c-runtime-library/lock.md)  
  
 [_unlock](../c-runtime-library/unlock.md)