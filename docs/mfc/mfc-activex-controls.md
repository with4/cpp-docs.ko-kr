---
title: "MFC ActiveX 컨트롤 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MFC ActiveX Controls (MFC)"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], MFC"
  - "COleControl 클래스, MFC ActiveX 컨트롤"
  - "컨테이너[C++], MFC ActiveX 컨트롤"
  - "디스패치 맵, MFC ActiveX 컨트롤"
  - "이벤트[C++], ActiveX 컨트롤"
  - "MFC ActiveX 컨트롤[C++]"
  - "MFC ActiveX 컨트롤[C++], 활성/비활성 상태"
  - "MFC ActiveX 컨트롤[C++], 컨테이너"
  - "MFC ActiveX 컨트롤[C++], serialize"
  - "serialization[C++], MFC ActiveX 컨트롤"
ms.assetid: c911fb74-3afc-4bf3-a0f5-7922b14d9a1b
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# MFC ActiveX 컨트롤
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX 컨트롤은 광범위한 OLE 기능을 지원하고 다양한 소프트웨어의 요구 사항에 맞게 사용자 지정할 수 있는 COM\(구성 요소 개체 모델\) 기반의 다시 사용 가능한 소프트웨어 구성 요소입니다.  ActiveX 컨트롤은 일반적인 ActiveX 컨트롤 컨테이너와 인터넷의 World Wide Web 웹 페이지 모두에 사용할 수 있도록 디자인되었습니다.  여기에 설명된 MFC나 [액티브 템플릿 라이브러리 \(ATL\)](../atl/active-template-library-atl-concepts.md)로 ActiveX 컨트롤을 만들 수 있습니다.  
  
 ActiveX 컨트롤은 해당 창에서 이벤트\(예: 마우스 클릭\)에 응답하여 호출될 수 있으며, 자동화 객체와 유사한 속성과 메서드를 포함한 인터페이스를 통해 관리할 수 있습니다.  
  
 이러한 컨트롤은 데이터베이스 접근, 데이터 모니터링 또는 그래프 등의 여러 가지 용도로 개발될 수 있습니다.  ActiveX 컨트롤은 이식성 외에도 이전에는 가능하지 않았던 기존 OLE 컨테이너와의 호환성과, 기존 OLE 컨테이너 메뉴와의 통합 기능 등을 지원합니다.  또한 ActiveX 컨트롤은 컨트롤이 읽기\/쓰기 속성 및 컨트롤 사용자가 호출할 수 있는 메서드 집합을 노출하도록 허용하는 자동화 기능을 완벽하게 지원합니다.  
  
 창 없는 ActiveX 컨트롤과 활성화 될 때만 창을 만드는 컨트롤을 만들 수 있습니다.  창 없는 컨트롤은 응용 프로그램의 표시 속도를 높이며 투명하고 사각형 모양이 아닌 컨트롤을 만들 수 있게 합니다.  ActiveX 컨트롤 속성을 비동기적으로 불러올 수도 있습니다.  
  
 ActiveX 컨트롤은 OLE 컨테이너에서 사용할 수 있는 in\-process 서버 \(일반적으로 작은 개체\) 로 구현됩니다.  ActiveX 컨트롤의 전체 기능은 ActiveX 컨트롤을 인식하도록 설계된 OLE 컨테이너 내에서 사용하는 경우에 사용할 수 있음을 주의하십시오.  ActiveX 컨트롤을 지원하는 컨테이너 목록을 보려면 [ActiveX 컨트롤을 다른 응용 프로그램에 포팅](../mfc/containers-for-activex-controls.md)을 참고하십시오.  이 컨테이너 형식\(이하 "컨트롤 컨테이너"\)는 컨트롤의 속성 및 메서드를 사용하여 ActiveX 컨트롤을 작동할 수 있으며, 이벤트의 양식으로 ActiveX 컨트롤에서 알림을 받습니다.  다음 구조도는 이 상호작용을 보여줍니다.  
  
 ![ActiveX 컨트롤 컨테이너 및 컨트롤의 상호 작용](../mfc/media/vc37221.png "vc37221")  
ActiveX 컨트롤 컨테이너와 창 있는 ActiveX 컨트롤 간의 상호 작용  
  
 ActiveX 컨트롤 최적화에 대한 최신 정보를 보려면 [MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)를 참조하십시오.  
  
 MFC ActiveX 컨트롤을 만들기 위해서는 [ActiveX 컨트롤 프로젝트 만들기](../mfc/reference/mfc-activex-control-wizard.md)를 참조하십시오.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)  
  
-   [액티브 문서](../mfc/active-documents.md)  
  
-   [ActiveX 컨트롤 사용](../data/ado-rdo/using-activex-controls.md)  
  
-   [\<caps:sentence id\="tgt23" sentenceid\="e07c7a1ebdac21120a91f75018670c81" class\="tgtSentence"\>ActiveX 컨트롤에 대한 이해\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms693753)  
  
-   [인터넷에서 사용하기 위한 기존 ActiveX 컨트롤의 업그레이드](../mfc/upgrading-an-existing-activex-control.md)  
  
##  <a name="_core_basic_components_of_an_activex_control"></a> ActiveX 컨트롤의 기본 구성 요소  
 ActiveX 컨트롤은 컨트롤 컨테이너와 사용자 간의 효율적인 상호 작용을 위하여 몇 가지 프로그래밍 요소를 사용합니다.  이들은 클래스 [COleControl](../mfc/reference/colecontrol-class.md), 이벤트 발생 기능의 집합과 디스패치 맵입니다.  
  
 개발되는 모든 ActiveX 컨트롤 개체는 MFC 기본 클래스인 `COleControl`에서 강력한 기능 집합을 상속받습니다.  이러한 기능에는 현재 위치에서 활성화 및 자동화 논리가 포함됩니다.  `COleControl`는 MFC 창 개체와 동일한 기능에 이벤트를 발생시킬 수 기능이 추가된 컨트롤 개체를 제공할 수 있습니다.  `COleControl`는 또한 [창 없는 컨트롤](../mfc/providing-windowless-activation.md)을 제공합니다. 창 없는 컨트롤은 창이 제공하는 일부 기능\(마우스 캡쳐, 키보드 초점, 스크롤링\)은 해당 컨테이너에 의존하지만, 훨씬 빠른 화면 표시를 제공합니다.  
  
 `COleControl`에서 나온 컨트롤 클래스이기 때문에, 이는 특정한 조건이 만족됐을 경우 컨트롤 컨테이너에게 메시지를 보내거나 "발생"시키고, 이벤트를 호출하는 기능을 상속합니다.  이러한 이벤트는 컨트롤에서 중요한 일이 발생했을 경우 컨트롤 컨테이너를 통지하는 데에 사용됩니다.  매개 변수를 이벤트에 연결하는 방법으로 이벤트에 관한 추가적인 정보를 컨트롤 컨테이너에 보낼 수 있습니다.  ActiveX 컨트롤의 이벤트에 대한 추가 정보는 [MFC ActiveX 컨트롤: 이벤트](../mfc/mfc-activex-controls-events.md) 문서를 참조하십시오.  
  
 마지막 요소인 디스패치 맵은 함수\(메서드라고 함\)와 특성\(속성 이라고 함\)의 집합을 컨트롤 사용자에게 보여주는 데에 사용됩니다.  속성은 컨트롤 컨테이너 또는 컨트롤 사용자가 다양한 방법으로 컨트롤을 조작할 수 있도록 합니다.  사용자는 컨트롤의 외관, 특정한 값을 변경할 수 있으며, 컨트롤이 유지하는 데이터의 특정 부분에 액세스하도록 하는 컨트롤을 요청할 수 있습니다.  이 인터페이스는 컨트롤 개발자에 의해 결정되며, **클래스 뷰**를 이용하여 정의됩니다.  ActiveX 컨트롤의 메서드 및 속성에 대한 자세한 내용은 [MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md) 및 [속성](../mfc/mfc-activex-controls-properties.md) 문서를 참조하십시오.  
  
##  <a name="_core_interaction_between_controls_with_windows_and_activex_control_containers"></a> Windows 컨트롤과 ActiveX 컨트롤 컨테이너의 상호 작용  
 컨트롤 컨테이너에서 컨트롤을 사용하는 경우, 통신을 위해 두 가지 메커니즘을 사용합니다. 속성 및 메서드를 노출하고 이벤트를 발생시킵니다.  다음 그림은 이러한 두 가지 메커니즘이 어떻게 구현되는지를 보여줍니다.  
  
 ![ActiveX 컨트롤은 해당 컨테이너와 통신합니다.](../mfc/media/vc37222.png "vc37222")  
ActiveX 컨트롤 컨테이너와 ActiveX 컨트롤 간의 통신  
  
 위 그림은 또한 다른 OLE 인터페이스가 \(자동화 및 이벤트와 비교하여\) 어떻게 컨트롤에 의해 처리되는지를 보여줍니다.  
  
 컨테이너를 이용한 모든 컨트롤의 통신은 `COleControl`에 의해 수행됩니다.  컨테이너의 몇몇 요청을 처리하기 위해 **COleControl**은 컨트롤 클래스에서 구현되는 멤버 함수를 호출합니다.  모든 메서드와 일부 속성은 이러한 방식으로 처리 됩니다.  컨트롤 클래스는 `COleControl`의 멤버 함수를 호출하여 컨테이너와 통신을 시작할 수도 있습니다.  이러한 방식으로 이벤트가 발생합니다.  
  
##  <a name="_core_active_and_inactive_states_of_an_activex_control"></a> ActiveX 컨트롤의 활성 및 비활성 상태  
 컨트롤은 활성 및 비활성의 두 가지 기본 상태를 가집니다.  전통적으로, 이러한 상태는 컨트롤이 창을 가졌는지의 여부에 의해 구별됩니다.  활성 컨트롤은 창을 가지지만 비활성 컨트롤은 그렇지 않습니다.  창 없는 활성화의 도입에 의해, 이러한 구분은 더 이상 절대적이지 않습니다. 그러나 여전히 많은 컨트롤에 적용됩니다.  
  
 [창 없는 컨트롤](../mfc/providing-windowless-activation.md)이 활성화되는 경우는, 마우스 캡쳐, 키보드 초점, 스크롤링 및 기타 창 서비스를 컨테이너로부터 빌려옵니다.  또한 [창을 만들기 위해 활성화될 때까지 기다림](../mfc/turning-off-the-activate-when-visible-option.md)은 물론, [비활성 컨트롤에 마우스 상호 작용을 제공](../mfc/providing-mouse-interaction-while-inactive.md)합니다.  
  
 컨트롤 창이 활성화되면 컨트롤 컨테이너, 사용자 및 Windows와 완전히 상호 작용할 수 있게 됩니다.  아래 그림은 ActiveX 컨트롤, 컨트롤 컨테이너와 운영 체제 사이의 통신 경로를 보여줍니다.  
  
 ![활성 창이 있는 ActiveX 컨트롤에서 Msg 처리](../mfc/media/vc37223.png "vc37223")  
창 있는 ActiveX 컨트롤의 Windows 메시지 처리\(활성화된 경우\)  
  
##  <a name="_core_serializing_activex_elements"></a> Serialization  
 영구성이라고도 불리는 데이터 직렬화 기능은 컨트롤이 속성 값을 영구 저장소에 쓸 수 있도록 허용합니다.  컨트롤은 저장소에서 개체의 상태를 읽어들여서 재생성될 수 있습니다.  
  
 컨트롤에 의해 기록 매체에 액세스할 권한을 얻는 것이 아니라는 것에 주의하십시오.  대신에, 컨트롤의 컨테이너가 적절한 때에 사용하기 위하여 기록 매체를 갖는 컨트롤을 제공해야 합니다.  직렬화에 대한 자세한 내용은 [MFC ActiveX 컨트롤: 직렬화](../mfc/mfc-activex-controls-serializing.md) 문서를 참조 하십시오.  직렬화의 최적화에 대한 정보는 ActiveX 컨트롤에서: 최적화의 [영구성 최적화 및 초기화](../mfc/optimizing-persistence-and-initialization.md)를 참조하십시오.  
  
##  <a name="_core_installing_activex_control_classes_and_tools"></a> ActiveX 컨트롤 클래스 및 도구 설치  
 Visual C\+\+를 설치할 때 설치 화면에서 ActiveX 컨트롤을 선택한 경우\(기본적으로 선택\), MFC ActiveX 컨트롤 클래스와 소매 및 디버그 ActiveX 컨트롤 런타임 DLLs가 자동으로 설치됩니다.  
  
 기본적으로 ActiveX 컨트롤 클래스 및 도구는 \\Program Files\\Microsoft Visual Studio.NET의 하위 디렉터리에 설치됩니다.  
  
-   **\\Common7\\Tools**  
  
     테스트 컨테이너 파일\(TstCon32.exe과 해당 도움말 파일\)을 포함합니다.  
  
-   **\\Vc7\\atlmfc\\include**  
  
     MFC로 ActiveX 컨트롤을 개발하는 데에 필요한 인클루드 파일을 포함합니다.  
  
-   **\\Vc7\\atlmfc\\src\\mfc**  
  
     특정 ActiveX 컨트롤 클래스에 대한 MFC 소스 코드를 포함합니다.  
  
-   **\\Vc7\\atlmfc\\lib**  
  
     MFC로 ActiveX 컨트롤을 개발하는 데에 필요한 라이브러리를 포함합니다.  
  
 MFC ActiveX 컨트롤에 대한 샘플도 있습니다.  이러한 샘플에 대한 자세한 내용은 [컨트롤 샘플: ActiveX 컨트롤 MFC\-Based](../top/visual-cpp-samples.md)를 참조하십시오.  
  
## 참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)