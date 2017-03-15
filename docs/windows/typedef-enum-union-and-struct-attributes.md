---
title: "Typedef, Enum, Union, and Struct Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "union attributes"
  - "attributes [C++], reference topics"
  - "struct attributes"
  - "typedef attributes"
  - "enum attributes"
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Typedef, Enum, Union, and Struct Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 특성을 적용은  [형식 정의](http://msdn.microsoft.com/ko-kr/cc96cf26-ba93-4179-951e-695d1f5fdcf1),  [구조체](../cpp/struct-cpp.md), 및  [열거형](../cpp/enumerations-cpp.md) C\+\+ 키워드입니다.  
  
### 형식 정의  
  
|특성|설명|  
|--------|--------|  
|[case](../windows/case-cpp.md)|함께 사용 되는  [switch\_type](../windows/switch-type.md) 특성에  **공용 구조체**.|  
|[custom](../windows/custom-cpp.md)|사용자 고유의 특성을 정의할 수 있습니다.|  
|[export](../windows/export.md)|.Idl 파일에 추가할 수 있는 데이터 구조를 인해 발생 합니다.|  
|[first\_is](../windows/first-is.md)|전송할 첫 번째 배열 요소는 인덱스를 지정 합니다.|  
|[HelpContext](../windows/helpcontext.md)|사용자가 도움말 파일에서이 요소에 대 한 정보를 보기 수 있는 컨텍스트 ID를 지정 합니다.|  
|[도움말 파일](../windows/helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정 합니다.|  
|[helpstring](../windows/helpstring.md)|문자열이 적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.|  
|[library\_block](../windows/library-block.md)|구문.idl 파일 라이브러리 블록 안에 배치 됩니다.|  
|[ptr](../windows/ptr.md)|전체 포인터로 대 한 포인터를 지정합니다.|  
|[public](../windows/public-cpp-attributes.md)|Typedef가에서.idl 파일에서 참조 되지 않는 경우에 형식 라이브러리에 진행 될 수 있습니다.|  
|[ref](../windows/ref-cpp.md)|참조 포인터를 식별합니다.|  
|[switch\_is](../windows/switch-is.md)|식 또는 공용 구조체 멤버 선택은 통합 분석할으로 역할을 하는 식별자를 지정 합니다.|  
|[switch\_type](../windows/switch-type.md)|통합 분석할으로 사용 되는 변수를 식별 합니다.|  
|[고유](../windows/unique-cpp.md)|고유한 포인터가 지정합니다.|  
|[wire\_marshal](../windows/wire-marshal.md)|전송 하는 응용 프로그램 특정 데이터 형식 대신 사용할 수 있는 데이터 형식을 지정 합니다.|  
  
### enum  
  
|특성|설명|  
|--------|--------|  
|[custom](../windows/custom-cpp.md)|사용자 고유의 특성을 정의할 수 있습니다.|  
|[export](../windows/export.md)|.Idl 파일에 추가할 수 있는 데이터 구조를 인해 발생 합니다.|  
|[uuid](../windows/uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정합니다.|  
|[v1\_enum](../windows/v1-enum.md)|지정 된 열거 형식 기본 16 비트 대신 32 비트 엔티티를 전송할 수 있는지를 지정 합니다.|  
  
### union  
  
|특성|설명|  
|--------|--------|  
|[custom](../windows/custom-cpp.md)|사용자 고유의 특성을 정의할 수 있습니다.|  
|[export](../windows/export.md)|.Idl 파일에 추가할 수 있는 데이터 구조를 인해 발생 합니다.|  
|[first\_is](../windows/first-is.md)|전송할 첫 번째 배열 요소는 인덱스를 지정 합니다.|  
|[last\_is](../windows/last-is.md)|전송 하도록 마지막 배열 요소의 인덱스를 지정 합니다.|  
|[length\_is](../windows/length-is.md)|전송 하도록 배열 요소 수를 지정 합니다.|  
|[max\_is](../windows/max-is.md)|올바른 배열 인덱스에 대 한 최대 값을 지정합니다.|  
|[size\_is](../windows/size-is.md)|메모리의 크기에 대 한 크기의 포인터를 할당, 크기의 포인터와 단일\-또는 다차원 배열에 대 한 포인터의 크기를 지정 합니다.|  
|[고유](../windows/unique-cpp.md)|고유한 포인터가 지정합니다.|  
|[uuid](../windows/uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정합니다.|  
  
### Nonencapsulated 공용 구조체  
  
|특성|설명|  
|--------|--------|  
|[ms\_union](../windows/ms-union.md)|Nonencapsulated 공용 구조체의 네트워크 데이터 표현 맞춤을 제어합니다.|  
|[no\_injected\_text](../windows/no-injected-text.md)|컴파일러가 특성 사용으로 인해 코드를 삽입 하지 못하도록 합니다.|  
  
### struct  
  
|특성|설명|  
|--------|--------|  
|[집계 가능한](../windows/aggregatable.md)|클래스가 집계를 지원함을 나타냅니다.|  
|[집계](../windows/aggregates.md)|컨트롤에서 대상 클래스를 집계를 나타냅니다.|  
|[appobject](../windows/appobject.md)|Coclass는 전체.exe 응용 프로그램에 연결 되 고 함수 및 속성은 coclass의이 형식 라이브러리에 전역적으로 사용할 수 있음을 나타냅니다을 응용 프로그램 개체를 식별 합니다.|  
|[coclass](../windows/coclass.md)|ActiveX 컨트롤을 만듭니다.|  
|[com\_interface\_entry](../windows/com-interface-entry-cpp.md)|COM 맵에 인터페이스 항목을 추가 합니다.|  
|[컨트롤](../windows/control.md)|컨트롤 사용자 정의 형식을 지정 합니다.|  
|[custom](../windows/custom-cpp.md)|사용자 고유의 특성을 정의할 수 있습니다.|  
|[db\_column](../windows/db-column.md)|지정 된 열은 행 집합에 바인딩합니다.|  
|[db\_command](../windows/db-command.md)|OLE DB 명령을 만듭니다.|  
|[db\_param](../windows/db-param.md)|지정 된 멤버 변수는 입력 또는 출력 매개 변수를 연결 하 고 변수를 구분 합니다.|  
|[db\_source](../windows/db-source.md)|데이터 원본에 연결을 만듭니다.|  
|[db\_table](../windows/db-table.md)|OLE DB 테이블을 엽니다.|  
|[default](../windows/default-cpp.md)|사용자 지정 또는 dispinterface coclass 내에서 정의 된 기본 프로그래밍 인터페이스를 나타냅니다.|  
|[defaultvtable](../windows/defaultvtable.md)|인터페이스 컨트롤에 대 한 기본 vtable 인터페이스를 정의합니다.|  
|[event\_receiver](../windows/event-receiver.md)|이벤트 수신기를 만듭니다.|  
|[event\_source](../windows/event-source.md)|이벤트 소스를 만듭니다.|  
|[export](../windows/export.md)|.Idl 파일에 추가할 수 있는 데이터 구조를 인해 발생 합니다.|  
|[first\_is](../windows/first-is.md)|전송할 첫 번째 배열 요소는 인덱스를 지정 합니다.|  
|[hidden](../windows/hidden.md)|항목이 존재 하지만 사용자 기반 브라우저에 표시 되어서는 안 있음을 나타냅니다.|  
|[implements\_category](../windows/implements-category.md)|클래스에 구현 된 구성 요소 범주를 지정합니다.|  
|[last\_is](../windows/last-is.md)|전송 하도록 마지막 배열 요소의 인덱스를 지정 합니다.|  
|[length\_is](../windows/length-is.md)|전송 하도록 배열 요소 수를 지정 합니다.|  
|[max\_is](../windows/max-is.md)|올바른 배열 인덱스에 대 한 최대 값을 지정합니다.|  
|[requires\_category](../windows/requires-category.md)|필수 구성 요소 범주는 대상 클래스를 지정합니다.|  
|[size\_is](../windows/size-is.md)|메모리의 크기에 대 한 크기의 포인터를 할당, 크기의 포인터와 단일\-또는 다차원 배열에 대 한 포인터의 크기를 지정 합니다.|  
|[source](../windows/source-cpp.md)|클래스에 COM 개체의 소스 인터페이스의 연결 지점 지정합니다.  속성 또는 메서드를 개체 또는 VARIANT는 이벤트의 소스인 멤버를 반환 하는 나타냅니다.|  
|[스레딩](../windows/threading-cpp.md)|COM 개체의 스레딩 모델을 지정합니다.|  
|[고유](../windows/unique-cpp.md)|고유한 포인터가 지정합니다.|  
|[uuid](../windows/uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정합니다.|  
|[version](../windows/version-cpp.md)|여러 개의 클래스 중에서 특정 버전을 식별합니다.|  
|[vi\_progid](../windows/vi-progid.md)|버전에 관계 없이 폼의 ProgID 지정합니다.|  
  
## 참고 항목  
 [Attributes by Usage](../windows/attributes-by-usage.md)