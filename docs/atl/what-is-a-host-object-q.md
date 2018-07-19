---
title: 호스트 개체는 무엇입니까? (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- host objects
ms.assetid: 4f8da992-b27e-45e8-b5e0-c8b1dcae4fac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d197f02949f6eaaeee50b428338684135d1db27
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357736"
---
# <a name="what-is-a-host-object"></a>호스트 개체는 무엇입니까?
호스트 개체는 특정 창에 대 한 ATL에서 제공 하는 ActiveX 컨트롤 컨테이너를 나타내는 COM 개체. 호스트 개체 하위 클래스 컨테이너 창 컨트롤에 대 한 메시지를 반영할 수는 컨트롤을 사용 하는 데 필요한 컨테이너 인터페이스를 제공 하 고 노출 하는 [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) 및 [ IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) 인터페이스 컨트롤의 환경을 구성할 수 있도록 합니다.  
  
 컨테이너의 앰비언트 속성을 설정 하는 호스트 개체를 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)

