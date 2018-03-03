---
title: "ATL 대화 상자 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- MFC dialog boxes, ATL dialogs
- dialog boxes, ATL
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d8c9969f4747c6c3fa2a39b7b0452f6ac54c9d58
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-atl-dialog-box"></a>ATL 대화 상자 추가
ATL 대화 상자에 프로젝트를 추가 하려면 프로젝트에 ATL 프로젝트 또는 ATL 지원을 포함 하는 MFC 프로젝트 중 하나 여야 합니다. 사용할 수는 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md) ATL 응용 프로그램을 만드는 또는 [MFC 응용 프로그램에 ATL 개체를 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC 응용 프로그램에 대 한 ATL 지원을 구현 하 합니다.  
  
 기본적으로 ATL 대화 상자 마법사에서 파생 된 대화 상자를 구현 [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)합니다. 이 클래스는 Windows 및 ActiveX 컨트롤을 호스팅하기 위한 지원 합니다. 마법사가 코드를 생성 한 후 ActiveX 컨트롤을 지 원하는의 오버 헤드가 발생 하지 않도록를 바꾸려면 `CAxDialogImpl` 하나로 [CSimpleDialog](../../atl/reference/csimpledialog-class.md) 또는 [CDialogImpl](../../atl/reference/cdialogimpl-class.md) 기본 클래스로 .  
  
> [!NOTE]
>  `CSimpleDialog`만 지 원하는 Windows 공용 컨트롤만 모달 대화 상자를 만듭니다. `CDialogImpl`모달 또는 모덜리스 대화 상자 중 하나를 만듭니다.  
  
### <a name="to-add-an-atl-dialog-resource-to-your-project"></a>프로젝트에 ATL 대화 상자 리소스를 추가 하려면  
  
1.  사용 하 여 ATL 프로젝트 만들기는 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)합니다.  
  
2.  [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **추가** 바로 가기 메뉴에서. 클릭 **클래스 추가**합니다.  
  
3.  템플릿 창에는 [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자를 클릭 **ATL 대화 상자**합니다. 클릭 **열려** 표시 하는 [ATL 대화 상자 마법사](../../atl/reference/atl-dialog-wizard.md)합니다.  
  
 자세한 내용은 참조 [대화 상자를 구현](../../atl/implementing-a-dialog-box.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [창 클래스](../../atl/atl-window-classes.md)   
 [메시지 맵](../../atl/message-maps-atl.md)

