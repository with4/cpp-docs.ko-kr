---
title: COM 특성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d37ba5c690b61840ad261e6ab966d0cc74c07c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861388"
---
# <a name="com-attributes"></a>COM 특성
COM 특성에는 COM 개발 및.NET Framework 공용 언어 런타임 개발의 다양 한 영역을 지 원하는 코드를 삽입 합니다. 이러한 영역 범위에서 사용자 지정 인터페이스 구현 및 인터페이스의 지원 스톡 속성, 메서드 및 이벤트를 지 원하는입니다. 또한 복합 및 ActiveX 컨트롤 구현을 위한 지원은 찾을 수 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|다른 컨트롤에서 컨트롤을 집계할 수 있도록 나타냅니다.|  
|[aggregates](../windows/aggregates.md)|컨트롤은 대상 클래스 집계 됨을 나타냅니다.|  
|[coclass](../windows/coclass.md)|COM 인터페이스를 구현할 수 있는 COM 개체를 만듭니다.|  
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|Com에 인터페이스 항목을 추가 합니다.|  
|[implements_category](../windows/implements-category.md)|클래스에 대해 구현 된 구성 요소 범주를 지정합니다.|  
|[progid](../windows/progid.md)|컨트롤의 ProgID를 정의합니다.|  
|[rdx](../windows/rdx.md)|만들거나 레지스트리 키를 수정 합니다.|  
|[registration_script](../windows/registration-script.md)|지정 된 등록 스크립트를 실행합니다.|  
|[requires_category](../windows/requires-category.md)|클래스에 대 한 필수 구성 요소 범주를 지정합니다.|  
|[support_error_info](../windows/support-error-info.md)|대상 개체에 대 한 오류 보고를 지원 합니다.|  
|[synchronize](../windows/synchronize.md)|메서드에 대 한 액세스를 동기화합니다.|  
|[스레딩](../windows/threading-cpp.md)|COM 개체에 대 한 스레딩 모델을 지정 합니다.|  
|[vi_progid](../windows/vi-progid.md)|컨트롤에 대 한 버전 독립 ProgID를 정의합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [그룹별 특성](../windows/attributes-by-group.md)