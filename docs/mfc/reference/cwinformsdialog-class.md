---
title: "CWinFormsDialog Class | Microsoft Docs"
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
  - "CWinFormsDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsDialog class"
  - "MFC[C++], Windows Forms 지원"
  - "Windows Forms[C++], MFC 지원"
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinFormsDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows Forms 사용자 정의 컨트롤을 호스팅하는 MFC 대화 상자 클래스에 대 한 래퍼.  
  
## 구문  
  
```  
template <typename TManagedControl>  
class CWinFormsDialog :   
   public CDialog  
```  
  
#### 매개 변수  
 `TManagedControl`  
 MFC 응용 프로그램의.NET Framework 사용자 컨트롤입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CWinFormsDialog::CWinFormsDialog](../Topic/CWinFormsDialog::CWinFormsDialog.md)|`CWinFormsDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWinFormsDialog::GetControl](../Topic/CWinFormsDialog::GetControl.md)|Windows Forms 사용자 정의 컨트롤에 대 한 참조를 검색합니다.|  
|[CWinFormsDialog::GetControlHandle](../Topic/CWinFormsDialog::GetControlHandle.md)|Windows Forms 사용자 정의 컨트롤에 대 한 창 핸들을 검색합니다.|  
|[CWinFormsDialog::OnInitDialog](../Topic/CWinFormsDialog::OnInitDialog.md)|만들고 Windows Forms 사용자 정의 컨트롤을 호스팅하는 MFC 대화 상자를 초기화 합니다.|  
  
### Public 연산자  
  
|Name||  
|----------|-|  
|[CWinFormsDialog::operator \-\>](../Topic/CWinFormsDialog::operator%20-%3E.md)|대체 [CWinFormsDialog::GetControl](../Topic/CWinFormsDialog::GetControl.md) 식에서입니다.|  
|[CWinFormsDialog::operator TManagedControl^](../Topic/CWinFormsDialog::operator%20TManagedControl%5E.md)|Windows Forms 사용자 정의 컨트롤에 대 한 참조는 형식을 비춥니다.|  
  
## 설명  
 `CWinFormsDialog`MFC 대화 상자 클래스에 대 한 래퍼입니다 \([CDialog](../../mfc/reference/cdialog-class.md)\)는 Windows Forms 호스트 \(<xref:System.Windows.Forms.UserControl>\) 사용자 정의 컨트롤입니다.  그러면.NET Framework 컨트롤 모달 또는 모덜리스 MFC 대화 상자에 표시 됩니다.  
  
 Windows Forms을 사용 하 여에 대 한 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md) 및 [Windows Form 사용자 정의 컨트롤을 MFC 대화 상자로 호스팅](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).  
  
## 요구 사항  
 **헤더:** afxwinforms.h  
  
## 참고 항목  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)