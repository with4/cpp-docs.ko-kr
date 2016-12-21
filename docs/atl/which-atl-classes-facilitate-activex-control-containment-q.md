---
title: "Which ATL Classes Facilitate ActiveX Control Containment? | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤 컨테이너[C++], ATL control hosting"
  - "hosting controls using ATL"
ms.assetid: 803a4605-7f4c-4139-8638-49d8783d31b0
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Which ATL Classes Facilitate ActiveX Control Containment?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL의 컨트롤 호스팅 코드는 ATL 클래스를 사용 하 여 필요 하지 않습니다. 간단 하 게 만들 수 있습니다는  **"AtlAxWin80"** 창이 필요한 경우 컨트롤 호스팅 API 사용 하 고 \(자세한 내용은  [ATL 컨트롤 호스팅 API는 무엇입니까?](../atl/what-is-the-atl-control-hosting-api-q.md)\).  그러나 다음 클래스 제약 기능을 쉽게 사용할 수 있도록 합니다.  
  
|클래스|설명|  
|---------|--------|  
|[CAxWindow](../atl/reference/caxwindow-class.md)|래핑하는  **"AtlAxWin80"** 창, 창 만들기, 컨트롤 만들기 및 컨트롤을 창에 연결 및 호스트 개체에서 인터페이스 포인터를 검색에 대 한 메서드를 제공 합니다.|  
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|래핑하는  **"AtlAxWinLic80"** 창에서 창을 만들기, 컨트롤 만들기 및\/또는 라이센스가 있는 컨트롤에는 창에 연결 하 고 호스트 개체에서 인터페이스 포인터를 검색에 대 한 메서드를 제공 합니다.|  
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|대화 상자 리소스를 기반으로 하는 ActiveX 컨트롤 클래스의 기본 클래스 역할을 합니다.  이러한 컨트롤이 다른 ActiveX 컨트롤을 포함할 수 있습니다.|  
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|대화 상자 리소스를 기반으로 하는 대화 상자 클래스에 대 한 기본 클래스 역할을 합니다.  이러한 대화 상자는 ActiveX 컨트롤을 포함할 수 있습니다.|  
|[CWindow](../atl/reference/cwindow-class.md)|하는 방법을 제공  [GetDlgControl](../Topic/CWindow::GetDlgControl.md), 호스트 창의 ID를 지정 하 여 컨트롤에 대 한 인터페이스 포인터 반환할 수 있습니다.  또한 Windows API 래퍼 노출 하 여 `CWindow` 일반적으로 창 관리를 쉽게 합니다.|  
  
## 참고 항목  
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)