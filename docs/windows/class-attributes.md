---
title: "클래스 특성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], class attributes
- class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9d6883774f6deeae2d8c372b68362c743d206eb9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="class-attributes"></a>클래스 특성
다음과 같은 특성에 적용 된 [클래스](../cpp/class-cpp.md) c + + 키워드입니다.  
  
|특성|설명|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|클래스에서 집계를 지원 하는지 나타냅니다.|  
|[aggregates](../windows/aggregates.md)|컨트롤은 대상 클래스 집계 됨을 나타냅니다.|  
|[appobject](../windows/appobject.md)|전체.exe 응용 프로그램과 연결 된 문서를 나타내고이 형식 라이브러리에서 함수 및 속성 coclass의를 전체적으로 사용할 수 있는 응용 프로그램 개체를으로 coclass를 식별 합니다.|  
|[case](../windows/case-cpp.md)|함께 사용 된 [switch_type](../windows/switch-type.md) 공용 구조체의 특성입니다.|  
|[coclass](../windows/coclass.md)|ActiveX 컨트롤을 만듭니다.|  
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|Com에 인터페이스 항목을 추가 합니다.|  
|[control](../windows/control.md)|사용자 정의 형식 컨트롤 임을 지정 합니다.|  
|[사용자 지정](../windows/custom-cpp.md)|특성을 직접 정의할 수 있습니다.|  
|[db_command](../windows/db-command.md)|OLE DB 명령을 만듭니다.|  
|[db_param](../windows/db-param.md)|지정 된 멤버 변수는 입력 또는 출력 매개 변수 연결 하 고 변수를 구분 합니다.|  
|[db_source](../windows/db-source.md)|데이터 원본에 대 한 연결을 만듭니다.|  
|[db_table](../windows/db-table.md)|OLE DB 테이블을 엽니다.|  
|[default](../windows/default-cpp.md)|coclass 내에 정의된 custom 또는 dispinterface가 기본 프로그래밍 인터페이스를 나타낸다는 것을 의미합니다.|  
|[defaultvtable](../windows/defaultvtable.md)|컨트롤에 대 한 기본 vtable 인터페이스로 인터페이스를 정의합니다.|  
|[event_receiver](../windows/event-receiver.md)|이벤트 수신기를 만듭니다.|  
|[event_source](../windows/event-source.md)|이벤트 소스를 만듭니다.|  
|[helpcontext](../windows/helpcontext.md)|사용자는 도움말 파일에서이 요소에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다.|  
|[helpfile](../windows/helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정합니다.|  
|[helpstringcontext](../windows/helpstringcontext.md)|.Hlp 또는.chm 파일 도움말 항목의 ID를 지정합니다.|  
|[helpstring](../windows/helpstring.md)|적용 되는 요소에 설명 하는 데 사용 되는 문자열을 지정 합니다.|  
|[hidden](../windows/hidden.md)|항목이 존재 하지만 하지 사용자 기반 브라우저에 표시할지 나타냅니다.|  
|[구현](../windows/implements-cpp.md)|IDL coclass의 구성원이 될 해야 하는 디스패치 인터페이스를 지정 합니다.|  
|[implements_category](../windows/implements-category.md)|클래스에 대해 구현 된 구성 요소 범주를 지정합니다.|  
|[모듈](../windows/module-cpp.md)|.Idl 파일의 라이브러리 블록을 정의합니다.|  
|[noncreatable](../windows/noncreatable.md)|단독으로 인스턴스화할 수 없는 개체를 정의 합니다.|  
|[progid](../windows/progid.md)|컨트롤의 ProgID를 정의합니다.|  
|[registration_script](../windows/registration-script.md)|지정 된 등록 스크립트를 실행합니다.|  
|[requestedit](../windows/requestedit.md)|속성을 지원 하는지 나타냅니다는 **OnRequestEdit** 알림입니다.|  
|[소스](../windows/source-cpp.md)|클래스에 연결 지점에 대 한 컨트롤의 소스 인터페이스를 지정합니다. 메서드나 속성에는 **소스** 특성 멤버 개체 또는 이벤트의 원본인 VARIANT를 반환 하는지 나타냅니다.|  
|[support_error_info](../windows/support-error-info.md)|대상 개체에 대 한 오류 보고를 지원 합니다.|  
|[스레딩](../windows/threading-cpp.md)|컨트롤에 대 한 스레딩 모델을 지정 합니다.|  
|[uuid](../windows/uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정합니다.|  
|[version](../windows/version-cpp.md)|클래스의 여러 버전 간에 특정 버전을 식별합니다.|  
|[vi_progid](../windows/vi-progid.md)|버전 독립 ProgID 형태의 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [용도별 특성](../windows/attributes-by-usage.md)