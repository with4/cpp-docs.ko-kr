---
title: COM 맵 매크로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00c15bf8567456254c8a338ed395a726fcbe8c9b
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879311"
---
# <a name="com-map-macros"></a>COM 맵 매크로
이러한 매크로 COM 인터페이스 맵을 정의 합니다.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|COM 인터페이스 맵 항목의 시작을 표시 합니다.|  
|[END_COM_MAP](#end_com_map)|COM 인터페이스 맵 항목의 끝을 표시 합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
   
##  <a name="begin_com_map"></a>  BEGIN_COM_MAP  
 COM 개체를 통해 클라이언트에 대 한 인터페이스를 노출 하는 메커니즘은 `QueryInterface`합니다.  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 인터페이스에 노출 하는 클래스 개체의 이름입니다.  
  
### <a name="remarks"></a>설명  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) 만 COM 맵에 인터페이스에 대 한 포인터를 반환 합니다. 인터페이스 맵에 BEGIN_COM_MAP 매크로 사용 하 여 시작, 사용 하 여 인터페이스의 각 항목을 추가 합니다 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) 매크로 또는 해당 변형 중 하나 지도를 완료 합니다 [END_COM_MAP](#end_com_map) 매크로입니다.  

  
### <a name="example"></a>예  
 ATL [호출기](../../visual-cpp-samples.md) 샘플:  
  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  

  
##  <a name="end_com_map"></a>  END_COM_MAP  
 COM 인터페이스 맵의 정의 종료합니다.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)   
 [COM 맵 전역 함수](../../atl/reference/com-map-global-functions.md)
