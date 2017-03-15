---
title: "Interface Attributes | Microsoft Docs"
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
  - "attributes [C++], reference topics"
  - "interface attributes"
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Interface Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 특성을 적용은  [인터페이스 \(또는 \_\_interface\)](../cpp/interface.md) C\+\+ 키워드입니다.  
  
|특성|설명|  
|--------|--------|  
|[async\_uuid](../windows/async-uuid.md)|동기 및 비동기 버전의 COM 인터페이스를 정의 하는 MIDL 컴파일러에 지시 하는 값을 지정 합니다.|  
|[custom](../windows/custom-cpp.md)|사용자 지정 특성을 정의할 수 있습니다.|  
|[dispinterface](../windows/dispinterface.md)|인터페이스는.idl 파일의 디스패치 인터페이스를 배치합니다.|  
|[dual](../windows/dual.md)|인터페이스를 이중 인터페이스로.idl 파일에서를 배치합니다.|  
|[export](../windows/export.md)|.Idl 파일에 추가할 수 있는 데이터 구조를 인해 발생 합니다.|  
|[HelpContext](../windows/helpcontext.md)|사용자가 도움말 파일에서이 요소에 대 한 정보를 보기 수 있는 컨텍스트 ID를 지정 합니다.|  
|[도움말 파일](../windows/helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정 합니다.|  
|[helpstring](../windows/helpstring.md)|문자열이 적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.|  
|[helpstringcontext](../windows/helpstringcontext.md)|도움말 항목의 ID는.hlp 또는.chm 파일을 지정합니다.|  
|[helpstringdll](../windows/helpstringdll.md)|문서 문자열 \(지역화\) 조회를 수행 하는 데는 DLL의 이름을 지정 합니다.|  
|[hidden](../windows/hidden.md)|항목이 존재 하지만 사용자 기반 브라우저에 표시 되어서는 안 있음을 나타냅니다.|  
|[library\_block](../windows/library-block.md)|구문.idl 파일 라이브러리 블록 안에 배치 됩니다.|  
|[local](../windows/local-cpp.md)|MIDL 컴파일러 인터페이스 헤더에서 사용 하는 경우 머리글 생성기로 사용할 수 있습니다.  개별 함수에서 사용 하는 경우에 대 한 없음 스텁이 생성 되는 로컬 프로시저를 지정 합니다.|  
|[nonextensible](../windows/nonextensible.md)|지정 하는 `IDispatch` 구현 속성만 포함 됩니다 및 메서드는 인터페이스 설명에 나열 된 및 런타임에 추가 하는 멤버로 확장할 수 없습니다.  이 특성은에서 사용할 수 있는  [듀얼](../windows/dual.md) 인터페이스.|  
|[odl](../windows/odl.md)|인터페이스와 개체 설명 언어 \(ODL\) 인터페이스를 식별합니다.|  
|[개체](../windows/object-cpp.md)|사용자 지정 인터페이스를 식별합니다.|  
|[oleautomation](../windows/oleautomation.md)|인터페이스를 자동화 호환입니다.|  
|[pointer\_default](../windows/pointer-default.md)|매개 변수 목록에 나타나는 최상위 포인터를 제외한 모든 포인터에 대 한 기본 포인터 특성을 지정 합니다.|  
|[ptr](../windows/ptr.md)|전체 포인터로 대 한 포인터를 지정합니다.|  
|[restricted](../windows/restricted.md)|라이브러리 멤버를 임의로 호출할 수 없습니다 지정 됩니다.|  
|[uuid](../windows/uuid-cpp-attributes.md)|라이브러리에 대 한 고유 ID를 제공합니다.|  
  
 인터페이스 정의 대 한 이러한 규칙을 준수 해야 합니다.  
  
-   기본 호출 규칙입니다  [\_\_stdcall](../cpp/stdcall.md).  
  
-   지정 하지 않으면 GUID가 제공 됩니다.  
  
-   오버 로드 된 메서드가 사용할 수 있습니다.  
  
 않는 지정 하는 경우는  [uuid](../windows/uuid-cpp-attributes.md) 특성 및 특성을 다른 프로젝트에서 동일한 인터페이스 이름을 사용 하 여 동일한 GUID가 생성 됩니다.  
  
## 참고 항목  
 [Attributes by Usage](../windows/attributes-by-usage.md)