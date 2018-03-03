---
title: "자동화 서버: 개체 수명 문제 | Microsoft Docs"
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
- objects [MFC], lifetime
- lifetime, automation server
- Automation servers, object lifetime
- servers, lifetime of Automation
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c9fab7af74dee482c5e8dffb327da9c037796fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="automation-servers-object-lifetime-issues"></a>자동화 서버: 개체 수명 문제
자동화 클라이언트를 만들거나 OLE 항목을 활성화, 서버 전달 클라이언트 포인터 해당 개체에 합니다. 클라이언트가 OLE 함수에 대 한 호출을 통해 개체에 대 한 참조를 설정 [iunknown:: Addref](http://msdn.microsoft.com/library/windows/desktop/ms691379)합니다. 이 참조는 클라이언트 호출할 때까지 실제로 [iunknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)합니다. (Microsoft Foundation Class 라이브러리 OLE 클래스로 작성 된 클라이언트 응용 프로그램이 이러한 호출을 허용할 필요가; 프레임 워크가 작업을 수행 합니다.) OLE 시스템 및 서버 자체 개체에 대 한 참조를 설정할 수 있습니다. 서버 외부 참조 개체에 계속 적용으로 개체를 삭제 해서는 안 됩니다.  
  
 프레임 워크 내부 개수에서 파생 된 모든 서버 개체에 대 한 참조 수를 유지 관리 [CCmdTarget](../mfc/reference/ccmdtarget-class.md)합니다. 이 수가 때 자동화 클라이언트에 업데이트 됩니다 또는 다른 엔터티 추가 또는 개체에 대 한 참조를 해제 합니다.  
  
 프레임 워크 참조 횟수가 0이 되 면 가상 함수를 호출 [CCmdTarget::OnFinalRelease](../mfc/reference/ccmdtarget-class.md#onfinalrelease)합니다. 이 함수의 기본 구현에서는 호출 하는 **삭제** 이 개체를 삭제 하는 연산자입니다.  
  
 Microsoft Foundation Class 라이브러리는 외부 클라이언트 응용 프로그램의 개체에 대 한 참조가 있는 경우 응용 프로그램 동작을 제어 하기 위한 추가 기능을 제공 합니다. 서버 외에도 각 개체에 대 한 참조 횟수를 유지 관리 하는 전역 활성 개체 수를 관리 합니다. 전역 함수 [AfxOleLockApp](../mfc/reference/application-control.md#afxolelockapp) 및 [AfxOleUnlockApp](../mfc/reference/application-control.md#afxoleunlockapp) 응용 프로그램의 활성 개체 수를 업데이트 합니다. 이 개수가 0이 아닌 사용자가 파일 메뉴에서 종료 또는 시스템 메뉴에서 닫기를 선택 응용 프로그램 종료 되지 않습니다. 대신, 응용 프로그램의 주 창이 숨겨집니다 (않으며 소멸 되지) 보류 중인 모든 클라이언트 요청이 완료 될 때까지입니다. 일반적으로 `AfxOleLockApp` 및 `AfxOleUnlockApp` 의 자동화를 지 원하는 클래스 각각 생성자 및 소멸자에서 호출 됩니다.  
  
 경우에 따라 상황 강제로 클라이언트에 아직 개체에 대 한 참조 하는 동안 종료 하는 서버. 예를 들어 서버 의존 하는 리소스를 사용할 수 없는 서버 오류가 발생 될 수 있습니다. 사용자를 다른 응용 프로그램에 대 한 참조는 개체를 포함 하는 서버 문서를 닫을 수도 있습니다.  
  
 Windows SDK에서 참조 `IUnknown::AddRef` 및 `IUnknown::Release`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [자동화 서버](../mfc/automation-servers.md)   
 [AfxOleCanExitApp](../mfc/reference/application-control.md#afxolecanexitapp)

