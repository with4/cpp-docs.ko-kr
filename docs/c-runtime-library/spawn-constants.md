---
title: "spawn 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _P_NOWAIT
- _P_OVERLAY
- _P_WAIT
- _P_DETACH
- _P_NOWAITO
dev_langs: C++
helpviewer_keywords:
- _P_OVERLAY constant
- P_DETACH constant
- P_OVERLAY constant
- P_NOWAIT constant
- _P_DETACH constant
- _P_NOWAIT constant
- _P_NOWAITO constant
- P_NOWAITO constant
- spawn constants
- P_WAIT constant
- _P_WAIT constant
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8f5f30cbf6598e4ac8d88652a6a842dcd6209273
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="spawn-constants"></a>spawn 상수
## <a name="syntax"></a>구문  
  
```  
#include <process.h>  
```  
  
## <a name="remarks"></a>설명  
 `mode` 인수는 생성 작업 전과 해당 작업이 수행되는 중에 호출 프로세스에 의해 수행되는 작업을 결정합니다. `mode`에 대해 다음 값을 사용할 수 있습니다.  
  
|상수|의미|  
|--------------|-------------|  
|`_P_OVERLAY`|호출 프로세스를 제거하며 호출 프로세스를 새로운 프로세스와 겹쳐서 표시합니다(`_exec` 호출과 효과가 같음).|  
|`_P_WAIT`|새로운 프로세스의 실행이 완료될 때까지 호출 스레드를 일시 중단합니다(동기적 `_spawn`).|  
|`_P_NOWAIT`, `_P_NOWAITO`|호출 프로세스를 계속 새로운 프로세스와 동시에 실행합니다(비동기적 `_spawn`).|  
|`_P_DETACH`|호출 프로세스를 계속 실행합니다. 새로운 프로세스는 콘솔 또는 키보드에 대한 액세스 없이 백그라운드에서 실행됩니다. 새로운 프로세스에 대해 `_cwait`를 호출하는 작업은 실패합니다. 이는 비동기적 `_spawn`입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [_spawn, _wspawn 함수](../c-runtime-library/spawn-wspawn-functions.md)   
 [전역 상수](../c-runtime-library/global-constants.md)