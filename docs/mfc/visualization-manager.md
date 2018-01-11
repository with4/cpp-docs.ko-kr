---
title: "시각화 관리자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 654ffc0f3fb4c33f153f3389442486ffa86b74a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="visualization-manager"></a>시각화 관리자
비주얼 관리자는 전체 응용 프로그램의 모양을 제어 하는 개체입니다. 동작 하는 단일 클래스 응용 프로그램에 대 한 모든 그리기 코드를 입력할 수 있는 합니다. MFC 라이브러리는 몇 가지 비주얼 관리자를 포함합니다. 응용 프로그램에 대 한 사용자 지정 보기를 만들려는 경우에 고유한 비주얼 관리자를 만들 수 있습니다. 다음 그림은 비주얼 관리자를 다른 설정 된 경우 동일한 응용 프로그램을 보여 줍니다.  
  
 ![CMFCVisualManagerWindows에서 렌더링 된 MyApp](../mfc/media/vmwindows.png "vmwindows")  
CMFCVisualManagerWindows 비주얼 관리자를 사용 하 여 MyApp  
  
 ![CMFCVisualManagerVS2005에서 렌더링 된 MyApp](../mfc/media/vmvs2005.png "vmvs2005")  
CMFCVisualManagerVS2005 비주얼 관리자를 사용 하 여 MyApp  
  
 ![CMFCVisualManagerOfficeXP에서 렌더링 된 MyApp](../mfc/media/vmofficexp.png "vmofficexp")  
CMFCVisualManagerOfficeXP 비주얼 관리자를 사용 하 여 MyApp  
  
 ![CMFCVisualManagerOffice2003에서 렌더링 된 MyApp](../mfc/media/vmoffice2003.png "vmoffice2003")  
CMFCVisualManagerOffice2003 비주얼 관리자를 사용 하 여 MyApp  
  
 ![CMFCVisualManagerOffice2007에서 렌더링 된 MyApp](../mfc/media/msoffice2007.png "msoffice2007")  
CMFCVisualManagerOffice2007 비주얼 관리자를 사용 하 여 MyApp  
  
 기본적으로 비주얼 관리자는 여러 GUI 요소에 대 한 그리기 코드를 유지 합니다. 사용자 지정 UI 요소를 제공 하려면 비주얼 관리자의 관련된 그리기 메서드를 재정의 해야 합니다. 이러한 메서드의 목록에 대 한 참조 [CMFCVisualManager 클래스](../mfc/reference/cmfcvisualmanager-class.md)합니다. 사용자 지정 모양을 제공 하기 위해 재정의할 수 하는 메서드는로 시작 하는 모든 메서드에 `OnDraw`합니다.  
  
 응용 프로그램 하나만 가질 수 있습니다 `CMFCVisualManager` 개체입니다. 정적 함수를 호출 응용 프로그램에 대 한 비주얼 관리자에 대 한 포인터를 얻으려면 [CMFCVisualManager::GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance)합니다. 모든 비주얼 관리자에서 상속 하기 때문에 `CMFCVisualManager`, `CMFCVisualManager::GetInstance` 사용자 지정 비주얼 관리자를 만드는 경우에 메서드가 적절 한 비주얼 관리자에 포인터를 가져올 됩니다.  
  
 사용자 지정 비주얼 관리자를 만들려는 경우 이미 존재 하는 비주얼 관리자에서 파생 해야 합니다. 기본 클래스에서 파생 하는 `CMFCVisualManager`합니다. 그러나 더 잘 비슷하도록 응용 프로그램에 대해 원하는 경우 다른 비주얼 관리자를 사용할 수 있습니다. 예를 들어, 사용 하려는 경우는 `CMFCVisualManagerOffice2007` 비주얼 관리자 하지만 변경 하려면 어떻게 표시될지 구분 기호에서 사용자 지정 클래스를 파생할 수 `CMFCVisualManagerOffice2007`합니다. 이 시나리오에서는 구분 기호를 그리기 위한 메서드만을 덮어써야 합니다.  
  
 응용 프로그램에 대 한 특정 비주얼 관리자를 사용 하는 다음 두 가지 있습니다. 호출 하는 한 가지 방법은 [CMFCVisualManager::SetDefaultManager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) 메서드와 적절 한 비주얼 관리자를 매개 변수로 전달 합니다. 다음 코드 예제에서는 사용 하는 방법을 보여 줍니다.는 `CMFCVisualManagerVS2005` 이 메서드로 비주얼 관리자:  
  
```  
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```  
  
 응용 프로그램에서 비주얼 관리자를 사용 하는 다른 방법은 수동으로 만드는 것입니다. 응용 프로그램은 모든 렌더링에 대 한이 새 비주얼 관리자를 사용 합니다. 그러나 하나만 있을 수 있으므로 `CMFCVisualManager` 개체 응용 프로그램 마다 새를 만들기 전에 현재 비주얼 관리자를 삭제 해야 합니다. 다음 예에서 `CMyVisualManager` 는에서 파생 되는 사용자 지정 시각적 관리자 `CMFCVisualManager`합니다. 다음 메서드는 어떤 비주얼 관리자는 인덱스에 따라 응용 프로그램을 표시 하는 데 사용 되 변경 됩니다.  
  
```  
void CMyApp::SetSkin (int index)  
{  
    if (CMFCVisualManager::GetInstance() != NULL)  
 {  
    delete CMFCVisualManager::GetInstance();

 }  
 
    switch (index)  
 {  
    case DEFAULT_STYLE: *// The following statement creates a new CMFCVisualManager  
    CMFCVisualManager::GetInstance();
break;  
 
    case CUSTOM_STYLE:  
    new CMyVisualManager;  
    break; 
 
    default: 
    CMFCVisualManager::GetInstance();
break;  
 }  
 
    CMFCVisualManager::GetInstance()->RedrawAll();

} 
```  
  
## <a name="see-also"></a>참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)   
 [CMFCVisualManager 클래스](../mfc/reference/cmfcvisualmanager-class.md)
