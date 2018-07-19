---
title: 'MFC ActiveX 컨트롤: 직렬화 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- _wVerMinor
- DoPropExchange
- _wVerMajor
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], version support
- wVerMinor global constant [MFC]
- GetVersion method [MFC]
- ExchangeVersion method [MFC]
- MFC ActiveX controls [MFC], serializing
- DoPropExchange method [MFC]
- versioning ActiveX controls
- wVerMajor global constant
ms.assetid: 9d57c290-dd8c-4853-b552-6f17f15ebedd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9db6ff6c0cdda01875e4968e4d92ca087ad2b57
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930063"
---
# <a name="mfc-activex-controls-serializing"></a>MFC ActiveX 컨트롤: Serialize
이 문서에서는 ActiveX 컨트롤을 serialize 하는 방법을 설명 합니다. Serialization은 프로세스에서 읽기 또는 쓰기를 영구 저장 매체에 디스크 파일 등입니다. Microsoft Foundation 클래스 (MFC) 라이브러리는 클래스의 serialization에 대 한 기본 제공 지원 `CObject`합니다. `COleControl` ActiveX 컨트롤 속성 교환 메커니즘을 사용 하 여이 지원이 확장 합니다.  
  
 ActiveX 컨트롤에 대 한 직렬화를 재정의 하 여 구현 됩니다 [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange)합니다. 이 함수는 로드 하는 동안 호출 하 고 멤버 변수 또는 변경 알림 사용 하 여 멤버 변수를 사용 하 여 구현 하는 모든 속성을 저장 컨트롤 개체의 저장 합니다.  
  
 다음 항목에서는 ActiveX 컨트롤을 직렬화와 관련 된 주요 문제를 설명 합니다.  
  
-   구현 `DoPropExchange` 컨트롤 개체를 serialize 하는 함수  
  
-   [Serialization 프로세스를 사용자 지정](#_core_customizing_the_default_behavior_of_dopropexchange)  
  
-   [버전 지원 구현](#_core_implementing_version_support)  
  
##  <a name="_core_implementing_the_dopropexchange_function"></a> DoPropExchange 함수 구현  
 기본 구현을 포함 하 여 컨트롤 클래스에 몇 가지 기본 처리기 함수는 자동으로 추가 ActiveX 컨트롤 마법사를 사용 하 여 컨트롤 프로젝트를 생성 하는 경우 [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange)합니다. 다음 예제에서는 ActiveX 컨트롤 마법사를 사용 하 여 만든 클래스에 추가 된 코드를 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]  
  
 영구 속성을 확인 하려는 경우 수정 `DoPropExchange` 속성 exchange 함수에 대 한 호출을 추가 하 여 합니다. 다음 예제에서는 CircleShape 속성의 기본값에 있는 사용자 지정 부울 CircleShape 속성의 serialization **TRUE**:  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]  
  
 다음 표에 컨트롤의 속성을 serialize 하는 데 사용할 수 있는 속성 교환 함수가 있습니다.  
  
|속성 교환 함수|용도|  
|---------------------------------|-------------|  
|**PX_Blob)**|큰 BLOB (Binary Object) 데이터 속성 형식을 serialize합니다.|  
|**PX_Bool)**|형식이 부울 속성을 serialize합니다.|  
|**PX_Color)**|형식 color 속성을 serialize합니다.|  
|**PX_Currency)**|형식을 serialize **CY** (currency) 속성입니다.|  
|**PX_Double)**|형식을 serialize **double** 속성입니다.|  
|**PX_Font)**|글꼴 유형 속성을 serialize합니다.|  
|**PX_Float)**|형식을 serialize **float** 속성입니다.|  
|**PX_IUnknown)**|유형의 속성을 직렬화 `LPUNKNOWN`합니다.|  
|**PX_Long)**|형식을 serialize **긴** 속성입니다.|  
|**PX_Picture)**|형식 그림 속성을 serialize합니다.|  
|**PX_Short)**|형식을 serialize **짧은** 속성입니다.|  
|**PXstring)**|형식을 serialize `CString` 속성입니다.|  
|**PX_ULong)**|형식을 serialize **ULONG** 속성입니다.|  
|**PX_UShort)**|형식을 serialize **USHORT** 속성입니다.|  
  
 이러한 속성 exchange 함수에 대 한 자세한 내용은 참조 하십시오. [지 속성 OLE 컨트롤의](../mfc/reference/persistence-of-ole-controls.md) 에 *MFC 참조*합니다.  
  
##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a> DoPropExchange의 기본 동작을 사용자 지정  
 기본 구현은 `DoPropertyExchange` (에서처럼 이전 항목)에서 기본 클래스를 호출할 `COleControl`합니다. 이 serialize에서 자동으로 지원 되는 속성 집합이 `COleControl`, 컨트롤의 사용자 지정 속성만 직렬화 하는 작업 보다 더 많은 저장소 공간을 사용 하 합니다. 이 호출을 제거 하면 중요 한 고려 속성만 serialize 개체가 있습니다. 컨트롤에 구현 된 스톡 속성 상태 저장 하거나 명시적으로 추가 하지 않는 한 컨트롤 개체를 로드할 때 serialize 되지 것입니다 **PX_** 을 호출 합니다.  
  
##  <a name="_core_implementing_version_support"></a> 버전 지원 구현  
 버전 지원을 통해 수정 된 ActiveX 컨트롤을을 새 영구적 속성을 추가 하 고 여전히를 감지 하 여 컨트롤의 이전 버전에서 만든 영구 상태를 로드할 수 있습니다. 컨트롤의 버전을 사용할 수 있도록 하려면 자체 영구 데이터의 일부로 호출 [COleControl::ExchangeVersion](../mfc/reference/colecontrol-class.md#exchangeversion) 컨트롤의 `DoPropExchange` 함수입니다. 이 호출은 ActiveX 컨트롤을 ActiveX 컨트롤 마법사를 사용 하 여 만들어진 경우에 자동으로 삽입 됩니다. 버전 지원에 필요 하지 않은 경우 제거할 수 있습니다. 그러나 컨트롤 크기에 비용은 매우 작은 (4 바이트) 유연성이 버전 지원을 제공 합니다.  
  
 컨트롤은 ActiveX 컨트롤 마법사로 만들어지지 않았으므로 하는 경우 한 호출을 추가 `COleControl::ExchangeVersion` 맨 앞에 다음 줄을 삽입 하 여 프로그램 `DoPropExchange` 함수 (호출 하기 전에 `COleControl::DoPropExchange`):  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 사용할 수 있습니다 **DWORD** 버전 번호입니다. ActiveX 컨트롤 마법사에 의해 생성 된 프로젝트를 사용 하 여 `_wVerMinor` 및 `_wVerMajor` 기본값으로 합니다. 이들은 프로젝트의 ActiveX 컨트롤 클래스의 구현 파일에 정의 된 전역 상수입니다. 나머지 부분 내에서 프로그램 `DoPropExchange` 함수를 호출할 수 있습니다 [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion) 언제 든 지 저장 하거나 검색 하는 버전을 검색 합니다.  
  
 다음 예제에서는이 샘플 컨트롤의 버전 1에는 "ReleaseDate" 속성만 있습니다. 버전 2는 "OriginalDate" 속성을 추가합니다. 컨트롤은 이전 버전에서 영구 상태를 로드를 시작 하는 경우 기본값을 새 속성에 대 한 멤버 변수를 초기화 합니다.  
  
 [!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 기본적으로 컨트롤 "변환" 오래 된 데이터를 최신 형식입니다. 예를 들어 버전 2는 컨트롤의 버전 1에 의해 저장 된 데이터를 로드 되 면 다시 저장 될 때 버전 2 형식을 기록 합니다. 컨트롤 형식 마지막 읽기에서 데이터를 저장 하려는 경우 전달 **FALSE** 를 호출할 때 세 번째 매개 변수로 `ExchangeVersion`합니다. 이 세 번째 매개 변수는 선택적 이며이 **TRUE** 기본적으로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

