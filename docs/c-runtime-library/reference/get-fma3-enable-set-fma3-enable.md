---
title: _get_FMA3_enable, _set_FMA3_enable | Microsoft Docs
ms.custom: 
ms.date: 6/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_FMA3_enable
- _set_FMA3_enable
apilocation:
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
- math/_get_FMA3_enable
- math/_set_FMA3_enable
dev_langs: C++
helpviewer_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
ms.assetid: 4c1dc4bc-e86b-451b-9211-5a2ba6c98ee4
caps.latest.revision: "1"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0a2810a8d6602efb689896cfe35cf61338eb24f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="getfma3enable-setfma3enable"></a>_get_FMA3_enable, _set_FMA3_enable
초월수 수식 부동 소수점 라이브러리 함수에서에서 사용 하 여 FMA3 지침 컴파일된 코드 x64 지정 하는 플래그를 가져오거나 설정 합니다. 플랫폼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _set_FMA3_enable(int flag);
int _get_FMA3_enable();
```  
  
### <a name="parameters"></a>매개 변수
*플래그*  
FMA3 구현의 x64 초월수 수식 부동 소수점 라이브러리 함수를 사용 하도록 설정 하려면 1로 설정, 플랫폼 또는 FMA3 지침을 사용 하지 않는 구현을 사용 하려면 0으로 합니다.
  
## <a name="return-value"></a>반환 값  
초월수 수학 부동 소수점 라이브러리 함수의 FMA3 구현을 사용 하는 경우는 0이 아닌 값입니다. 그렇지 않으면 0입니다.  
  
## <a name="remarks"></a>설명  
사용 하 여는 `_set_FMA3_enable` 함수를 사용 하도록 설정 하거나 FMA3 지침 CRT 라이브러리에서 수학 초월수 부동 소수점 함수에 사용 하지 않도록 설정 합니다. 반환 값 변경 후 사용 구현이 반영합니다. CPU FMA3 지침을 지원 하지 않으면이 함수는 라이브러리에 사용할 수 없습니다 및 반환 값은 0입니다. 사용 하 여 `_get_FMA3_enable` 라이브러리의 현재 상태를 가져옵니다. 기본적으로 x64 플랫폼에서 CRT 시작 코드가 여부를 검색 CPU FMA3 지침 지원 및 사용 하면 라이브러리에서 FMA3 구현을 사용 하지 않도록 설정 합니다.
  
FMA3 구현은 서로 다른 알고리즘을 사용 하므로 계산의 결과에서 약간의 차이가 FMA3 구현을 설정 또는 해제, 때나 않거나 FMA3를 지원 하지 않는 컴퓨터 간의 observable 수 있습니다. 자세한 내용은 참조 [부동 소수점 마이그레이션 문제](../../porting/floating-point-migration-issues.md)합니다.

## <a name="requirements"></a>요구 사항  
  
`_set_FMA3_enable` 및 `_get_FMA3_enable` 함수에에서만 제공 되는 X64 버전의 CRT 합니다.  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_set_FMA3_enable` <br /><br /> `_get_FMA3_enable`| C: \<math.h><br /><br /> C + +: \<cmath > 또는 \<math.h >|  
  
`_set_FMA3_enable` 및 `_get_FMA3_enable` 함수는 Microsoft 전용입니다. 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)
[부동 소수점 마이그레이션 문제](../../porting/floating-point-migration-issues.md)  