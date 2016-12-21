---
title: "IDL Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
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
  - "IDL attributes"
  - ".idl files, attributes"
  - "IDL files, attributes"
  - ".idl files"
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDL Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

전통적으로.idl 파일을 유지 관리 하 여 했습니다.  
  
-   구조 및 수정할 수 있도록 하려면.idl 파일의 구문에 익숙해야 합니다.  
  
-   .Idl 파일의 몇 가지 측면을 수정할 수 있게 하는 마법사를 사용 합니다.  
  
 이제 Visual C\+\+ IDL 특성을 사용 하 여 소스 코드 파일에서 해당.idl 파일을 수정할 수 있습니다.  대부분의 경우 Visual C\+\+ IDL 특성을 MIDL 특성 이름이 같은 경우  Visual C\+\+ IDL 특성 및 MIDL 특성 이름이 되 면 동일한 소스 코드 파일에서 Visual C\+\+ 특성을 설정 합니다. 해당 namesake MIDL 특성이 있는.idl 파일에서 발생 합니다 의미 합니다.  그러나 Visual C\+\+ IDL 특성 MIDL 속성의 모든 기능을 제공할 수 있습니다지 않습니다.  
  
 않는 사용 되 면  [COM 특성](../windows/com-attributes.md), IDL 특성을 사용 하면 인터페이스를 정의 합니다.  소스 코드를 컴파일할 때 생성 된.idl 파일을 정의 하는 특성 사용 됩니다.  ATL 프로젝트에 COM 특성을 사용 하는 경우 일부 IDL, 같은 특성을  **coclass**, 코드를 프로젝트에 삽입 될 수 있습니다.  
  
 참고  [idl\_quote](../windows/idl-quote.md) Visual C\+\+의 현재 버전에서 지원 되지 않는 MIDL 구문을 사용할 수 있습니다.  이 같은 다른 특성  [importlib](../windows/importlib.md) 및  [includelib](../windows/includelib-cpp.md) 현재 Visual C\+\+ 프로젝트에서 기존.idl 파일을 사용 하는 데 도움이 됩니다.  
  
|특성|설명|  
|--------|--------|  
|[집계 가능한](../windows/aggregatable.md)|컨트롤을 다른 컨트롤에 의해 집계 될 수 있습니다 나타냅니다.|  
|[appobject](../windows/appobject.md)|Coclass는 전체 EXE 응용 프로그램에 연결 된, 함수 및 속성은 coclass의이 형식 라이브러리에 전역적으로 사용할 수 있는지 나타냅니다을 응용 프로그램 개체를 식별 합니다.|  
|[async\_uuid](../windows/async-uuid.md)|동기 및 비동기 버전의 COM 인터페이스를 정의 하는 MIDL 컴파일러에 지시 하는 값을 지정 합니다.|  
|[bindable](../windows/bindable.md)|속성이 데이터 바인딩을 지원합니다.|  
|[call\_as](../windows/call-as.md)|원격 가능 하지 않을 기능을 원격 함수에 매핑할 수 있습니다.|  
|[case](../windows/case-cpp.md)|사용은  [switch\_type](../windows/switch-type.md) 특성에는 공용 구조체입니다.|  
|[coclass](../windows/coclass.md)|Coclass 정의.idl 파일에 클래스가 배치 됩니다.|  
|[컨트롤](../windows/control.md)|컨트롤 사용자 정의 형식을 지정 합니다.|  
|[cpp\_quote](../windows/cpp-quote.md)|지정 된 문자열을 따옴표 없이 생성 된 헤더 파일에 내보냅니다.|  
|[defaultbind](../windows/defaultbind.md)|개체를 가장 잘 나타내는 단일의 바인딩 가능한 속성을 나타냅니다.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic 코드 최적화에 사용 됩니다.|  
|[defaultvalue](../windows/defaultvalue.md)|입력 된 선택적 매개 변수에 대 한 기본값을 지정할 수 있습니다.|  
|[default](../windows/default-cpp.md)|사용자 지정 또는 dispinterface coclass 내에서 정의 된 기본 프로그래밍 인터페이스를 나타냅니다.|  
|[defaultvtable](../windows/defaultvtable.md)|인터페이스 컨트롤에 대 한 기본 vtable 인터페이스를 정의합니다.|  
|[dispinterface](../windows/dispinterface.md)|인터페이스는.idl 파일의 디스패치 인터페이스를 배치합니다.|  
|[displaybind](../windows/displaybind.md)|사용자에 게 바인딩할 수 있다고 표시 되어야 하는 속성을 나타냅니다.|  
|[dual](../windows/dual.md)|인터페이스를 이중 인터페이스로.idl 파일에서를 배치합니다.|  
|[항목](../windows/entry.md)|내보낸된 함수 또는 상수는 모듈의 dll에서 진입점을 지정 하 여 지정 합니다.|  
|[first\_is](../windows/first-is.md)|전송할 첫 번째 배열 요소는 인덱스를 지정 합니다.|  
|[HelpContext](../windows/helpcontext.md)|사용자가 도움말 파일에서이 요소에 대 한 정보를 보기 수 있는 컨텍스트 ID를 지정 합니다.|  
|[도움말 파일](../windows/helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정 합니다.|  
|[helpstringcontext](../windows/helpstringcontext.md)|도움말 항목의 ID는.hlp 또는.chm 파일을 지정합니다.|  
|[helpstringdll](../windows/helpstringdll.md)|문서 문자열 \(지역화\) 조회를 수행 하는 데는 DLL의 이름을 지정 합니다.|  
|[helpstring](../windows/helpstring.md)|문자열이 적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.|  
|[hidden](../windows/hidden.md)|항목이 존재 하지만 사용자 기반 브라우저에 표시 되어서는 안 있음을 나타냅니다.|  
|[idl\_module](../windows/idl-module.md)|DLL에 진입점을 지정합니다.|  
|[idl\_quote](../windows/idl-quote.md)|Visual C\+\+의 현재 버전에서 지원 되지 않는 IDL 구문을 또는 특성을 사용할 수 있습니다.|  
|[id](../windows/id.md)|멤버 함수 \(속성 또는 메서드가 인터페이스 또는 dispinterface에\)는 DISPID를 지정합니다.|  
|[iid\_is](../windows/iid-is.md)|인터페이스 포인터에서 가리키는 COM 인터페이스의 IID를 지정 합니다.|  
|[immediatebind](../windows/immediatebind.md)|데이터베이스가 즉시 데이터 바인딩된 개체의 속성 변경 알림을 받을 수 있도록 나타냅니다.|  
|[importlib](../windows/importlib.md)|이미 생성 되 고 형식 라이브러리를 사용할 수 있는 다른 형식 라이브러리에 컴파일된 형식이 있습니다.|  
|[import](../windows/import.md)|주의.idl 파일에서 참조 하려는 정의 포함 하는 다른.idl,.odl, 또는 머리글 파일을 지정 합니다.|  
|[포함](../windows/include-cpp.md)|생성 된.idl 파일에 포함 시킬 헤더 파일을 지정 합니다.|  
|[includelib](../windows/includelib-cpp.md)|생성 된.idl 파일에 포함 될.idl 또는.h 파일이 됩니다.|  
|[in](../windows/in-cpp.md)|매개 변수가 호출된 되는 프로시저를 호출 하는 프로시저에서 전달 될입니다.|  
|[last\_is](../windows/last-is.md)|전송 하도록 마지막 배열 요소의 인덱스를 지정 합니다.|  
|[lcid](../windows/lcid.md)|로캘 식별자를 함수에 전달할 수 있습니다.|  
|[length\_is](../windows/length-is.md)|전송 하도록 배열 요소 수를 지정 합니다.|  
|[사용 허가](../windows/licensed.md)|적용 되는 coclass 허가 되지 사용 하 여 인스턴스화할 수 있음을 나타내며  **에서는 IClassFactory2**.|  
|[local](../windows/local-cpp.md)|MIDL 컴파일러 인터페이스 헤더에서 사용 하는 경우 머리글 생성기로 사용할 수 있습니다.  개별 함수에서 사용 하는 경우에 대 한 없음 스텁이 생성 되는 로컬 프로시저를 지정 합니다.|  
|[max\_is](../windows/max-is.md)|올바른 배열 인덱스에 대 한 최대 값을 지정합니다.|  
|[모듈\(module\)](../windows/module-cpp.md)|.Idl 파일 라이브러리 블록을 정의합니다.|  
|[ms\_union](../windows/ms-union.md)|Nonencapsulated 공용 구조체의 네트워크 데이터 표현 맞춤을 제어합니다.|  
|[no\_injected\_text](../windows/no-injected-text.md)|컴파일러가 특성 사용으로 인해 코드를 삽입 하지 못하도록 합니다.|  
|[nonbrowsable](../windows/nonbrowsable.md)|인터페이스 멤버 속성 브라우저에 표시 되어야 함을 나타냅니다.|  
|[만들 수 없도록](../windows/noncreatable.md)|자체로 인스턴스화할 수 있는 개체를 정의 합니다.|  
|[nonextensible](../windows/nonextensible.md)|지정 하는 `IDispatch` 구현 속성만 포함 됩니다 및 메서드는 인터페이스 설명에 나열 된 및 런타임에 추가 하는 멤버로 확장할 수 없습니다.|  
|[개체](../windows/object-cpp.md)|사용자 지정 인터페이스를 식별 합니다. 사용자 지정 특성을 갖는 동의어입니다.|  
|[odl](../windows/odl.md)|인터페이스와 개체 설명 언어 \(ODL\) 인터페이스를 식별합니다.|  
|[oleautomation](../windows/oleautomation.md)|인터페이스를 자동화 호환입니다.|  
|[\(옵션\)](../windows/optional-cpp.md)|멤버 함수에 대 한 선택적 매개 변수를 지정합니다.|  
|[out](../windows/out-cpp.md)|호출된 된 프로시저에서 호출 하는 프로시저로 \(서버에서 클라이언트로\)에서 반환 되는 포인터 매개 변수를 식별 합니다.|  
|[pointer\_default](../windows/pointer-default.md)|매개 변수 목록에 나타나는 최상위 포인터를 제외한 모든 포인터에 대 한 기본 포인터 특성을 지정 합니다.|  
|[pragma](../windows/pragma.md)|지정 된 문자열을 따옴표 없이 생성 된.idl 파일에 내보냅니다.|  
|[progid](../windows/progid.md)|COM 개체에 대 한 Progid를 지정합니다.|  
|[propget](../windows/propget.md)|속성 접근자 \(get\) 함수를 지정합니다.|  
|[propputref](../windows/propputref.md)|값이 아닌 참조를 사용 하 여 속성 설정 함수를 지정 합니다.|  
|[propput](../windows/propput.md)|속성 설정 함수를 지정합니다.|  
|[ptr](../windows/ptr.md)|전체 포인터로 대 한 포인터를 지정합니다.|  
|[public](../windows/public-cpp-attributes.md)|Typedef가에서.idl 파일에서 참조 되지 않는 경우에 형식 라이브러리에 진행 될 수 있습니다.|  
|[범위](../windows/range-cpp.md)|인수 또는 런타임에 값이 설정 된 필드에 대해 허용 가능한 값 범위를 지정 합니다.|  
|[readonly](../windows/readonly-cpp.md)|변수에 할당 하지 못하도록합니다.|  
|[ref](../windows/ref-cpp.md)|참조 포인터를 식별합니다.|  
|[requestedit](../windows/requestedit.md)|이 속성을 지원함을 나타내는  **OnRequestEdit** 알림.|  
|[restricted](../windows/restricted.md)|라이브러리 또는 모듈, 인터페이스 또는 dispinterface의 구성원이 임의로 호출할 수 없습니다 것을 지정 합니다.|  
|[retval](../windows/retval.md)|멤버의 반환 값을 받는 매개 변수를 지정 합니다.|  
|[size\_is](../windows/size-is.md)|메모리의 크기에 대 한 크기의 포인터를 할당, 크기의 포인터와 단일\-또는 다차원 배열에 대 한 포인터의 크기를 지정 합니다.|  
|[source](../windows/source-cpp.md)|구성원의 클래스, 속성 또는 메서드는 이벤트의 원본입니다.|  
|[string](../windows/string-cpp.md)|나타냅니다 있는 1 차원 `char`, `wchar_t`,  **바이트**, 또는 문자열로 배열 또는 이러한 배열에 대 한 포인터를 처리 해야 합니다.|  
|[switch\_is](../windows/switch-is.md)|식 또는 공용 구조체 멤버 선택은 통합 분석할으로 역할을 하는 식별자를 지정 합니다.|  
|[switch\_type](../windows/switch-type.md)|통합 분석할으로 사용 되는 변수를 식별 합니다.|  
|[transmit\_as](../windows/transmit-as.md)|전송 된 형식에는 클라이언트 및 서버 응용 프로그램을 조작 하는 제시 된 형식 연결 하도록 컴파일러에 지시 합니다.|  
|[uidefault](../windows/uidefault.md)|형식 정보 멤버는 사용자 인터페이스에 표시 하기 위해 기본 멤버입니다.|  
|[고유](../windows/unique-cpp.md)|고유한 포인터가 지정합니다.|  
|[usesgetlasterror](../windows/usesgetlasterror.md)|호출자에 게 해당 함수를 호출 하는 동안 오류가 있으면, 다음 호출자가 호출할 수 있습니다 알려줍니다 `GetLastError` 오류 코드를 검색 합니다.|  
|[uuid](../windows/uuid-cpp-attributes.md)|클래스 또는 인터페이스에 대 한 고유 ID를 지정합니다.|  
|[v1\_enum](../windows/v1-enum.md)|지정 된 열거 형식 기본 16 비트 대신 32 비트 엔티티를 전송할 수 있는지를 지정 합니다.|  
|[vararg](../windows/vararg.md)|함수가 가변 개수의 인수를 사용 하도록 지정.|  
|[vi\_progid](../windows/vi-progid.md)|버전에 관계 없이 폼의 ProgID 지정합니다.|  
|[wire\_marshal](../windows/wire-marshal.md)|전송 하는 응용 프로그램 특정 데이터 형식 대신 사용할 수 있는 데이터 형식을 지정 합니다.|  
  
## 참고 항목  
 [Attributes by Group](../windows/attributes-by-group.md)   
 [Attribute Limitations](http://msdn.microsoft.com/ko-kr/6e6c4329-f667-4869-b991-cbe9cb7a8f61)