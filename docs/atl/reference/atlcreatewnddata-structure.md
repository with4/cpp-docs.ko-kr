---
title: "_AtlCreateWndData 구조 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs: C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 99fc06e44f24b176482a6ff0b08ceed45b0f4f17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData 구조
이 구조 ATL에서 창 작업 코드에 클래스 인스턴스 데이터를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```  
  
## <a name="members"></a>멤버  
 **m_pThis**  
 **이** 창 프로시저에서 클래스 인스턴스에 대 한 액세스를 가져오는 데 사용 되는 포인터입니다.  
  
 `m_dwThreadID`  
 현재 클래스 인스턴스의 스레드 ID입니다.  
  
 **m_pNext**  
 다음에 대 한 포인터 `_AtlCreateWndData` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체](../../atl/reference/atl-structures.md)





