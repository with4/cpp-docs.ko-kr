---
title: "IView Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IView class"
  - "views [MFC]"
  - "뷰, 클래스"
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: 23
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IView Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

여러 가지 방법을 구현에서는  [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 사용 하 여 관리 되는 컨트롤에 알림을 보냅니다.  
  
## 구문  
  
```  
interface class IView  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IView::OnActivateView](../Topic/IView::OnActivateView.md)|보기를 활성화 또는 비활성화 하는 경우 MFC에서 호출 됩니다.|  
|[IView::OnInitialUpdate](../Topic/IView::OnInitialUpdate.md)|프레임 워크에서 보기는 문서에 처음 연결한 후 하지만 처음 보기를 표시 하기 전에 호출 됩니다.|  
|[IView::OnUpdate](../Topic/IView::OnUpdate.md)|보기의 문서를 수정한 후 MFC에서 호출 합니다. 이 함수 보기를 표시 수정 반영 하도록 업데이트할 수 있습니다.|  
  
## 설명  
 `IView`여러 메서드를 구현 하 `CWinFormsView` 사용 하 여 일반적인 알림을 관리 되는 호스팅된 컨트롤에 전달 합니다.  이러한  [OnInitialUpdate](../Topic/IView::OnInitialUpdate.md),  [OnUpdate](../Topic/IView::OnUpdate.md) 및  [OnActivateView](../Topic/IView::OnActivateView.md).  
  
 `IView`유사한  [CView](../../mfc/reference/cview-class.md), 관리 되는 뷰 및 컨트롤에만 사용 되지만.  
  
 Windows Forms을 사용 하 여에 대 한 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## 요구 사항  
 헤더: afxwinforms.h \(어셈블리 atlmfc\\lib\\mfcmifc80.dll에서 정의\)  
  
## 참고 항목  
 [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)