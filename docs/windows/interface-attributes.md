---
title: 인터페이스 특성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6f57cdce20a54b8bc56b804e12f59f92855c7f69
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880207"
---
# <a name="interface-attributes"></a>인터페이스 특성
다음과 같은 특성에 적용 된 [인터페이스 (또는 __interface)](../cpp/interface.md) c + + 키워드입니다.  
  
|특성|설명|  
|---------------|-----------------|  
|[async_uuid](../windows/async-uuid.md)|동기 및 비동기 버전 COM 인터페이스의 정의 MIDL 컴파일러에 지시 하 UUID를 지정 합니다.|  
|[custom](../windows/custom-cpp.md)|사용자 지정 특성을 정의할 수 있습니다.|  
|[dispinterface](../windows/dispinterface.md)|.Idl 파일의 인터페이스를 디스패치 인터페이스로 배치합니다.|  
|[dual](../windows/dual.md)|.Idl 파일에는 이중 인터페이스로 인터페이스를 배치합니다.|  
|[export](../windows/export.md)|데이터 구조는.idl 파일에 배치 하면 됩니다.|  
|[helpcontext](../windows/helpcontext.md)|사용자는 도움말 파일에서이 요소에 대 한 정보를 볼 수 있는 컨텍스트 ID를 지정 합니다.|  
|[helpfile](../windows/helpfile.md)|형식 라이브러리에 대 한 도움말 파일의 이름을 설정합니다.|  
|[helpstring](../windows/helpstring.md)|적용 되는 요소에 설명 하는 데 사용 되는 문자열을 지정 합니다.|  
|[helpstringcontext](../windows/helpstringcontext.md)|.Hlp 또는.chm 파일 도움말 항목의 ID를 지정합니다.|  
|[helpstringdll](../windows/helpstringdll.md)|문서 문자열 조회 (지역화)를 수행 하는 데 DLL의 이름을 지정 합니다.|  
|[hidden](../windows/hidden.md)|항목이 존재 하지만 하지 사용자 기반 브라우저에 표시할지 나타냅니다.|  
|[library_block](../windows/library-block.md)|.Idl 파일의 라이브러리 블록 내부는 구문을 배치합니다.|  
|[local](../windows/local-cpp.md)|MIDL 컴파일러 인터페이스 헤더에서 사용 될 때 헤더 생성기로 사용할 수 있습니다. 개별 함수를 사용할 경우 로컬 없는 스텁을 생성 되는 프로시저를 지정 합니다.|  
|[nonextensible](../windows/nonextensible.md)|지정 된 `IDispatch` 구현 속성만 포함 및 메서드와 인터페이스 설명에 나열 된 추가 멤버와 런타임 시 확장할 수 없습니다. 이 특성에만 사용할 수는 [이중](../windows/dual.md) 인터페이스입니다.|  
|[odl](../windows/odl.md)|개체 설명 언어 ODL () 인터페이스는 인터페이스를 식별합니다.|  
|[object](../windows/object-cpp.md)|사용자 지정 인터페이스를 식별합니다.|  
|[oleautomation](../windows/oleautomation.md)|자동화 호환 인터페이스를 나타냅니다.|  
|[pointer_default](../windows/pointer-default.md)|매개 변수 목록에 표시 되는 최상위 포인터를 제외 하 고 모든 포인터에 대 한 기본 포인터 특성을 지정 합니다.|  
|[ptr](../windows/ptr.md)|전체 포인터도 포인터를 지정합니다.|  
|[restricted](../windows/restricted.md)|라이브러리의 멤버를 임의로 호출할 수 없도록 지정 합니다.|  
|[uuid](../windows/uuid-cpp-attributes.md)|라이브러리에 대 한 고유 ID를 제공합니다.|  
  
 인터페이스 정의 대 한 이러한 규칙을 준수 해야 합니다.  
  
-   기본 호출 규칙은 [__stdcall](../cpp/stdcall.md)합니다.  
  
-   GUID는 제공 하지 않으면 드립니다 제공 됩니다.  
  
-   오버 로드 된 메서드가 없는 허용 됩니다.  
  
 지정 하지 않는 경우는 [uuid](../windows/uuid-cpp-attributes.md) 특성 및 서로 다른 특성을 프로젝트에서 동일한 인터페이스 이름을 사용 하는 동일한 GUID가 생성 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [용도별 특성](../windows/attributes-by-usage.md)