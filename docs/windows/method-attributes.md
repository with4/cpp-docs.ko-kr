---
title: 메서드 특성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- method attributes
- attributes [C++], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d2efe55058ab2ace7530afee7255b2ba08377b0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="method-attributes"></a>메서드 특성
다음 특성은 클래스, coclass 등 또는 인터페이스의 메서드에 적용 합니다.  
  
|특성|설명|  
|---------------|-----------------|  
|[bindable](../windows/bindable.md)|속성이 데이터 바인딩을 지원 하는지 나타냅니다.|  
|[call_as](../windows/call-as.md)|원격 가능 하지 함수를 원격 함수에 매핑할 수 있습니다.|  
|[custom](../windows/custom-cpp.md)|특성을 직접 정의할 수 있습니다.|  
|[db_column](../windows/db-column.md)|행 집합을 지정된 된 열에 바인딩합니다.|  
|[db_command](../windows/db-command.md)|OLE DB 명령을 만듭니다.|  
|[db_param](../windows/db-param.md)|지정 된 멤버 변수는 입력 또는 출력 매개 변수 연결 하 고 변수를 구분 합니다.|  
|[db_source](../windows/db-source.md)|데이터 원본에 대 한 연결을 만듭니다.|  
|[db_table](../windows/db-table.md)|OLE DB 테이블을 엽니다.|  
|[defaultbind](../windows/defaultbind.md)|개체에 가장 잘 나타내는 단일, 바인딩 가능 속성을 나타냅니다.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic 코드 최적화를 위해 사용 합니다.|  
|[displaybind](../windows/displaybind.md)|바인딩 가능한 사용자에 게 표시 되어야 하는 속성을 나타냅니다.|  
|[helpcontext](../windows/helpcontext.md)|사용자는 도움말 파일에서이 요소에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다.|  
|[helpfile](../windows/helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정합니다.|  
|[helpstring](../windows/helpstring.md)|적용 되는 요소에 설명 하는 데 사용 되는 문자열을 지정 합니다.|  
|[helpstringcontext](../windows/helpstringcontext.md)|.Hlp 또는.chm 파일 도움말 항목의 ID를 지정합니다.|  
|[helpstringdll](../windows/helpstringdll.md)|문서 문자열 조회 (지역화)를 수행 하는 데 DLL의 이름을 지정 합니다.|  
|[hidden](../windows/hidden.md)|항목이 존재 하지만 하지 사용자 기반 브라우저에 표시할지 나타냅니다.|  
|[ID](../windows/id.md)|멤버 함수 (속성 또는 메서드를 인터페이스 또는 dispinterface)에 대 한 DISPID를 지정합니다.|  
|[immediatebind](../windows/immediatebind.md)|데이터 바인딩된 개체의 속성에 대 한 모든 변경의 데이터베이스를 즉시 된다는 있는지를 나타냅니다.|  
|[in](../windows/in-cpp.md)|매개 변수가 호출된 된 프로시저를 호출 하는 프로시저에서 전달 하도록 임을 나타냅니다.|  
|[local](../windows/local-cpp.md)|MIDL 컴파일러 인터페이스 헤더에서 사용 될 때 헤더 생성기로 사용할 수 있습니다. 개별 함수를 사용할 경우 로컬 없는 스텁을 생성 되는 프로시저를 지정 합니다.|  
|[nonbrowsable](../windows/nonbrowsable.md)|인터페이스 멤버를 속성 브라우저에 표시 되지 해야 나타냅니다.|  
|[propget](../windows/propget.md)|속성 접근자 함수를 지정합니다.|  
|[propput](../windows/propput.md)|속성 설정 함수를 지정합니다.|  
|[propputref](../windows/propputref.md)|값을 대신 참조를 사용 하는 속성 설정 함수를 지정 합니다.|  
|[ptr](../windows/ptr.md)|전체 포인터도 포인터를 지정합니다.|  
|[range](../windows/range-cpp.md)|형식 정의 나 런타임에 해당 값이 설정 되는 필드에 대 한 허용 가능한 값의 범위를 지정 합니다.|  
|[requestedit](../windows/requestedit.md)|속성을 지원 하는지 나타냅니다는 **OnRequestEdit** 알림입니다.|  
|[restricted](../windows/restricted.md)|모듈, 인터페이스 또는 dispinterface의 멤버를 임의로 호출할 수 없도록 지정 합니다.|  
|[satype](../windows/satype.md)|데이터 형식을 지정 된 **SAFEARRAY** 구조입니다.|  
|[소스](../windows/source-cpp.md)|클래스에 연결 지점에 대 한 컨트롤의 소스 인터페이스를 지정합니다. 메서드나 속성에는 **소스** 특성 멤버 개체 또는 이벤트의 원본인 VARIANT를 반환 하는지 나타냅니다.|  
|[synchronize](../windows/synchronize.md)|대상 방법에 대 한 액세스를 동기화합니다.|  
|[vararg](../windows/vararg.md)|함수에 가변 개수의 인수 수행는 지정 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [용도별 특성](../windows/attributes-by-usage.md)