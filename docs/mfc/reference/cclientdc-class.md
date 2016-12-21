---
title: "CClientDC Class | Microsoft Docs"
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
  - "CClientDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CClientDC class"
  - "CDC 클래스, device contexts for client areas"
  - "client-area device context"
  - "device contexts, 클라이언트 영역"
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CClientDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 함수 호출을 수행 합니다.  [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) 생성할 때 및  [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) 소멸 시.  
  
## 구문  
  
```  
  
class CClientDC : public CDC  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CClientDC::CClientDC](../Topic/CClientDC::CClientDC.md)|생성 된 `CClientDC` 연결 개체는 `CWnd`.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CClientDC::m\_hWnd](../Topic/CClientDC::m_hWnd.md)|`HWND` 이 창 `CClientDC` 유효 합니다.|  
  
## 설명  
 즉 관련 된 장치 컨텍스트를 `CClientDC` 개체 창의 클라이언트 영역입니다.  
  
 에 대 한 자세한 내용은 `CClientDC`를 참조 하십시오  [장치 컨텍스트](../../mfc/device-contexts.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [MDI MFC 샘플](../../top/visual-cpp-samples.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)