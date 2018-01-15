---
title: "데이터 멤버 특성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], reference topics
- data members [C++], attributes
- data members [C++]
ms.assetid: 95b2397d-1daf-4ae4-8cd0-06956d005b13
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 954a0448f160ba6d19eb4f48d44b0b7e0a718f17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="data-member-attributes"></a>데이터 멤버 특성
다음 특성은 클래스, coclass 등 또는 인터페이스의 데이터 멤버에 적용 합니다.  
  
|특성|설명|  
|---------------|-----------------|  
|[db_accessor](../windows/db-accessor.md)|그룹 **db_column** 에 참여 하는 특성 `IAccessor`-바인딩을 기반으로 합니다.|  
|[db_column](../windows/db-column.md)|행 집합을 지정된 된 열에 바인딩합니다.|  
|[db_command](../windows/db-command.md)|OLE DB 명령을 만듭니다.|  
|[db_param](../windows/db-param.md)|지정 된 멤버 변수는 입력 또는 출력 매개 변수 연결 하 고 변수를 구분 합니다.|  
|[db_source](../windows/db-source.md)|데이터 원본에 대 한 연결을 만듭니다.|  
|[db_table](../windows/db-table.md)|OLE DB 테이블을 엽니다.|  
|[defaultbind](../windows/defaultbind.md)|개체에 가장 잘 나타내는 단일, 바인딩 가능 속성을 나타냅니다.|  
|[displaybind](../windows/displaybind.md)|바인딩 가능한 사용자에 게 표시 되어야 하는 속성을 나타냅니다.|  
|[ID](../windows/id.md)|멤버 함수 (속성 또는 메서드를 인터페이스 또는 dispinterface)에 대 한 DISPID를 지정합니다.|  
|[범위](../windows/range-cpp.md)|형식 정의 나 런타임에 해당 값이 설정 되는 필드에 대 한 허용 가능한 값의 범위를 지정 합니다.|  
|[rdx](../windows/rdx.md)|레지스트리 키를 만들거나 기존 레지스트리 키를 수정 합니다.|  
|[readonly](../windows/readonly-cpp.md)|데이터 멤버에 대한 할당을 금지합니다.|  
|[requestedit](../windows/requestedit.md)|속성을 지원 하는지 나타냅니다는 **OnRequestEdit** 알림입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [용도별 특성](../windows/attributes-by-usage.md)