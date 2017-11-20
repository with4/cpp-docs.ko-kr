---
title: "_inp, _inpw, _inpd | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _inp
- _inpw
- _inpd
apilocation:
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- inpd
- _inp
- _inpw
- _inpd
dev_langs: C++
helpviewer_keywords:
- inp function
- inpw function
- ports, I/O routines
- inpd function
- _inp function
- _inpd function
- I/O [CRT], port
- _inpw function
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 983efc1f3341ca334415e8cdd37f96f12fbb3e11
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="inp-inpw-inpd"></a>_inp, _inpw, _inpd
포트에서의 입력으로, 바이트(`_inp`), 워드(`_inpw`), 또는 2배 워드(`_inpd`)입니다.  
  
> [!IMPORTANT]
>  이러한 함수는 사용되지 않습니다. Visual Studio 2015부터 CRT에서 사용할 수 없습니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
int _inp(   
   unsigned short port   
);  
unsigned short _inpw(   
   unsigned short port   
);  
unsigned long _inpd(   
   unsigned short port   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `port`  
 I/O 포트 번호입니다.  
  
## <a name="return-value"></a>반환 값  
 함수가 `port`에서 바이트, 워드 또는 2배 워드를 반환합니다. 반환되는 오류가 없습니다.  
  
## <a name="remarks"></a>설명  
 `_inp`, `_inpw`및 `_inpd` 함수는 바이트, 워드 및 2배 워드를 각각 지정된 된 입력 포트로부터 읽습니다. 입력 값은 0 - 65,535 범위의 부호 없는 정수(Short)입니다.  
  
 이러한 함수는 I/O 포트에서 직접 읽기 때문에 Windows NT, Windows 2000, Windows XP 및 Windows Server 2003의 사용자 코드에서 사용할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_inp`|\<conio.h>|  
|`_inpw`|\<conio.h>|  
|`_inpd`|\<conio.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [콘솔 및 포트 I/O](../c-runtime-library/console-and-port-i-o.md)   
 [_outp, _outpw, _outpd](../c-runtime-library/outp-outpw-outpd.md)