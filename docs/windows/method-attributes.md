---
title: "Method Attributes | Microsoft Docs"
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
  - "method attributes"
  - "attributes [C++], reference topics"
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Method Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터페이스, coclass, 또는 클래스의 메서드는 다음과 같은 특성이 적용 됩니다.  
  
|특성|설명|  
|--------|--------|  
|[bindable](../windows/bindable.md)|속성이 데이터 바인딩을 지원합니다.|  
|[call\_as](../windows/call-as.md)|원격 가능 하지 않을 기능을 원격 함수에 매핑할 수 있습니다.|  
|[custom](../windows/custom-cpp.md)|사용자 고유의 특성을 정의할 수 있습니다.|  
|[db\_column](../windows/db-column.md)|지정 된 열은 행 집합에 바인딩합니다.|  
|[db\_command](../windows/db-command.md)|OLE DB 명령을 만듭니다.|  
|[db\_param](../windows/db-param.md)|지정 된 멤버 변수는 입력 또는 출력 매개 변수를 연결 하 고 변수를 구분 합니다.|  
|[db\_source](../windows/db-source.md)|데이터 원본에 연결을 만듭니다.|  
|[db\_table](../windows/db-table.md)|OLE DB 테이블을 엽니다.|  
|[defaultbind](../windows/defaultbind.md)|개체를 가장 잘 나타내는 단일의 바인딩 가능한 속성을 나타냅니다.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic 코드 최적화에 사용 됩니다.|  
|[displaybind](../windows/displaybind.md)|사용자에 게 바인딩할 수 있다고 표시 되어야 하는 속성을 나타냅니다.|  
|[HelpContext](../windows/helpcontext.md)|사용자가 도움말 파일에서이 요소에 대 한 정보를 보기 수 있는 컨텍스트 ID를 지정 합니다.|  
|[도움말 파일](../windows/helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정 합니다.|  
|[helpstring](../windows/helpstring.md)|문자열이 적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.|  
|[helpstringcontext](../windows/helpstringcontext.md)|도움말 항목의 ID는.hlp 또는.chm 파일을 지정합니다.|  
|[helpstringdll](../windows/helpstringdll.md)|문서 문자열 \(지역화\) 조회를 수행 하는 데는 DLL의 이름을 지정 합니다.|  
|[hidden](../windows/hidden.md)|항목이 존재 하지만 사용자 기반 브라우저에 표시 되어서는 안 있음을 나타냅니다.|  
|[id](../windows/id.md)|멤버 함수 \(속성 또는 메서드가 인터페이스 또는 dispinterface에\)는 DISPID를 지정합니다.|  
|[immediatebind](../windows/immediatebind.md)|데이터베이스가 즉시 데이터 바인딩된 개체의 속성 변경 알림을 받을 수 있도록 나타냅니다.|  
|[in](../windows/in-cpp.md)|매개 변수가 호출된 되는 프로시저를 호출 하는 프로시저에서 전달 될입니다.|  
|[local](../windows/local-cpp.md)|MIDL 컴파일러 인터페이스 헤더에서 사용 하는 경우 머리글 생성기로 사용할 수 있습니다.  개별 함수에서 사용 하는 경우에 대 한 없음 스텁이 생성 되는 로컬 프로시저를 지정 합니다.|  
|[nonbrowsable](../windows/nonbrowsable.md)|인터페이스 멤버 속성 브라우저에 표시 되어야 함을 나타냅니다.|  
|[propget](../windows/propget.md)|속성 접근자 함수를 지정합니다.|  
|[propput](../windows/propput.md)|속성 설정 함수를 지정합니다.|  
|[propputref](../windows/propputref.md)|값이 아닌 참조를 사용 하 여 속성 설정 함수를 지정 합니다.|  
|[ptr](../windows/ptr.md)|전체 포인터로 대 한 포인터를 지정합니다.|  
|[범위](../windows/range-cpp.md)|인수 또는 런타임에 값이 설정 된 필드에 대해 허용 가능한 값 범위를 지정 합니다.|  
|[requestedit](../windows/requestedit.md)|이 속성을 지원함을 나타내는  **OnRequestEdit** 알림.|  
|[restricted](../windows/restricted.md)|멤버는 모듈, 인터페이스 또는 dispinterface를 임의로 호출할 수 없습니다 지정 합니다.|  
|[satype](../windows/satype.md)|데이터 형식을 지정은  **SAFEARRAY** 구조체입니다.|  
|[source](../windows/source-cpp.md)|연결 지점에 대 한 원본 인터페이스를 컨트롤의 클래스를 지정합니다.  속성 또는 메서드를 해당  **소스**  개체 또는 VARIANT는 이벤트의 소스인 멤버를 반환 하는 특성을 나타냅니다.|  
|[동기화](../windows/synchronize.md)|대상 메서드에 대 한 액세스가 동기화합니다.|  
|[vararg](../windows/vararg.md)|함수가 가변 개수의 인수를 사용 하도록 지정.|  
  
## 참고 항목  
 [Attributes by Usage](../windows/attributes-by-usage.md)