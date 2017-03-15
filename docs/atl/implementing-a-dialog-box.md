---
title: "Implementing a Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, 대화 상자"
  - "CAxDialogImpl class, implementing dialog boxes in ATL"
  - "CSimpleDialog class, implementing dialog boxes in ATL"
  - "대화 상자, ATL"
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Implementing a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL 프로젝트에 대화 상자를 추가 하는 방법은 두 가지: ATL 대화 상자 마법사를 사용 하거나 수동으로 추가 합니다.  
  
## ATL 대화 상자 마법사와 대화 상자 추가  
 에  [클래스 추가 대화 상자](../ide/add-class-dialog-box.md), ATL 프로젝트에 대화 상자를 추가 하는 ATL 대화 상자 개체를 선택 합니다.  ATL 대화 상자 마법사를 적절 하 게 입력 하 고 클릭  **완료**.  파생 된 클래스 마법사 추가  [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) 프로젝트에.  자원 보기에서 열을  **보기** 메뉴, 대화 상자를 찾아 두 번 클릭 하 여 리소스 편집기에서 엽니다.  
  
> [!NOTE]
>  대화 상자에서 파생 된 경우 `CAxDialogImpl`, ActiveX 모두 호스팅하는 및 Windows 컨트롤을 합니다.  대화 상자 클래스에 ActiveX 컨트롤 지원 오버 헤드를 원하지 않으면 사용  [CSimpleDialog](../atl/reference/csimpledialog-class.md) 또는  [CDialogImpl](../atl/reference/cdialogimpl-class.md) 대신 합니다.  
  
 클래스 뷰에서 대화 상자 클래스에 메시지 및 이벤트 처리기를 추가할 수 있습니다.  자세한 내용은 [ATL 메시지 처리기 추가](../atl/adding-an-atl-message-handler.md)를 참조하십시오.  
  
## 대화 상자에 수동으로 추가  
 대화 상자 구현 창을 구현 하는 것과 비슷합니다.  클래스에서 파생  [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md),  [CDialogImpl](../atl/reference/cdialogimpl-class.md), 또는  [CSimpleDialog](../atl/reference/csimpledialog-class.md) 선언 하 고는  [메시지 맵](../atl/message-maps-atl.md) 메시지를 처리 합니다.  그러나 대화 상자 템플릿 리소스 ID에서 파생 된 클래스도 지정 해야 합니다.  클래스 데이터 멤버 있어야 `IDD` 이 값을 유지 합니다.  
  
> [!NOTE]
>  ATL 대화 상자 마법사를 사용 하 여 대화 상자를 만들 때 마법사를 자동으로 추가 된 `IDD` 구성원으로는 `enum` 형식.  
  
 `CDialogImpl`한 모달 또는 모덜리스 대화 상자는 Windows 컨트롤을 호스트를 구현할 수 있습니다.  `CAxDialogImpl`모두 ActiveX 및 Windows 컨트롤을 호스팅하는 모덜리스 대화 상자는 모달 구현할 수 있습니다.  
  
 모달 대화 상자를 만들려면 인스턴스를 만들을 `CDialogImpl`\-파생 \(또는 `CAxDialogImpl`\-파생\) 클래스 및 다음 호출에서  [DoModal](../Topic/CDialogImpl::DoModal.md) 메서드.  모달 대화 상자를 닫으려면 호출을  [EndDialog](../Topic/CDialogImpl::EndDialog.md) 메시지 처리기에서 메서드.  모덜리스 대화 상자를 만들려면 호출을  [만들기](../Topic/CDialogImpl::Create.md) 메서드 대신 `DoModal`.  모덜리스 대화 상자를 파괴 하려면 호출  [DestroyWindow](../Topic/CDialogImpl::DestroyWindow.md).  
  
 이벤트 싱크 자동 수행  [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md).  처리기에서와 같이 대화 상자의 메시지 처리기 구현에 `CWindowImpl`\-파생 클래스.  특정 메시지 반환 값이 없는 경우로 반환 된 `LRESULT`.  반환 되는 `LRESULT` 값 Windows 대화 관리자가 적절 한 처리에 대 한 ATL에서 매핑되는.  소스 코드에 대 한 자세한 내용은  [CDialogImplBaseT::DialogProc](../Topic/CDialogImpl::DialogProc.md) atlwin.h에서.  
  
## 예제  
 다음 클래스는 대화 상자를 구현합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/CPP/implementing-a-dialog-box_1.h)]  
  
## 참고 항목  
 [창 클래스](../atl/atl-window-classes.md)