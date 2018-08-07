---
title: 'Mutex:: lock 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 61d95072-b690-441e-a080-0bf94a733141
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c96ef497331fecf8125c51a7b8bd669ec758927
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603526"
---
# <a name="mutexlock-method"></a>Mutex::Lock 메서드
현재 개체를 때까지 대기 또는 **뮤텍스** 지정된 된 핸들, 뮤텍스 또는 지정 된 시간 제한 간격이 경과 하는 릴리스를 사용 하 여 연결 된 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *시간 (밀리초)*  
 제한 시간 간격(밀리초)입니다. 기본값은 INFINITE으로, 무제한 대기합니다.  
  
 *h*  
 핸들을 **뮤텍스** 개체입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>참고 항목
 [Mutex 클래스](../windows/mutex-class1.md)