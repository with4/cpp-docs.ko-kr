---
title: "마법사 및 리소스 편집기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- application wizards [MFC], and MFC
- MFC, resource editors
- resource editors, MFC
- MFC Application Wizard
- editors [MFC], resource
- wizards [MFC]
- wizards [MFC], MFC programming
- MFC, wizards
- Class View tool, managing Windows messages
ms.assetid: f5dd4d13-9dc1-4a49-b6bf-5b3cb45fa8ba
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fd81a8548dbb746da4afa5b89bc49ee801cbaeb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="wizards-and-the-resource-editors"></a>마법사 및 리소스 편집기
Visual c + + MFC 프로그래밍 많은 통합된 리소스 편집기와 함께 사용 하기 위해 몇 가지 마법사를 포함합니다. ActiveX 컨트롤 프로그래밍에 대해는 [ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md) 것과 마찬가지로 MFC 응용 프로그램 마법사의 목적을 갖습니다. 대부분의이 도구는 MFC 응용 프로그램을 작성할 수 있지만, 도구 크게 단순화 하 고 빠르게 작업 합니다.  
  
##  <a name="_core_use_appwizard_to_create_an_mfc_application"></a>MFC 응용 프로그램 마법사를 사용 하 여 MFC 응용 프로그램을 만들려면  
 사용 하 여는 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md) Visual c + +에서는 OLE를 포함 하 고 데이터베이스 지원 있는 MFC 프로젝트를 만들려고 합니다. 프로젝트의에서 파일에 포함할 응용 프로그램, 문서, 뷰 및 프레임 창 클래스입니다. 표준 리소스, 메뉴 및 선택적 도구 모음; 포함 다른 필수 Windows 파일입니다. 및 선택적.rtf 파일 프로그램의 도움말 파일을 만드는 업그레이드 및 수정할 수 있습니다 하는 표준 Windows 도움말 항목을 포함 하 합니다.  
  
##  <a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a>클래스 뷰를 사용 하 여 클래스 및 Windows 메시지를 관리 하려면  
 클래스 뷰 사용 하면 Windows 메시지 및 명령에 대 한 처리기 함수를 만드는, 생성 하 고 클래스, 관리 클래스 멤버 변수를 만듭니다, 그리고 자동화 메서드 및 속성을 만들고, 데이터베이스 클래스 등.  
  
> [!NOTE]
>  클래스 뷰를 사용 하면 MFC 클래스의 가상 함수를 재정의할 수 있습니다. 클래스 및 가상 함수 재정의를 선택 합니다. 프로세스의 나머지 다음 단락에 설명 된 대로 메시지 처리와 비슷합니다.  
  
 Windows에서 실행 되는 응용 프로그램은 [메시지 구동](../mfc/message-handling-and-mapping.md)합니다. 실행 중인 프로그램에서 발생 하는 다른 이벤트 및 사용자 작업 하면 프로그램에서 창에 메시지를 보낼 창 됩니다. 예를 들어 사용자가 창에서 마우스를 클릭 하면 Windows 보냅니다는 `WM_LBUTTONDOWN` 메시지 마우스 왼쪽된 단추를 누르면 및 `WM_LBUTTONUP` 단추를 놓을 때 메시지입니다. Windows도 보냅니다 **WM_COMMAND** 메시지를 사용자가 메뉴 모음에서 명령을 선택 합니다.  
  
 MFC 프레임 워크에서 문서, 뷰, 프레임 창, 문서 템플릿 및 응용 프로그램 개체와 같은 다양 한 개체 수 "메시지를 처리". 이러한 개체는 "처리기 함수" 멤버의 멤버 중 하나로 함수를 제공 하 고 프레임 워크를 해당 처리기 들어오는 메시지를 매핑합니다.  
  
 프로그래밍 작업의 많은 부분 메시지 매핑할 수 있는 개체를 선택한 다음 해당 매핑을 구현은 합니다. 이렇게 하려면 속성 창 및 클래스 뷰를 사용 합니다.  
  
 속성 창의 빈 메시지 처리기 멤버 함수를 만들고 소스 코드 편집기를 사용 하 여 처리기의 본문을 구현 합니다. 만들 하거나 클래스 (MFC 클래스에서 파생 되지 않은 사용자 지정 클래스 포함)와 클래스 뷰에서 해당 멤버를 편집할 수도 있습니다. 클래스 뷰를 사용 하 여 및 코드 프로젝트에 추가 하는 마법사에 대 한 자세한 내용은 참조 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)합니다.  
  
##  <a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a>리소스 편집기를 사용 하 여 만들고 리소스 편집  
 Visual c + +를 사용 하 여 [리소스 편집기](../windows/resource-editors.md) 를 만들고 메뉴, 대화 상자, 사용자 지정 컨트롤, 액셀러레이터 키, 비트맵, 아이콘, 커서, 문자열 및 버전 리소스를 편집 합니다. Visual c + + 버전 4.0부터 도구 모음 편집기 도구 모음을 만들 훨씬 더 쉽게 만듭니다.  
  
 를 더 많은 수 있도록 Microsoft Foundation Class 라이브러리는 공통 라는 파일을 제공 합니다. RES 일반적인에서 복사할 수 있는 "클립 아트" 리소스를 포함 합니다. RES 및 고유한 리소스 파일에 붙여 넣습니다. 일반적인 합니다. RES 도구 모음 단추, 일반적인 커서, 아이콘 및 더 포함 되어 있습니다. 사용 하 고, 수정 하 고, 응용 프로그램에서 이러한 리소스를 재배포할 수 있습니다. 공통에 대 한 자세한 내용은 합니다. RES를 참조는 [클립 아트 샘플](../visual-cpp-samples.md)합니다.  
  
 MFC 응용 프로그램 마법사, Visual c + + 마법사, 리소스 편집기 및 MFC 프레임 워크 많은 작업을 수행 하 고 코드를 훨씬 쉽게 관리할 수 있도록 합니다. 응용 프로그램별 코드의 대부분 문서와 뷰 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스를 사용하여 Windows 응용 프로그램 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)
