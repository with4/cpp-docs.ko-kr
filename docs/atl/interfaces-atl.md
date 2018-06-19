---
title: 인터페이스 (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0db5a79f187cb0fe320bf67aace751a5d4c537d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359316"
---
# <a name="interfaces-atl"></a>인터페이스 (ATL)
인터페이스는 개체는 외부 기능을 노출 하는 방법입니다. COM 인터페이스에는 개체에 의해 구현 되는 함수 (예: c + + vtable) 포인터의 테이블입니다. 테이블 인터페이스를 나타내고 가리키는 함수는 해당 인터페이스의 메서드입니다. 개체는 선택한 만큼의 인터페이스를 노출할 수 있습니다.  
  
 기본 COM 인터페이스를 기반으로 하는 각 인터페이스 [IUnknown](../atl/iunknown.md)합니다. 메서드 **IUnknown** 개체에서 노출 하는 다른 인터페이스를 탐색할 수 있습니다.  
  
 또한 각 인터페이스에는 고유한 ID IID (인터페이스) 제공 됩니다. 이 고유성을 사용 하면 인터페이스 버전 관리를 지원 하기가 쉬워졌습니다. 인터페이스의 새 버전을 새 IID 가진 새로운 인터페이스 하기만 합니다.  
  
> [!NOTE]
>  표준 COM 및 OLE 인터페이스에 대 한 Iid는 미리 정의 되어 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [COM 개체 및 인터페이스](http://msdn.microsoft.com/library/windows/desktop/ms690343)

