---
title: "인터넷의 ActiveX 컨트롤 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX controls [MFC], creating
- ActiveX controls [MFC], Internet
- downloading data with ActiveX controls
- OLE controls [MFC], upgrading to ActiveX
- Internet applications [MFC], ActiveX controls
- networks [MFC], downloading with ActiveX controls
ms.assetid: 7ab943c8-2022-41df-9065-d629b616eeec
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c02d807f6b77ca7aa35ffe91b929122a3743be6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="activex-controls-on-the-internet"></a>인터넷의 ActiveX 컨트롤
ActiveX 컨트롤은 OLE 컨트롤 지정의 업데이트 된 버전입니다. 컨트롤은 다양 한 인터넷에서 COM 인식 웹 브라우저를 비롯 한 다른 컨테이너에에서 사용할 수 있는 프로그래밍 가능한 소프트웨어 구성 요소를 개발 하기 위한 기본 아키텍처입니다. ActiveX 컨트롤은 인터넷 컨트롤이 될 수 있습니다 및 활성 문서에 기능을 추가 하거나 웹 페이지의 일부가 될 수 있습니다. 웹 페이지에 컨트롤은 스크립팅을 사용 하 여 서로 통신할 수 있습니다.  
  
 ActiveX 컨트롤 인터넷에 제한 되지 않습니다. ActiveX 컨트롤 사용할 수도 있습니다 모든 컨테이너에서 컨트롤에서 해당 컨테이너에 필요한 인터페이스를 지원 합니다.  
  
 **ActiveX 컨트롤을 포함 하 여 여러 가지 장점이 있습니다.**  
  
-   OLE 컨트롤을 이전 보다 필요한 인터페이스 수가 적습니다.  
  
-   항상 내부 활성화와를 창 없는 수 있는 기능입니다.  
  
 **ActiveX 컨트롤을 하기 위해 다음과 같은 컨트롤 같아야 합니다.**  
  
-   지원 된 **IUnknown** 인터페이스입니다.  
  
-   COM 개체 여야 합니다.  
  
-   내보내기 **DLLRegisterServer** 및 **DLLUnRegisterServer**합니다.  
  
-   기능에 대 한 필요에 따라 추가 인터페이스를 지원 합니다.  
  
## <a name="making-your-existing-controls-internet-friendly"></a>인터넷 환경에 기존 컨트롤을 만들기  
 인터넷에 상대적으로 낮은 전송 속도 대 한 고려 사항은 필요 인터넷 환경에서 잘 작동 하는 컨트롤을 디자인 합니다. 기존 컨트롤을 사용할 수 있습니다. 그러나 코드 크기를 작게 하 고 비동기적으로 다운로드 하 여 컨트롤 속성을 확인 하려면 수행 해야 하는 단계가 있습니다.  
  
 컨트롤의 성능을 향상 시키기 위해 효율성 고려 사항에 다음이 팁을 따릅니다.  
  
-   문서에 설명 된 기술을 구현 [ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)합니다.  
  
-   어떻게 컨트롤을 인스턴스화하는 것이 좋습니다.  
  
-   비동기; 수 다른 프로그램을 저장 하지 않으므로 합니다.  
  
-   작은 블록의에서 데이터를 다운로드 합니다.  
  
     큰 스트림을 예: 비트맵 또는 비디오 데이터를 다운로드할 때 비동기적으로 협력 하 여 컨테이너에서 컨트롤의 데이터에 액세스 합니다. 데이터도 검색 될 수 있습니다 다른 제어 기능과 함께 공동으로 작업 하는 증분 또는 점진적 동기적으로 데이터를 검색 합니다. 코드는 비동기적으로 다운로드 될 수 있습니다.  
  
-   백그라운드에서 속성 및 코드를 다운로드 합니다.  
  
-   사용자 인터페이스를 될 최대한 빨리으로 활성화 합니다.  
  
-   것이 좋습니다 (예: 비트맵 이미지 또는 비디오 데이터) 속성과 큰 데이터를 Blob 영구 데이터가 저장 되는 방법입니다.  
  
     상당한 양의 큰 비트맵 또는 AVI 파일 등의 영구 데이터를 사용 하 여 컨트롤 다운로드 방법을에 주의 필요 합니다. 문서 또는 페이지가 가능한 한 빨리 볼 수 있으며 사용자 컨트롤은 백그라운드에서 데이터를 검색 하는 동안 페이지와 상호 작용 하도록 허용 됩니다.  
  
-   효율적인 루틴 코드 크기를 유지 하 고 실행 시간을 작성 합니다.  
  
     작은 단추 및 label 컨트롤을 몇 바이트만의 지속적 데이터를 사용 하는 것은 브라우저 내 사용 하 여 인터넷 환경에서 사용 하기 위해 적합 합니다.  
  
-   컨테이너에 전달 되는 진행 하는 것이 좋습니다.  
  
     시점과 다운로드가 완료 되 면 사용자는 페이지와 상호 작용을 시작할 수 있는 시기를 포함 하 여 비동기 다운로드 진행 상황을 컨테이너를 알립니다. 컨테이너 수 진행 상황 (예: 완료율) 사용자에 게 표시 합니다.  
  
-   클라이언트 컴퓨터에 컨트롤을 등록 하는 방법을 고려해 야 합니다.  
  
## <a name="creating-a-new-activex-control"></a>새 ActiveX 컨트롤 만들기  
 응용 프로그램 마법사를 사용 하 여 새 컨트롤을 만들 때 비동기 모니커 뿐만 아니라 다른 최적화에 대 한 지원을 사용 하도록 선택할 수 있습니다. 에 컨트롤 속성을 비동기적으로 다운로드 하는 지원을 추가 하려면 다음이 단계를 수행 합니다.  
  
#### <a name="to-create-your-project-using-the-mfc-activex-control-wizard"></a>MFC ActiveX 컨트롤 마법사를 사용 하 여 프로젝트를 만들려면  
  
1.  클릭 `New` 에 **파일** 메뉴.  
  
2.  선택 **MFC ActiveX 컨트롤 마법사** Visual c + +에서 프로젝트 및 프로젝트 이름을 지정 합니다.  
  
3.  에 **제어 설정** 페이지에서 **속성을 비동기적으로 로드**합니다. 이 옵션을 선택 하면 사용자에 대 한 준비 상태 속성 및 준비 상태 변경 이벤트를 설정 합니다.  
  
     또한 선택할 수 있습니다 다른 최적화와 같은 **창 없는 활성화**에 설명 되어 있는 [ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)합니다.  
  
4.  선택 **마침** 프로젝트를 만듭니다.  
  
#### <a name="to-create-a-class-derived-from-cdatapathproperty"></a>CDataPathProperty에서 파생 된 클래스를 만들려면  
  
1.  파생 된 클래스를 만들고 `CDataPathProperty`합니다.  
  
2.  각 컨트롤에 대 한 헤더 파일이 포함 된 소스 파일에서 앞에이 클래스에 대 한 헤더 파일에 추가 합니다.  
  
3.  이 클래스에서 재정의 `OnDataAvailable`합니다. 이 함수는 데이터를 표시할 수 있는 때마다 호출 됩니다. 데이터를 사용할 수 있게 되 면을 선택 하면 예를 들어 되 어떤 방식으로 처리할 수 있습니다.  
  
     다음 코드 부분은 간단한 예제 점진적으로 편집 컨트롤에서 데이터를 표시 합니다. 플래그의 사용을 확인 **BSCF_FIRSTDATANOTIFICATION** 편집 컨트롤의 선택을 취소 합니다.  
  
     [!code-cpp[NVC_MFCActiveXControl#1](../mfc/codesnippet/cpp/activex-controls-on-the-internet_1.cpp)]  
  
     참고 AFXCMN를 포함 해야 합니다. H 사용 하 여 `CListCtrl` 클래스입니다.  
  
4.  컨트롤의 전체 상태가 변경 (예를 들어에 초기화 된 로드 또는 사용자의 대화형)을 호출 `COleControl::InternalSetReadyState`합니다. 컨트롤에는 하나의 데이터 경로 속성을 하는 경우에 코드를 추가할 수 있습니다 **BSCF_LASTDATANOTIFICATION** 다운로드가 완료 되는 컨테이너를 알릴 수 있습니다. 예:  
  
     [!code-cpp[NVC_MFCActiveXControl#2](../mfc/codesnippet/cpp/activex-controls-on-the-internet_2.cpp)]  
  
5.  `OnProgress`을 재정의합니다. `OnProgress`, 최대 범위를 표시 하는 숫자를 전달 하 고 현재 다운로드 얼마나 진행 숫자 표시 됩니다. 사용자에 게 완료율과 같은 상태를 표시 하려면이 숫자를 사용할 수 있습니다.  
  
 다음 절차 앞서 파생 시킨 클래스를 사용 하도록 컨트롤에 속성을 추가 합니다.  
  
#### <a name="to-add-a-property"></a>속성을 추가 하려면  
  
1.  **클래스 뷰**라이브러리 노드 아래에 있는 인터페이스를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가**, 다음 **속성 추가**합니다. 시작 합니다.는 **속성 추가 마법사**합니다.  
  
2.  에 **속성 추가 마법사**, 선택는 **Set/Get 메서드** 라디오 단추를 입력은 **속성 이름**, 예: EditControlText, 및는 로선택BSTR**속성 형식**합니다.  
  
3.  **마침**을 클릭합니다.  
  
4.  멤버 변수를 선언 하면 `CDataPathProperty`-ActiveX 컨트롤 클래스를 파생 클래스입니다.  
  
     [!code-cpp[NVC_MFCActiveXControl#3](../mfc/codesnippet/cpp/activex-controls-on-the-internet_3.h)]  
  
5.  구현 된 **Get/Set** 메서드. 에 대 한 **가져오기**, 문자열을 반환 합니다. 에 대 한 `Set`, 속성 및 호출 로드 `SetModifiedFlag`합니다.  
  
     [!code-cpp[NVC_MFCActiveXControl#4](../mfc/codesnippet/cpp/activex-controls-on-the-internet_4.cpp)]  
  
6.  [DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange), 다음 줄 추가:  
  
     [!code-cpp[NVC_MFCActiveXControl#5](../mfc/codesnippet/cpp/activex-controls-on-the-internet_5.cpp)]  
  
7.  재정의 [ResetData](../mfc/reference/cdatapathproperty-class.md#resetdata) 이 줄을 추가 하 여 해당 컨트롤을 다시 설정할 속성을 알릴 수 있습니다.  
  
     [!code-cpp[NVC_MFCActiveXControl#6](../mfc/codesnippet/cpp/activex-controls-on-the-internet_6.cpp)]  
  
## <a name="deciding-whether-to-derive-from-cdatapathproperty-or-ccacheddatapathproperty"></a>CDataPathProperty 또는 CCachedDataPathProperty에서 파생 여부 결정  
 이전 예제에서 컨트롤의 속성을 파생 하기 위한 단계를 설명 `CDataPathProperty`합니다. 실시간 데이터는 자주 변경 되 고 현재 값만 않는 모든 데이터를 유지 하지 필요가 다운로드 하는 경우에 적합 한 선택입니다. 예로 주식 시세 컨트롤입니다.  
  
 또한에서 파생 시켜 `CCachedDataPathProperty`합니다. 이 경우 다운로드 한 데이터가 메모리 파일에 캐시 됩니다. 다운로드 한 모든 데이터를 유지 하는 경우이 좋은 선택-점진적으로 비트맵을 렌더링 하는 컨트롤 예를 들어 있습니다. 이 경우 클래스에는 데이터를 포함 하는 멤버 변수.  
  
 `CMemFile m_Cache;`  
  
 ActiveX 컨트롤 클래스를 사용 하 여이 메모리 매핑된 파일에 사용할 수 있습니다 `OnDraw` 데이터를 표시 합니다. ActiveX 컨트롤에서 `CCachedDataPathProperty`-파생 클래스 멤버 함수를 재정의 `OnDataAvailable` 기본 클래스 구현을 호출 후 컨트롤을 무효화 합니다.  
  
 [!code-cpp[NVC_MFCActiveXControl#7](../mfc/codesnippet/cpp/activex-controls-on-the-internet_7.cpp)]  
  
## <a name="downloading-data-asynchronously-using-activex-controls"></a>ActiveX 컨트롤을 사용 하 여 비동기적으로 데이터를 다운로드 합니다.  
 비동기적으로 네트워크를 통해 데이터를 다운로드를 수행 합니다. 그렇게 하므로 하는 경우 많은 양의 데이터를 전송 하거나 연결이 느린 경우 다운로드 프로세스는 클라이언트에 있는 다른 프로세스를 차단 하지 것입니다.  
  
 비동기 모니커는 네트워크를 통해 데이터를 비동기적으로 다운로드 하는 방법을 제공 합니다. 비동기 모니커 읽기 작업은 작업이 완료 되지 않은 경우에 즉시 반환 합니다.  
  
 예를 들어 10 바이트 사용할 수 있고 읽기 1k 파일에 비동기적으로 호출 되 읽기 차단 되지 않는 아니지만 현재 사용할 수 있는 10 바이트를 반환 합니다.  
  
 구현 [비동기 모니커](../mfc/asynchronous-monikers-on-the-internet.md) 를 사용 하 여 `CAsyncMonikerFile` 클래스입니다. 그러나 ActiveX 컨트롤을 사용할 수는 `CDataPathProperty` 클래스에서 파생 된 `CAsyncMonikerFile`, 비동기 컨트롤 속성을 구현할 수 있도록 합니다.  
  
 ASYNDOWN 샘플 데이터를 읽을 타이머를 사용 하는 비동기 루프를 설정 하는 방법을 보여 줍니다. ASYNDOWN "방법:: AsyncDown에서는 비동기 데이터 다운로드" (Q177244) 기술 자료 문서에 자세히 설명 되어 이며 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. (Microsoft 다운로드 센터에서 파일을 다운로드 하는 방법에 대 한 자세한 내용은 "방법 가져올 Microsoft 지원 파일에서 온라인 서비스" (Q119591) Microsoft 기술 자료 문서 참조). 기술 자료 문서를 찾을 수 [http://support.microsoft.com/support](http://support.microsoft.com/support)합니다.  
  
 타이머를 설정 하는 ASYNDOWN에 사용 되는 기본 기술은 **CDataPathProperty::OnDataAvailable** 를 나타내는 데이터를 사용할 수 있습니다. 타이머 메시지를 받으면 응용 프로그램 데이터는 128 바이트 블록에서 읽고 편집 컨트롤을 채웁니다. 데이터를 사용할 수 없는 타이머 메시지를 처리할 때 사용 되는 타이머 꺼져 있습니다. `OnDataAvailable`나중에 도착 하면 더 많은 데이터가 사용 되는 타이머를 설정 합니다.  
  
## <a name="displaying-a-control-on-a-web-page"></a>웹 페이지에 컨트롤 표시  
 개체 태그 및 웹 페이지에 컨트롤 삽입에 대 한 특성의 예를 들면 다음과 같습니다.  
  
 `<OBJECT`  
  
 `CLASSID="clsid:FC25B780-75BE-11CF-8B01-444553540000"`  
  
 `CODEBASE="/ie/download/activex/iechart.ocx"`  
  
 `ID=chart1`  
  
 `WIDTH=400`  
  
 `HEIGHT=200`  
  
 `ALIGN=center`  
  
 `HSPACE=0`  
  
 `VSPACE=0`  
  
 `>`  
  
 `<PARAM NAME="BackColor" value="#ffffff">`  
  
 `<PARAM NAME="ForeColor" value="#0000ff">`  
  
 `<PARAM NAME="url" VALUE="/ie/controls/chart/mychart.txt">`  
  
 `</OBJECT>`  
  
## <a name="updating-an-existing-ole-control-to-use-new-activex-control-features"></a>ActiveX 컨트롤의 새로운 기능을 사용 하는 기존 OLE 컨트롤 업데이트  
 OLE 컨트롤 4.2 이전 버전의 Visual c + +로 만든 경우 해당 성능을 개선 하 고 기능을 향상을 위해 수행할 수 있는 단계가 있습니다. 이러한 변경의 자세한 논의 알려면 [ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)합니다.  
  
 준비 상태 속성을 추가 해야 기존 컨트롤에 비동기 속성 지원을 추가 하는 경우 및 `ReadyStateChange` 이벤트 직접 합니다. 컨트롤에 대 한 생성자를 추가 합니다.  
  
 [!code-cpp[NVC_MFCActiveXControl#8](../mfc/codesnippet/cpp/activex-controls-on-the-internet_8.cpp)]  
  
 코드를 호출 하 여 다운로드는 준비 상태를 업데이트 합니다 [COleControl::InternalSetReadyState](../mfc/reference/colecontrol-class.md#internalsetreadystate)합니다. 한 곳을 호출할 수 있습니다 `InternalSetReadyState` 에서 보낸는 `OnProgress` 의 재정의 `CDataPathProperty`-클래스를 파생 합니다.  
  

  
## <a name="see-also"></a>참고 항목  
 [MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)   
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)

