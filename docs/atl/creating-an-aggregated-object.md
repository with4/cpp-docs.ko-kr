---
title: 집계 개체 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f6ff5a0fdcff62d62469f17388f633b83739a09
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850828"
---
# <a name="creating-an-aggregated-object"></a>집계 개체 만들기
집계 대리자 `IUnknown` 외부 개체에 대 한 포인터를 제공 하는 호출 `IUnknown` 내부 개체입니다.  
  
### <a name="to-create-an-aggregated-object"></a>집계 개체를 만들려면  
  
1.  추가 `IUnknown` 클래스에 대 한 포인터 개체를 생성자에 NULL로 초기화 합니다.  
  
2.  재정의 [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) 집계를 만드는 합니다.  
  
3.  사용 하 여는 `IUnknown` 포인터에 대 한 두 번째 매개 변수로 1 단계에서에서 정의 된 [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) 매크로입니다.  
  
4.  재정의 [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) 해제 하는 `IUnknown` 포인터입니다.  
  
> [!NOTE]
>  사용 하 고 하는 동안 집계 된 개체의 인터페이스를 릴리스 하는 경우 `FinalConstruct`를 추가 해야 합니다 [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) 클래스 개체의 정의에 매크로입니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)

