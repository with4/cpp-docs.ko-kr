---
title: __set_app_type | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __set_app_type
- _set_app_type
apilocation:
- msvcr90.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __set_app_type
dev_langs:
- C++
helpviewer_keywords:
- __set_app_type
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 854873987cd83b89efc5c9006c1e091023c91226
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389064"
---
# <a name="setapptype"></a>__set_app_type
현재 응용 프로그램 형식을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void __set_app_type (  
   int at  
   )  
```  
  
#### <a name="parameters"></a>매개 변수  
 `at`  
 응용 프로그램 형식을 나타내는 값입니다. 가능한 값은 다음과 같습니다.  
  
|값|설명|  
|-----------|-----------------|  
|_UNKNOWN_APP|알 수 없는 응용 프로그램 형식입니다.|  
|_CONSOLE_APP|콘솔(명령줄) 응용 프로그램입니다.|  
|_GUI_APP|GUI(Windows) 응용 프로그램입니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|__set_app_type|internal.h|