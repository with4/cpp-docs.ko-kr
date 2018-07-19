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
ms.openlocfilehash: b7becd9e27294c81ce6144d08c79cfac52636fbf
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848267"
---
# <a name="interfaces-atl"></a>인터페이스 (ATL)
인터페이스에 개체 외부 세계에 해당 기능을 노출 하는 방법입니다. COM의 인터페이스 (예: c + + vtable)를 구현 하는 함수 포인터의 테이블입니다. 테이블 인터페이스를 나타내며 가리키는 함수는 해당 인터페이스의 메서드. 개체는 선택한 만큼의 인터페이스를 노출할 수 있습니다.  
  
 각 인터페이스에 기본 COM 인터페이스가 기반 [IUnknown](../atl/iunknown.md)합니다. 메서드 `IUnknown` 개체에 의해 노출 되는 다른 인터페이스에 대 한 탐색을 허용 합니다.  
  
 또한 각 인터페이스에는 고유한 인터페이스 ID (IID)를 지정 됩니다. 이 고유성 쉽게 인터페이스 버전 관리를 지원 합니다. 인터페이스의 새 버전은 새 IID 사용 하 여 새 인터페이스 하기만 하면 됩니다.  
  
> [!NOTE]
>  표준 COM 및 OLE 인터페이스에 대 한 Iid 미리 정의 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [COM 개체 및 인터페이스](http://msdn.microsoft.com/library/windows/desktop/ms690343)

