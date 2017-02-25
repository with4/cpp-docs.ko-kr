---
title: "COleControlModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControlModule class"
  - "control modules"
  - "MFC ActiveX controls, OLE control modules"
  - "OLE control modules"
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleControlModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 제어 모듈 개체에서 파생 되는 기본 클래스입니다.  
  
## 구문  
  
```  
class COleControlModule : public CWinApp  
```  
  
## 설명  
 이 클래스는 컨트롤 모듈을 초기화 하는 멤버 함수를 제공 합니다.  Mfc 클래스를 사용 하 여 각 OLE 컨트롤 모듈에서 파생 한 개체는 포함할 수 있습니다 `COleControlModule`.  이 개체는 다른 C\+\+ 전역 개체를 만들 때 생성 됩니다.  선언 하면 파생 된 `COleControlModule` 개체는 전역 수준에서.  
  
 사용에 대 한 자세한 내용은 `COleControlModule` 클래스를 참조 하십시오의  [CWinApp](../../mfc/reference/cwinapp-class.md) 클래스 및 문서  [ActiveX 컨트롤](../../mfc/mfc-activex-controls.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## 요구 사항  
 **헤더:**  afxctl.h  
  
## 참고 항목  
 [TESTHELP MFC 샘플](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)