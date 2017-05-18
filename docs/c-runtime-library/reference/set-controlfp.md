---
title: _set_controlfp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_controlfp
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_controlfp
- _set_controlfp
dev_langs:
- C++
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: f7cf06b52624178a3d5bbe5907289eab7f57cbb5
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="setcontrolfp"></a>_set_controlfp
부동 소수점 제어 단어를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __cdecl _set_controlfp(  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `newControl`  
 새 제어 단어 비트 값입니다.  
  
 `mask`  
 설정할 새 제어 단어 비트의 마스크입니다.  
  
## <a name="return-value"></a>반환 값  
 없음  
  
## <a name="remarks"></a>설명  
 `_set_controlfp`는 `_control87`과 유사하지만 부동 소수점 제어 단어를 `newControl`로 설정하기만 합니다. 값의 비트는 부동 소수점 제어 상태를 나타냅니다. 부동 소수점 제어 상태를 사용하면 프로그램이 부동 소수점 연산 패키지에서 정밀도, 반올림 및 무한대 모드를 변경할 수 있습니다. `_set_controlfp`를 사용하여 부동 소수점 예외를 마스킹 또는 마스킹 해제할 수도 있습니다. 자세한 내용은 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)를 참조하세요.  
  
 로 컴파일하는 경우이 함수는 사용 되지 않습니다 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 공용 언어 런타임은 기본 부동 소수점 정밀도만 지원 하기 때문에 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|호환성|  
|-------------|---------------------|-------------------|  
|`_set_controlfp`|\<float.h>|x86 프로세서만|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)
