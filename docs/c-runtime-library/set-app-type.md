---
title: _set_app_type | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_app_type
apilocation: api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
dev_langs: C++
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 86078a8ff66eadc1cdd6b177ba074abfd1683345
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="setapptype"></a>_set_app_type
시작 시에 앱이 콘솔 앱인지 아니면 GUI 앱인지를 CRT에 알려 주는 데 사용되는 내부 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum _crt_app_type
{
    _crt_unknown_app,
    _crt_console_app,
    _crt_gui_app
} _crt_app_type;

void __cdecl _set_app_type(
    _crt_app_type appType
    ); 
```  
  
## <a name="parameters"></a>매개 변수  
 `appType`  
 응용 프로그램 형식을 나타내는 값입니다. 가능한 값은 다음과 같습니다.  
  
|값|설명|  
|----------------|-----------------|  
|_crt_unknown_app|알 수 없는 응용 프로그램 형식입니다.|  
|_crt_console_app|콘솔(명령줄) 응용 프로그램입니다.|  
|_crt_gui_app|GUI(Windows) 응용 프로그램입니다.|  
  
## <a name="remarks"></a>설명  
 일반적으로는 이 함수를 호출할 필요가 없습니다. 이 함수는 앱에서 `main`이 호출되기 전에 실행되는 C 런타임 시작 코드의 일부분입니다.
 
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|_set_app_type|process.h|

