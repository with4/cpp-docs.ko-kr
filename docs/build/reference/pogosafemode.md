---
title: PogoSafeMode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: PogoSafeMode
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f40dad6feff9e49deeb495e8acbf2584dea3e41
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="pogosafemode"></a>PogoSafeMode
응용 프로그램 프로 파일링에 대 한 빠른 모드나 안전 모드를 사용할지 여부를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
PogoSafeMode  
```  
  
## <a name="remarks"></a>설명  
 프로필 기반 최적화 (PGO)의 두 가지 가능한 모드 단계에서 프로 파일링: 빠른 모드와 안전 모드입니다. 사용 하 여 프로 파일링 이면 고속 모드는 **INC** 데이터 카운터를 늘리려면 명령입니다. **INC** 명령은 빠르지만 스레드로부터 안전 하지 않습니다. 프로 파일링 하는 것은 안전 모드로 사용 하 여는 **LOCK INC** 데이터 카운터를 늘리려면 명령입니다. **LOCK INC** 명령으로 동일한 기능에는 **INC** 명령 개이고는 스레드로부터 안전 하지만 보다 느립니다는 **INC** 명령입니다.  
  
 기본적으로 빠른 모드로 작동 PGO 프로 파일링 합니다. `PogoSafeMode`안전 모드를 사용 하려는 경우에 필요 합니다.  
  
 PGO 안전 모드로 프로 파일링을 실행 하거나 사용 해야 환경 변수 `PogoSafeMode` 또는 링커 스위치 **-PogoSafeMode**시스템에 따라 합니다. X64 프로 파일링 수행 중인 경우 컴퓨터를 링커 스위치를 사용 해야 합니다. X86 프로 파일링 수행 중인 경우 컴퓨터를 먼저 정의 해야 환경 변수 값으로 최적화 프로세스를 시작 합니다.  
  
## <a name="example"></a>예  
  
```  
set PogoSafeMode=1  
```  
  
## <a name="see-also"></a>참고 항목  
 [프로필 기반 최적화에 대 한 환경 변수](../../build/reference/environment-variables-for-profile-guided-optimizations.md)   
 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)