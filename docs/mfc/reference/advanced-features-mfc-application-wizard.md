---
title: "MFC 응용 프로그램 마법사, 고급 기능 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.advanced"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC 응용 프로그램 마법사, 고급 기능"
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# MFC 응용 프로그램 마법사, 고급 기능
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 도움말, 인쇄 지원 등과 같은 응용 프로그램을 위한 추가 기능을 설정할 수 있는 옵션에 대해 설명합니다.  각 섹션에서 이 고급 기능에 추가 지원을 지정하세요.  
  
 **상황에 맞는 도움말\(HTML\)**  
 F1 키 및 도움말 메뉴를 사용하거나 대화 상자의 **도움말** 단추를 클릭하여 표시할 수 있는 상황에 맞는 도움말을 위한 도움말 파일 집합을 생성합니다.  도움말을 지원하려면 도움말 컴파일러가 필요합니다.  도움말 컴파일러가 없으면 설치를 다시 실행하여 설치할 수 있습니다.  
  
 자세한 내용은 [HTML 도움말: 프로그램에 대한 상황에 맞는 도움말](../../mfc/html-help-context-sensitive-help-for-your-programs.md) 및 [도움말 파일\(HTML 도움말\)](../../ide/help-files-html-help.md)을 참조하세요.  
  
 **인쇄 및 인쇄 미리 보기**  
 MFC 라이브러리에서 [CView Class](../../mfc/reference/cview-class.md)의 멤버 함수를 호출하여 인쇄, 인쇄 설정 및 인쇄 미리 보기 명령을 처리하는 코드를 생성합니다.  마법사에서는 응용 프로그램 메뉴에 이러한 함수에 대한 명령을 추가합니다.  마법사의 [MFC 응용 프로그램 마법사, 응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) 페이지에서 **문서\/뷰 아키텍처 지원**을 지정한 응용 프로그램에서만 인쇄를 지원합니다.  기본적으로 문서\/뷰 응용 프로그램은 인쇄를 지원합니다.  
  
 **자동화**  
 응용 프로그램이 다른 응용 프로그램에서 구현된 개체를 처리할 수 있도록 지정하거나 자동화 클라이언트에 응용 프로그램을 노출시킵니다.  
  
 **ActiveX 컨트롤**  
 ActiveX 컨트롤을 지원합니다\(기본값\).  이 옵션을 선택하지 않고 나중에 ActiveX 컨트롤을 프로젝트에 삽입하려면 응용 프로그램의 [CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md) 멤버 함수에서 [AfxEnableControlContainer](../Topic/AfxEnableControlContainer.md)에 대한 호출을 추가해야 합니다.  
  
 **MAPI\(메시징 API\)**  
 응용 프로그램에서 메일 메시지를 만들고, 편집하고, 전송하고, 저장할 수 있도록 지정합니다.  
  
 **Windows 소켓**  
 TCP\/IP 네트워크를 통해 통신하는 응용 프로그램을 작성할 때 사용할 수 있는 Windows 소켓을 지원합니다.  
  
 **Active Accessibility**  
 [IAccessible](http://msdn.microsoft.com/library/windows/desktop/dd318466)에 대한 지원을 [CWnd](../../mfc/reference/cwnd-class.md) 파생 클래스에 추가함으로써 내게 필요한 옵션 지원 클라이언트와 보다 원활하게 상호 작용할 수 있도록 사용자 인터페이스를 사용자 지정할 수 있습니다.  
  
 **공용 컨트롤 매니페스트**  
 기본적으로 활성화되어 있습니다.  Microsoft Windows XP 및 새 운영 체제에 포함된 공용 컨트롤 DLL을 사용할 수 있도록 하는 응용 프로그램 매니페스트를 생성합니다.  
  
 공용 컨트롤 DLL의 버전 6에서는 기존 응용 프로그램에서 사용하는 이전 버전의 공용 컨트롤을 자동으로 업데이트하지 않습니다.  공용 컨트롤 DLL의 버전 6을 사용하려면 응용 프로그램에서 해당 DLL을 로드하도록 지시하는 응용 프로그램 매니페스트를 만들어야 합니다.  이 공용 컨트롤 DLL에서는 Windows XP 테마도 지원합니다.  
  
 응용 프로그램 매니페스트에서는 응용 프로그램에 필요한 다른 DLL 및 버전도 지정할 수 있습니다.  응용 프로그램 매니페스트에 대한 자세한 내용은 [격리된 응용 프로그램과 side\-by\-side 어셈블리](http://msdn.microsoft.com/library/dd408052) 의 [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] 를 참조하세요.  
  
 **다시 시작 관리자 지원**  
 [Windows 다시 시작 관리자](http://msdn.microsoft.com/library/windows/desktop/aa373680\(v=vs.85\).aspx)에 대한 지원을 추가합니다.  이 비디오에서는 MFC에서 다시 시작 관리자를 사용하는 방법인 [방법: 새로운 다시 시작 관리자 사용](http://msdn.microsoft.com/vstudio/ee886407)을 설명합니다.  
  
 **고급 프레임 창**  
 |옵션|설명|  
|--------|--------|  
|**탐색기 도킹 창**|Visual Studio **솔루션 탐색기**와 유사한 도킹 창을 주 프레임 창 왼쪽에 만듭니다.|  
|**출력 도킹 프레임**|Visual Studio **출력** 창과 유사한 도킹 창을 주 프레임 창 아래쪽에 만듭니다.|  
|**속성 도킹 창**|Visual Studio **속성** 창과 유사한 도킹 창을 주 프레임 창 오른쪽에 만듭니다.|  
|**탐색 창**|Outlook 탐색 모음과 유사한 도킹 창을 주 프레임 창 왼쪽에 만듭니다.|  
|**캡션 표시줄**|Office 스타일의 캡션 표시줄을 주 프레임 창 위쪽에 만듭니다.|  
  
 **최근 파일 목록의 파일 수**  
 가장 최근에 사용된 파일 목록에 나열될 파일 수를 지정합니다.  기본값은 4입니다.  
  
## 참고 항목  
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)