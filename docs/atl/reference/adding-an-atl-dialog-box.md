---
title: "Adding an ATL Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트, 대화 상자 리소스 추가"
  - "대화 상자, ATL"
  - "MFC 대화 상자, ATL 대화 상자"
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Adding an ATL Dialog Box
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL 대화 상자를 프로젝트에 추가하려면 프로젝트가 ATL 프로젝트이거나 ATL을 지원하는 MFC 프로젝트여야 합니다.  [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)를 사용하여 ATL 응용 프로그램을 만들거나 [MFC 응용 프로그램에 ATL 개체를 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)하여 MFC 응용 프로그램에 ATL 지원을 구현할 수 있습니다.  
  
 기본적으로 ATL 대화 상자 마법사에서는 [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)에서 파생된 대화 상자를 구현합니다.  이 클래스는 ActiveX 컨트롤과 Windows 컨트롤에 대한 호스팅을 지원합니다.  ActiveX 컨트롤 지원과 관련한 오버헤드를 원하지 않는 경우에는 마법사에서 코드를 생성한 후 기본 클래스를 `CAxDialogImpl`의 모든 인스턴스에서 [CSimpleDialog](../../atl/reference/csimpledialog-class.md)나 [CDialogImpl](../../atl/reference/cdialogimpl-class.md)로 바꿉니다.  
  
> [!NOTE]
>  `CSimpleDialog`는 Windows 공용 컨트롤만 지원하는 모달 대화 상자만 만들고,  `CDialogImpl`은 모달 대화 상자나 모덜리스 대화 상자 중 하나를 만듭니다.  
  
### ATL 대화 상자 리소스를 프로젝트에 추가하려면  
  
1.  [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)를 사용하여 ATL 프로젝트를 만듭니다.  
  
2.  [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **추가**를 클릭합니다.  **클래스 추가**를 클릭합니다.  
  
3.  [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자의 템플릿 창에서 **ATL 대화 상자**를 클릭합니다.  **열기**를 클릭하면 [ATL 대화 상자 마법사](../../atl/reference/atl-dialog-wizard.md)가 나타납니다.  
  
 자세한 내용은 [대화 상자 구현](../../atl/implementing-a-dialog-box.md)을 참조하십시오.  
  
## 참고 항목  
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [창 클래스](../../atl/atl-window-classes.md)   
 [Message Maps](../../atl/message-maps-atl.md)