---
title: "ATL 연결 지점 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CFirePropNotifyEvent class, connection point classes
- connection points [C++], ATL classes
- ATL, connection points
- CComDynamicUnkArray class, connection point classes
- CFirePropNotifyEvent class
- CComUnkArray class, connection point classes
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9845fdffdd951809ee7127c5fec86097a6219354
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-connection-point-classes"></a>ATL 연결 지점 클래스
ATL 연결 지점 지원 하기 위해 다음 클래스를 사용:  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) 연결 지점을 구현 합니다. 나타내는 보내기 인터페이스의 IID는 템플릿 매개 변수로 전달 됩니다.  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) 연결 지점 컨테이너를 구현 하 고 목록을 관리 `IConnectionPointImpl` 개체입니다.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) 나타내는 연결 지점을 구현 하는 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 인터페이스입니다.  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) 임의 개수의 연결 지점과 싱크 간에 연결을 관리 합니다.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) 미리 정의 된 다양 한 템플릿 매개 변수로 지정 된 연결을 관리 합니다.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) 개체 속성 변경 되거나 변경 되려고 하는 클라이언트의 싱크를에 알립니다.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) ATL COM 개체에 대 한 연결점에 대 한 지원을 제공 합니다. 이러한 연결점은 COM 개체에서 제공 되는 이벤트 싱크 맵이 매핑됩니다.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 하려면 적절 한 처리기 함수에 경로 이벤트 클래스에서 이벤트 싱크 맵와 함께 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연결 지점](../atl/atl-connection-points.md)

