---
title: "CHtmlEditCtrl Class | Microsoft Docs"
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
  - "CHtmlEditCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditCtrl class"
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHtmlEditCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC 창에서 ActiveX WebBrowser 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CHtmlEditCtrl: public CWnd,   
   public CHtmlEditCtrlBase< CHtmlEditCtrl >  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](../Topic/CHtmlEditCtrl::CHtmlEditCtrl.md)|`CHtmlEditCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHtmlEditCtrl::Create](../Topic/CHtmlEditCtrl::Create.md)|ActiveX WebBrowser 컨트롤을 만들고이에 연결 된 `CHtmlEditCtrl` 개체입니다.  이 함수는 자동으로 ActiveX WebBrowser 컨트롤이 편집 모드로 전환 됩니다.|  
|[CHtmlEditCtrl::GetDHtmlDocument](../Topic/CHtmlEditCtrl::GetDHtmlDocument.md)|검색 된  [IHTMLDocument2](https://msdn.microsoft.com/en-us/library/aa752574.aspx) 인터페이스는 문서에 포함 된 WebBrowser 컨트롤에 현재 로드 된.|  
|[CHtmlEditCtrl::GetStartDocument](../Topic/CHtmlEditCtrl::GetStartDocument.md)|포함 된 WebBrowser 컨트롤에 로드 하는 기본 문서 URL을 검색 합니다.|  
  
## 설명  
 편집 모드로 만들어진 WebBrowser 호스트 컨트롤에 자동으로 배치 됩니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHtmlEditCtrl`  
  
## 요구 사항  
 **헤더:** afxhtml.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)