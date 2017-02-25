---
title: "CDialogBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDialogBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogBar class"
  - "dialog bars, Windows modeless dialog box"
  - "대화 상자, 모덜리스"
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDialogBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 모덜리스 대화 상자에 컨트롤 막대의 기능을 제공합니다.  
  
## 구문  
  
```  
class CDialogBar : public CControlBar  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDialogBar::CDialogBar](../Topic/CDialogBar::CDialogBar.md)|`CDialogBar` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDialogBar::Create](../Topic/CDialogBar::Create.md)|Windows 대화 상자 모음을 만들고이에 연결 된 `CDialogBar` 개체입니다.|  
  
## 설명  
 사용자가 탭 사이 표준 Windows 컨트롤을 포함 한다는 점에서 대화 상자 표시줄 대화 상자와 유사 합니다.  다른 유사 대화 대화 상자 막대를 나타내려면 서식 파일을 만드는 것입니다.  
  
 만들고 대화 상자 모음을 사용 하는 것 만들고 사용 하는 `CFormView` 개체입니다.  먼저 사용 하는  [대화 상자 편집기](../../mfc/dialog-editor.md) 대화 서식 파일에 스타일 정의에  **WS\_CHILD** 및 기타 스타일 없음.  서식 파일의 스타일에 있어야  **WS\_VISIBLE**.  생성 하는 생성자를 호출 하는 응용 프로그램 코드에는 `CDialogBar` 개체를 호출 하 고  **만들기** 대화 상자 표시줄 창을 만들고 연결할 수는 `CDialogBar` 개체.  
  
 에 대 한 자세한 내용은 `CDialogBar`, 문서를 참조 하십시오.  [대화 상자 막대](../../mfc/dialog-bars.md) 및  [기술 참고 31](../../mfc/tn031-control-bars.md), 컨트롤 막대입니다.  
  
> [!NOTE]
>  현재 릴리스에서 `CDialogBar` 개체 Windows Forms 컨트롤을 호스팅할 수 없습니다.  Visual C\+\+에서 Windows Forms 컨트롤에 대 한 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## 요구 사항  
 **헤더:**  afxext.h  
  
## 참고 항목  
 [CTRLBARS MFC 샘플](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)