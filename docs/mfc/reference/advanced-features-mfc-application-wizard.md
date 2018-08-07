---
title: 고급 기능을 MFC 응용 프로그램 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.advanced
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, advanced features
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5094c18f72182929565e7c23c38b63443839da1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358458"
---
# <a name="advanced-features-mfc-application-wizard"></a>MFC 응용 프로그램 마법사, 고급 기능
이 항목에서는 도움말, 인쇄 지원 등과 같은 응용 프로그램을 위한 추가 기능을 설정할 수 있는 옵션에 대해 설명합니다. 각 섹션에서 이 고급 기능에 추가 지원을 지정하세요.  
  
 **상황에 맞는 도움말 (HTML)**  
 F1 키 및 도움말 메뉴를 사용 하거나 클릭 하 여 볼 수 있는 상황에 맞는 도움말에 대 한 도움말 파일의 집합을 생성 한 **도움말** 대화 상자에서 단추입니다. 도움말을 지원하려면 도움말 컴파일러가 필요합니다. 도움말 컴파일러가 없으면 설치를 다시 실행하여 설치할 수 있습니다.  
  
 참조 [HTML 도움말: 프로그램에 대 한 상황에 맞는 도움말](../../mfc/html-help-context-sensitive-help-for-your-programs.md) 및 [도움말 파일 (HTML 도움말)](../../ide/help-files-html-help.md) 자세한 정보에 대 한 합니다.  
  
 **인쇄 및 인쇄 미리 보기**  
 멤버 함수를 호출 하 여 인쇄 설정 및 인쇄 미리 보기 명령을, 인쇄를 처리 하는 코드를 생성 된 [CView 클래스](../../mfc/reference/cview-class.md) MFC 라이브러리에서. 마법사에서는 응용 프로그램 메뉴에 이러한 함수에 대한 명령을 추가합니다. 인쇄 지원은 지정 하는 응용 프로그램에만 사용할 수 있는 **문서/뷰 아키텍처 지원** 에 [MFC 응용 프로그램 마법사, 응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) 마법사의 페이지입니다. 기본적으로 문서/뷰 응용 프로그램은 인쇄를 지원합니다.  
  
 **자동화**  
 응용 프로그램이 다른 응용 프로그램에서 구현된 개체를 처리할 수 있도록 지정하거나 자동화 클라이언트에 응용 프로그램을 노출시킵니다.  
  
 **ActiveX 컨트롤**  
 ActiveX 컨트롤을 지원합니다(기본값). 에 대 한 호출을 추가 해야 하는 경우이 옵션을 선택 하지 않으며 나중에 ActiveX 컨트롤을 프로젝트에 삽입 하려면 [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) 응용 프로그램에서 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 멤버 함수입니다.  
  
 **MAPI (메시징 API)**  
 응용 프로그램에서 메일 메시지를 만들고, 편집하고, 전송하고, 저장할 수 있도록 지정합니다.  
  
 **Windows 소켓**  
 TCP/IP 네트워크를 통해 통신하는 응용 프로그램을 작성할 때 사용할 수 있는 Windows 소켓을 지원합니다.  
  
 **Active Accessibility**  
 에 대 한 지원을 추가 [IAccessible](http://msdn.microsoft.com/library/windows/desktop/dd318466) 를 [CWnd](../../mfc/reference/cwnd-class.md)-액세스 가능 클라이언트와 상호 사용자 인터페이스 사용자 지정 하는 데 사용할 수 있는 클래스를 파생 합니다.  
  
 **공용 컨트롤 매니페스트**  
 기본적으로 활성화되어 있습니다. Microsoft Windows XP 및 새 운영 체제에 포함된 공용 컨트롤 DLL을 사용할 수 있도록 하는 응용 프로그램 매니페스트를 생성합니다.  
  
 공용 컨트롤 DLL의 버전 6에서는 기존 응용 프로그램에서 사용하는 이전 버전의 공용 컨트롤을 자동으로 업데이트하지 않습니다. 공용 컨트롤 DLL의 버전 6을 사용하려면 응용 프로그램에서 해당 DLL을 로드하도록 지시하는 응용 프로그램 매니페스트를 만들어야 합니다. 이 공용 컨트롤 DLL에서는 Windows XP 테마도 지원합니다.  
  
 응용 프로그램 매니페스트에서는 응용 프로그램에 필요한 다른 DLL 및 버전도 지정할 수 있습니다. 응용 프로그램 매니페스트에 대 한 자세한 내용은 참조 하십시오. [격리 된 응용 프로그램 및 Side-by-side-어셈블리](http://msdn.microsoft.com/library/dd408052) Windows sdk에서입니다.  
  
 **다시 시작 관리자 지원**  
 에 대 한 지원을 추가 하는 [Windows 다시 시작 관리자](http://msdn.microsoft.com/library/windows/desktop/aa373680\(v=vs.85\).aspx)합니다. 이 비디오에서는 MFC에서 다시 시작 관리자를 사용 하는 방법을 보여 줍니다: [사용 하려면 어떻게 할까요?: 새로운 다시 시작 관리자](http://msdn.microsoft.com/vstudio/ee886407)합니다.  
  
 **고급 프레임 창**  
 |옵션|설명|  
|------------|-----------------|  
|**탐색기 도킹 창**|Visual Studio 유사한 도킹 창을 만듭니다 **솔루션 탐색기** 주 프레임 창 왼쪽에 있습니다.|  
|**출력 도킹 프레임**|Visual Studio 유사한 도킹 창을 만듭니다 **출력** 주 프레임 창 아래에 있는 창입니다.|  
|**속성 도킹 창**|Visual Studio 유사한 도킹 창을 만듭니다 **속성** 주 프레임 창 오른쪽에 있는 창입니다.|  
|**탐색 창**|Outlook 탐색 모음과 유사한 도킹 창을 주 프레임 창 왼쪽에 만듭니다.|  
|**캡션 표시줄**|Office 스타일의 캡션 표시줄을 주 프레임 창 위쪽에 만듭니다.|  
  
 **최근 파일 목록의 파일 수**  
 가장 최근에 사용된 파일 목록에 나열될 파일 수를 지정합니다. 기본값은 4입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)

