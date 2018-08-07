---
title: _AtlCreateWndData 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf51197750e9595570a7b011c179c2ed4c7902c3
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880010"
---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData 구조체
이 구조 ATL에서 창 작업 코드에서 클래스 인스턴스 데이터를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```  
  
## <a name="members"></a>멤버  
 `m_pThis`  
 합니다 **이** 창 프로시저에서 클래스 인스턴스에 대 한 액세스를 가져오는 데 대 한 포인터입니다.  
  
 `m_dwThreadID`  
 현재 클래스 인스턴스의 스레드 ID입니다.  
  
 `m_pNext`  
 다음에 대 한 포인터 `_AtlCreateWndData` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
## <a name="see-also"></a>참고 항목  
 [클래스 및 구조체](../../atl/reference/atl-classes.md)





