---
title: "ATL 연결 지점 예제 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 518976381209fe774f32b286e42a9840159a9404
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="atl-connection-point-example"></a>ATL 연결 지점 예제
지 원하는 개체를 보여 주는이 예제 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 보내기 인터페이스로:  
  
 [!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]  
  
 지정 하는 경우 `IPropertyNotifySink` 송신 인터페이스를 사용 하 여 클래스 [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) 대신 `IConnectionPointImpl`합니다. 예:  
  
 [!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]  
  
## <a name="see-also"></a>참고 항목  
 [연결 지점](../atl/atl-connection-points.md)

