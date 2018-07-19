---
title: 개체 상태 매크로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3657e7076bf67a5a3870d7d127cc150f976ecde
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883660"
---
# <a name="object-status-macros"></a>개체 상태 매크로
이 매크로 ActiveX 컨트롤에 속하는 플래그를 설정 합니다.  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|ATL ActiveX 컨트롤의 OLEMISC 플래그를 설정 하는 데 사용 합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  

##  <a name="declare_olemisc_status"></a>  DECLARE_OLEMISC_STATUS  
 ATL ActiveX 컨트롤의 OLEMISC 플래그를 설정 하는 데 사용 합니다.  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>매개 변수  
 *miscstatus*  
 해당 되는 모든 OLEMISC 플래그입니다.  
  
### <a name="remarks"></a>설명  
 이 매크로 ActiveX 컨트롤에 대 한 OLEMISC 플래그를 설정 하는 데 사용 됩니다. 가리킵니다 [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) 대 한 자세한 내용은 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)
