---
title: "MFC ActiveX 컨트롤: ActiveX 컨트롤 지역화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LocaleID
- AfxOleRegisterTypeLib
dev_langs:
- C++
helpviewer_keywords:
- localization, ActiveX controls
- MFC ActiveX controls [MFC], localizing
- LocaleID ambient property [MFC]
- LOCALIZE sample [MFC]
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd6384507982f74e02e8e4f42c97926f9125981e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤 지역화
이 문서에서는 ActiveX 컨트롤 인터페이스의 지역화를 위한 절차를 설명 합니다.  
  
 국제 시장에 ActiveX 컨트롤을 조정 하려는 경우에 컨트롤을 지역화 하는 것이 좋습니다. Windows 기본 영어, 독일어, 프랑스어 및 스웨덴어를 포함 하 여 외에도 많은 언어를 지원 합니다. 따라서 해당 인터페이스는 영어로 하는 경우 컨트롤에 대 한 문제가 발생할 수 있습니다.  
  
 일반적으로 ActiveX 컨트롤 LocaleID 앰비언트 속성에 해당 로캘을 기반 항상 해야 합니다. 이렇게 하는 데는 다음과 같은 세 가지 방법이 있습니다.  
  
-   LocaleID 앰비언트 속성의 현재 값에 따라 요청 시 항상 리소스를 로드 합니다. MFC ActiveX 컨트롤 샘플 [LOCALIZE](../visual-cpp-samples.md) 이 전략을 사용 합니다.  
  
-   첫 번째 컨트롤은 인스턴스를 만들 경우, LocaleID 앰비언트 속성에 따라 리소스를 로드 하 고 다른 모든 인스턴스에 대 한 이러한 리소스를 사용 합니다. 이 문서에서는이 전략을 보여줍니다.  
  
    > [!NOTE]
    >  이 제대로 작동 하지 일부 경우에 더 이상 서로 다른 로캘을 하는 경우.  
  
-   사용 하 여는 **OnAmbientChanged** 알림 함수를 동적으로 컨테이너의 로캘에 대 한 적절 한 리소스를 로드 합니다.  
  
    > [!NOTE]
    >  이 연결은 컨트롤을 사용할 수 있지만 LocaleID 앰비언트 속성이 변경 될 때 런타임 DLL 동적으로 자체 리소스를 업데이트 하지는 않습니다. 또한 ActiveX 컨트롤 런타임 Dll은 스레드 로컬을 사용 하 여 해당 리소스에 대 한 로캘을 결정 합니다.  
  
 이 문서의 나머지 부분에서는 두 개의 지역화 전략을 설명 합니다. 첫 번째 전략 [컨트롤의 프로그래밍 기능 인터페이스 보여지는](#_core_localizing_your_control.92.s_programmability_interface) (속성, 메서드 및 이벤트의 이름). 두 번째 전략 [컨트롤의 사용자 인터페이스 보여지는](#_core_localizing_the_control.92.s_user_interface), 컨테이너의 앰비언트 LocaleID 속성을 사용 합니다. 컨트롤 지역화의 데모를 보려면 MFC ActiveX 컨트롤 샘플을 참조 [LOCALIZE](../visual-cpp-samples.md)합니다.  
  
##  <a name="_core_localizing_your_control.92.s_programmability_interface"></a>컨트롤의 프로그래밍 기능 인터페이스를 지역화합니다.  
 컨트롤의 프로그래밍 인터페이스 (프로그래머가 컨트롤을 사용 하는 응용 프로그램에서 사용 하는 인터페이스)를 지역화 하는 경우 컨트롤의 수정된 버전을 만들어야 합니다. IDL 지원 하려는 각 언어에 대 한 (컨트롤 형식 라이브러리를 작성 하기 위한 스크립트) 파일입니다. 컨트롤 속성 이름을 지역화 하려면 유일한 자리입니다.  
  
 지역화 된 컨트롤을 개발할 때 형식 라이브러리 수준에서 특성으로 로캘 ID를 포함 합니다. 예를 들어 프랑스 지역화 된 속성 이름이 포함 된 형식 라이브러리에 제공 하려는 경우 샘플의 복사본을 만듭니다. IDL 파일을 찾아 SAMPLEFR 호출 합니다. IDL 합니다. 로캘 ID 특성 (프랑스어에 대 한 로캘 ID은 0x040c) 파일을 추가 다음과 비슷합니다.  
  
 [!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]  
  
 SAMPLEFR에 속성 이름을 변경 합니다. 프랑스 관련 정보 및 다음 사용 하 여 MKTYPLIB IDL 합니다. 프랑스 되려면 EXE 형식 라이브러리를 SAMPLEFR입니다. TLB 합니다.  
  
 여러 지역화 된 형식 라이브러리를 만들려면 어떤 지역화를 추가할 수 있습니다. IDL 파일을 프로젝트와은 자동으로 생성 됩니다.  
  
#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>추가 하는 합니다. ActiveX 컨트롤 프로젝트에 대 한 IDL 파일  
  
1.  컨트롤 프로젝트를 열고에 **프로젝트** 메뉴를 클릭 하 여 **기존 항목 추가**합니다.  
  
     **기존 항목 추가** 대화 상자가 나타납니다.  
  
2.  필요한 경우에 드라이브 및 디렉터리를 선택 합니다.  
  
3.  에 **파일 형식** 상자 **모든 파일 (\*.\*)** .  
  
4.  파일 목록 상자에서 두 번 클릭 하 고 있습니다. IDL 파일을 프로젝트에 삽입 합니다.  
  
5.  클릭 **열려** 때 필요한 모든 추가 했습니다. IDL 파일입니다.  
  
 파일을 프로젝트에 추가 되어, 나머지 프로젝트를 빌드할 때 빌드됩니다. 지역화 된 형식 라이브러리 현재 ActiveX 컨트롤 프로젝트 디렉터리에 있습니다.  
  
 프로그램 코드 내에서 내부 속성 이름 (일반적으로 영어로)를 항상 사용 및 지역화 되지 않습니다. 컨트롤 디스패치 맵, 속성 exchange 함수 및 속성 페이지 데이터 교환 코드를 포함 합니다.  
  
 하나의 형식 라이브러리 (합니다. TLB) 파일로 컨트롤 구현 하는 리소스에 바인딩될 수도 있습니다 (합니다. OCX) 파일입니다. 이 일반적으로 표준화 된 버전 (일반적으로 영어) 이름입니다. 지역화 된 버전을 제공 하려면 컨트롤을 제공 하는 합니다. OCX (함 이미에 바인딩된 기본값입니다. TLB 버전) 및 합니다. 에 대 한 적절 한 로캘로 TLB 합니다. 즉는 합니다. 영어 버전에 대 한 올바른 이후 OCX 필요 합니다. TLB에 이미 바인딩 되었습니다. 지역화 된 형식 라이브러리도 다른 로캘의 함께 출고 되어야 합니다는 합니다. OCX 합니다.  
  
 컨트롤의 클라이언트가 지역화 된 형식 라이브러리를 찾을 수 있도록 하려면 로캘 관련을 등록 합니다. Windows 시스템 레지스트리 TypeLib 섹션 아래의 TLB 파일. 세 번째의 매개 변수 (일반적으로 선택 사항)는 [AfxOleRegisterTypeLib](../mfc/reference/registering-ole-controls.md#afxoleregistertypelib) 함수는이 목적을 위해 제공 됩니다. 다음 예제에서는 ActiveX 컨트롤에 대 한 프랑스 형식 라이브러리를 등록 합니다.  
  
 [!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]  
  
 컨트롤 등록 되는 `AfxOleRegisterTypeLib` 함수는 지정 된 항목에 대 한 자동으로 찾습니다. TLB 파일 컨트롤와 동일한 디렉터리에 Windows 등록 데이터베이스에 등록 합니다. 경우는 합니다. TLB 파일을 찾을 수 없습니다, 함수에 영향을 주지 않습니다.  
  
##  <a name="_core_localizing_the_control.92.s_user_interface"></a>컨트롤의 사용자 인터페이스를 지역화합니다.  
 컨트롤의 사용자 인터페이스를 지역화 하려면 언어 관련 리소스 Dll에 모든 컨트롤의 사용자가 볼 수 리소스 (예: 속성 페이지 및 오류 메시지)를 배치 합니다. 그런 다음 사용자 로캘에 대 한 적절 한 DLL을 선택 하는 컨테이너의 앰비언트 LocaleID 속성을 사용할 수 있습니다.  
  
 다음 코드 예제를 찾아 특정 로캘에 대 한 리소스 DLL을 로드 하는 한 가지 방법을 보여 줍니다. 이 멤버 함수를 호출 `GetLocalizedResourceHandle` 이 예에서는 ActiveX 컨트롤 클래스의 멤버 함수를 수 있습니다.  
  
 [!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]  
  
 Note 각각의 경우 switch 문의 더 특수 한 지역화를 제공 하는 하위 언어 ID를 확인할 수 없습니다. 이 함수의 데모를 보려면 참조는 `GetResourceHandle` 함수에서 MFC ActiveX 컨트롤 샘플 [LOCALIZE](../visual-cpp-samples.md)합니다.  
  
 호출할 수 있는 컨트롤 처음 로드 될 때 자체는 컨테이너로, [COleControl::AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid) 로캘 ID를 검색 컨트롤이 반환 된 로캘 ID 값을 전달할 수는 `GetLocalizedResourceHandle` 적절 한 리소스 라이브러리를 로드 하는 함수입니다. 컨트롤이 있는 경우 결과 핸들을 전달 해야를 [AfxSetResourceHandle](../mfc/reference/application-information-and-management.md#afxsetresourcehandle):  
  
 [!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]  
  
 멤버 함수 재정의 하는 예를 들어 위의 코드 샘플을 넣는 [COleControl::OnSetClientSite](../mfc/reference/colecontrol-class.md#onsetclientsite)합니다. 또한 `m_hResDLL` 컨트롤 클래스의 멤버 변수 여야 합니다.  
  
 컨트롤의 속성 페이지의 지역화를 위한 유사한 논리를 사용할 수 있습니다. 속성 페이지를 지역화 하려면 다음 샘플과 유사한 코드 속성 페이지의 구현 파일에 추가 합니다 (재정의에서 [COlePropertyPage::OnSetPageSite](../mfc/reference/colepropertypage-class.md#onsetpagesite)):  
  
 [!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

