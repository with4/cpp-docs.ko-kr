---
title: "Typedef, Enum, Union 및 Struct 특성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- union attributes
- attributes [C++], reference topics
- struct attributes
- typedef attributes
- enum attributes
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9bba47c5c0ea12ae7c1ae4f57adc24b58166ded8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="typedef-enum-union-and-struct-attributes"></a>Typedef, Enum, Union 및 Struct 특성
다음과 같은 특성에 적용 된 [typedef](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1), [구조체](../cpp/struct-cpp.md), 및 [열거형](../cpp/enumerations-cpp.md) c + + 키워드입니다.  
  
### <a name="typedef"></a>형식 정의  
  
|특성|설명|  
|---------------|-----------------|  
|[case](../windows/case-cpp.md)|함께 사용 된 [switch_type](../windows/switch-type.md) 특성에 **union**합니다.|  
|[사용자 지정](../windows/custom-cpp.md)|특성을 직접 정의할 수 있습니다.|  
|[export](../windows/export.md)|데이터 구조는.idl 파일에 배치 하면 됩니다.|  
|[first_is](../windows/first-is.md)|전송 될 첫 번째 배열 요소의 인덱스를 지정 합니다.|  
|[helpcontext](../windows/helpcontext.md)|사용자는 도움말 파일에서이 요소에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다.|  
|[helpfile](../windows/helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정합니다.|  
|[helpstring](../windows/helpstring.md)|적용 되는 요소에 설명 하는 데 사용 되는 문자열을 지정 합니다.|  
|[library_block](../windows/library-block.md)|.Idl 파일의 라이브러리 블록 내부는 구문을 배치합니다.|  
|[ptr](../windows/ptr.md)|전체 포인터도 포인터를 지정합니다.|  
|[public](../windows/public-cpp-attributes.md)|.Idl 파일 내에서 참조 하지 않는 경우에 형식 라이브러리로 typedef 상태로 진행 될를 확인 합니다.|  
|[ref](../windows/ref-cpp.md)|참조 포인터를 식별합니다.|  
|[switch_is](../windows/switch-is.md)|식 또는 공용 구조체 멤버를 선택 하 고 union 판별 역할 식별자를 지정 합니다.|  
|[switch_type](../windows/switch-type.md)|Union 판별으로 사용 된 변수의 형식을 식별 합니다.|  
|[unique](../windows/unique-cpp.md)|고유한 포인터를 지정합니다.|  
|[wire_marshal](../windows/wire-marshal.md)|응용 프로그램 관련 데이터 형식이 아닌 전송을 위해 사용 될 데이터 형식을 지정 합니다.|  
  
### <a name="enum"></a>enum  
  
|특성|설명|  
|---------------|-----------------|  
|[사용자 지정](../windows/custom-cpp.md)|특성을 직접 정의할 수 있습니다.|  
|[export](../windows/export.md)|데이터 구조는.idl 파일에 배치 하면 됩니다.|  
|[uuid](../windows/uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정합니다.|  
|[v1_enum](../windows/v1-enum.md)|열거 형식이 지정된 된 16 비트 기본이 아닌 32 비트 엔터티 전송 될 지시 합니다.|  
  
### <a name="union"></a>union  
  
|특성|설명|  
|---------------|-----------------|  
|[사용자 지정](../windows/custom-cpp.md)|특성을 직접 정의할 수 있습니다.|  
|[export](../windows/export.md)|데이터 구조는.idl 파일에 배치 하면 됩니다.|  
|[first_is](../windows/first-is.md)|전송 될 첫 번째 배열 요소의 인덱스를 지정 합니다.|  
|[last_is](../windows/last-is.md)|전송할 마지막 배열 요소의 인덱스를 지정 합니다.|  
|[length_is](../windows/length-is.md)|전송할 배열 요소의 수를 지정 합니다.|  
|[max_is](../windows/max-is.md)|유효한 배열 인덱스에 대 한 최대값을 지정합니다.|  
|[size_is](../windows/size-is.md)|메모리의 크기 크기의 포인터에 대 한 할당 된 크기의 포인터 및 단일 또는 다차원 배열에 대 한 포인터 크기 지정 합니다.|  
|[unique](../windows/unique-cpp.md)|고유한 포인터를 지정합니다.|  
|[uuid](../windows/uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정합니다.|  
  
### <a name="nonencapsulated-union"></a>Nonencapsulated 공용 구조체  
  
|특성|설명|  
|---------------|-----------------|  
|[ms_union](../windows/ms-union.md)|Nonencapsulated 공용 구조체의 네트워크 데이터 표현 맞춤을 제어합니다.|  
|[no_injected_text](../windows/no-injected-text.md)|특성 사용 결과로 코드 주입에서 컴파일러를 방지 합니다.|  
  
### <a name="struct"></a>struct  
  
|특성|설명|  
|---------------|-----------------|  
|[aggregatable](../windows/aggregatable.md)|클래스에서 집계를 지원 하는지 나타냅니다.|  
|[aggregates](../windows/aggregates.md)|컨트롤은 대상 클래스 집계 됨을 나타냅니다.|  
|[appobject](../windows/appobject.md)|전체.exe 응용 프로그램과 연결 된 문서를 나타내고이 형식 라이브러리에서 함수 및 속성 coclass의를 전체적으로 사용할 수 있는 응용 프로그램 개체를으로 coclass를 식별 합니다.|  
|[coclass](../windows/coclass.md)|ActiveX 컨트롤을 만듭니다.|  
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|Com에 인터페이스 항목을 추가 합니다.|  
|[control](../windows/control.md)|사용자 정의 형식 컨트롤 임을 지정 합니다.|  
|[사용자 지정](../windows/custom-cpp.md)|특성을 직접 정의할 수 있습니다.|  
|[db_column](../windows/db-column.md)|행 집합을 지정된 된 열에 바인딩합니다.|  
|[db_command](../windows/db-command.md)|OLE DB 명령을 만듭니다.|  
|[db_param](../windows/db-param.md)|지정 된 멤버 변수는 입력 또는 출력 매개 변수 연결 하 고 변수를 구분 합니다.|  
|[db_source](../windows/db-source.md)|데이터 원본에 대 한 연결을 만듭니다.|  
|[db_table](../windows/db-table.md)|OLE DB 테이블을 엽니다.|  
|[default](../windows/default-cpp.md)|coclass 내에 정의된 custom 또는 dispinterface가 기본 프로그래밍 인터페이스를 나타낸다는 것을 의미합니다.|  
|[defaultvtable](../windows/defaultvtable.md)|컨트롤에 대 한 기본 vtable 인터페이스로 인터페이스를 정의합니다.|  
|[event_receiver](../windows/event-receiver.md)|이벤트 수신기를 만듭니다.|  
|[event_source](../windows/event-source.md)|이벤트 소스를 만듭니다.|  
|[export](../windows/export.md)|데이터 구조는.idl 파일에 배치 하면 됩니다.|  
|[first_is](../windows/first-is.md)|전송 될 첫 번째 배열 요소의 인덱스를 지정 합니다.|  
|[hidden](../windows/hidden.md)|항목이 존재 하지만 하지 사용자 기반 브라우저에 표시할지 나타냅니다.|  
|[implements_category](../windows/implements-category.md)|클래스에 대해 구현 된 구성 요소 범주를 지정합니다.|  
|[last_is](../windows/last-is.md)|전송할 마지막 배열 요소의 인덱스를 지정 합니다.|  
|[length_is](../windows/length-is.md)|전송할 배열 요소의 수를 지정 합니다.|  
|[max_is](../windows/max-is.md)|유효한 배열 인덱스에 대 한 최대값을 지정합니다.|  
|[requires_category](../windows/requires-category.md)|대상 클래스의 필수 구성 요소 범주를 지정합니다.|  
|[size_is](../windows/size-is.md)|메모리의 크기 크기의 포인터에 대 한 할당 된 크기의 포인터 및 단일 또는 다차원 배열에 대 한 포인터 크기 지정 합니다.|  
|[소스](../windows/source-cpp.md)|클래스를 연결 지점에 대 한 COM 개체의 소스 인터페이스를 지정합니다. 속성 또는 메서드 멤버 개체 또는 이벤트의 원본인 VARIANT를 반환 하는지 나타냅니다.|  
|[스레딩](../windows/threading-cpp.md)|COM 개체에 대 한 스레딩 모델을 지정 합니다.|  
|[unique](../windows/unique-cpp.md)|고유한 포인터를 지정합니다.|  
|[uuid](../windows/uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정합니다.|  
|[version](../windows/version-cpp.md)|클래스의 여러 버전 간에 특정 버전을 식별합니다.|  
|[vi_progid](../windows/vi-progid.md)|버전 독립 ProgID 형태의 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [용도별 특성](../windows/attributes-by-usage.md)