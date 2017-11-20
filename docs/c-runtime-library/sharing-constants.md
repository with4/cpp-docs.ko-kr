---
title: "상수 공유 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
dev_langs: C++
helpviewer_keywords:
- _SH_DENYRW constant
- SH_DENYRD constant
- _SH_COMPAT constant
- _SH_DENYRD constant
- SH_DENYRW constant
- sharing constants
- SH_DENYNO constant
- _SH_DENYWR constant
- SH_DENYWR constant
- _SH_DENYNO constant
- SH_COMPAT constant
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 941cf63dd7a5eb761881e7068fa141d5e6b87a33
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="sharing-constants"></a>상수 공유
파일 공유 모드에 대한 상수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#include <share.h>  
  
```  
  
## <a name="remarks"></a>설명  
 *shflag* 인수는 공유 모드를 결정하며 하나 이상의 상수로 구성됩니다. *oflag* 인수([파일 상수](../c-runtime-library/file-constants.md) 참조)와 함께 사용할 수 있습니다.  
  
 다음 표에는 상수 목록과 해당 의미가 나열되어 있습니다.  
  
|상수|의미|  
|--------------|-------------|  
|`_SH_DENYRW`|파일에 대한 읽기 및 쓰기 액세스 거부|  
|`_SH_DENYWR`|파일에 대한 쓰기 액세스 거부|  
|`_SH_DENYRD`|파일에 대한 읽기 액세스 거부|  
|`_SH_DENYNO`|읽기 및 쓰기 액세스 허용|  
|`_SH_SECURE`|보안 모드 설정(공유 읽기, 전용 쓰기 액세스)|  
  
## <a name="see-also"></a>참고 항목  
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [전역 상수](../c-runtime-library/global-constants.md)