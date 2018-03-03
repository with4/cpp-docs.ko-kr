---
title: "자동화 서버 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a33cf8113825804ac831b518e371c4150f2620ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="automation-servers"></a>자동화 서버
자동화를 다른 응용 프로그램에서 구현 된 개체를 조작 하거나 조작할 수 있도록 개체를 노출 시키는 응용 프로그램에 대 한 수 있게 합니다. 자동화 서버는 다른 응용 프로그램에 프로그래밍 가능 개체 (자동화 개체 라고 함)을 노출 하는 응용 프로그램 (호출 [자동화 클라이언트](../mfc/automation-clients.md)). 자동화 서버는 자동화 구성 요소 라고도 합니다.  
  
 개체에 직접 액세스 하 여 특정 절차를 자동화 하는 클라이언트를 통해 자동화 개체를 노출 하 고 서버 기능은 사용할 수 있습니다. 응용 프로그램은 다른 응용 프로그램에 대 한 유용한 기능을 제공 하는 경우이 방식으로 개체를 노출 하는 것은 유용 합니다. 예를 들어 워드 프로세서 다른 프로그램에서 사용할 수 있도록 해당 맞춤법 검사 기능을 노출 될 수 있습니다. 따라서이 개체 노출을 통해 공급 업체를 다른 응용 프로그램의 기존 기능을 사용 하 여 자사 응용 프로그램의 기능을 향상 시킬 수 있습니다.  
  
 이 자동화 개체는 속성 및 메서드 외부 인터페이스로 사용 합니다. 속성에는 자동화 개체의 특성 이름이 지정 됩니다. C + + 클래스의 데이터 멤버와 같은 속성을 합니다. 메서드는 자동화 개체에서 작동 하는 함수입니다. C + + 클래스의 public 멤버 함수와 유사 합니다.  
  
> [!NOTE]
>  옵션은 c + + 데이터 멤버 처럼 속성에 직접 액세스할 수 있는 하지 않습니다. 투명 한 액세스를 제공 하려면 액세스 하는 데 get/set 멤버 함수 쌍과 자동화 개체에 내부 변수를 설정 합니다.  
  
 일반적으로 잘 정의 된 인터페이스를 통해 응용 프로그램의 기능을 노출 하 여 자동화 수 있게 단일 일반 프로그래밍 언어의 대신 Microsoft Visual Basic 같은 다양 한, 응용 프로그램별 매크로에 응용 프로그램 작성 언어들.  
  
##  <a name="_core_support_for_automation_servers"></a>자동화 서버에 대 한 지원  
 Visual c + + 및 MFC 프레임 워크 자동화 서버에 대 한 광범위 한 지원을 제공합니다. 응용 프로그램의 기능에 여 노력을 집중할 수 있도록 자동화 서버를 만드는 작업의 오버 헤드의 대부분을 처리 합니다.  
  
 자동화 지원을 위한 프레임 워크의 기본 메커니즘은 디스패치 맵은 선언과 OLE에 대 한 메서드 및 속성을 노출 하는 데 필요한 호출으로 확장 되는 매크로의 집합입니다. 일반적인 디스패치 맵은 다음과 같습니다.  
  
 [!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]  
  
 속성 창, 클래스 뷰 디스패치 맵을 유지 관리 지원 합니다. 클래스에 새 메서드 또는 속성을 추가 하면 해당 Visual c + + 추가 `DISP_FUNCTION` 또는 `DISP_PROPERTY` 매크로 클래스 이름, 메서드 또는 속성 및 데이터 형식의 외부 이름과 내부 이름을 나타내는 매개 변수를 사용 합니다.  
  
 **클래스 추가** 대화 상자도 자동화 클래스의 선언 및 해당 속성 및 작업 관리를 간소화 합니다. 클래스 추가 대화 상자를 사용 하 여 프로젝트에 클래스를 추가할 때 기본 클래스를 지정 합니다. 클래스 추가 대화 상자 표시 "OLE 만들 수 있는" (즉, 여부 클래스의 개체에 만들 수 있으며 COM 클라이언트의 요청) 인지 새 클래스가 자동화를 지원 하는지 여부를 지정 하는 데 사용할 컨트롤의 기본 클래스 자동화를 허용 하는 경우 및 COM 사용 하도록 클라이언트에 대 한 외부 이름입니다.  
  
 **클래스 추가** 대화 상자에는 다음 클래스 선언 생성을 지정한 OLE 기능에 대 한 적절 한 매크로 포함 합니다. 또한 구현 클래스의 멤버 함수에 대 한 기본 코드를 추가합니다.  
  
 MFC 응용 프로그램 마법사 시작 단계 자동화 서버 응용 프로그램에 관련 된 단계를 간소화 합니다. 선택 하는 경우는 **자동화** 에서 확인란은 **고급 기능** 페이지, 응용 프로그램에 추가 하는 MFC 응용 프로그램 마법사 `InitInstance` 함수 자동화를 등록 하는 데 필요한 호출 개체 및 응용 프로그램을 자동화 서버로 실행 합니다.  
  
### <a name="what-do-you-want-to-do"></a>뭘 하고 싶으세요  
  
-   [자동화 클라이언트에 알아보기](../mfc/automation-clients.md)  
  
-   [CCmdTarget 클래스에 대 한 자세한 정보](../mfc/reference/ccmdtarget-class.md)  
  
-   [COleDispatchDriver 클래스에 대 한 자세한 정보](../mfc/reference/coledispatchdriver-class.md)  
  
## <a name="see-also"></a>참고 항목  
 [자동화](../mfc/automation.md)   
 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)

