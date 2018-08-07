---
title: 응용 프로그램에 팝업 메뉴 연결 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- pop-up menus, connecting to applications
- context menus, connecting to applications
- menus, pop-up
- shortcut menus, connecting to applications
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 533fc4eea9299d51183a91febb371ff8142e0a7b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879531"
---
# <a name="connecting-a-pop-up-menu-to-your-application"></a>응용 프로그램에 팝업 메뉴 연결
### <a name="to-connect-a-pop-up-menu-to-your-application"></a>응용 프로그램에 팝업 메뉴를 연결하려면  
  
1.  예를 들면 WM_CONTEXTMENU에 대 한 메시지 처리기를 추가 합니다. 자세한 내용은 참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)합니다.  
  
2.  메시지 처리기에 다음 코드를 추가합니다.  
  
    ```  
    CMenu menu;  
    VERIFY(menu.LoadMenu(IDR_MENU1));  
    CMenu* pPopup = menu.GetSubMenu(0);  
    ASSERT(pPopup != NULL);  
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());  
    ```  
  
    > [!NOTE]
    >  [CPoint](../atl-mfc-shared/reference/cpoint-class.md) **전달 된 메시지 처리기는 화면 좌표로 표시 합니다.**  
  

  
 **요구 사항**  
  
 MFC  
  
## <a name="see-also"></a>참고 항목  
 [팝업 메뉴 만들기](../windows/creating-pop-up-menus.md)   
 [메뉴 편집기](../windows/menu-editor.md)   
