---
title: "ATL 연결 지점 예제 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf59a8093568b96b5f2173d91ba52a6bfeb103b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-connection-point-example"></a>ATL 연결 지점 예제
지 원하는 개체를 보여 주는이 예제 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 보내기 인터페이스로:  
  
 [!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]  
  
 지정 하는 경우 `IPropertyNotifySink` 송신 인터페이스를 사용 하 여 클래스 [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) 대신 `IConnectionPointImpl`합니다. 예:  
  
 [!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]  
  
## <a name="see-also"></a>참고 항목  
 [연결 지점](../atl/atl-connection-points.md)

