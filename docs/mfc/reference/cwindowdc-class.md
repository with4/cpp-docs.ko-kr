---
title: "CWindowDC Class | Microsoft Docs"
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
  - "CWindowDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWindowDC class"
  - "device contexts, window"
  - "screen output classes"
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWindowDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDC`에서 파생  
  
## 구문  
  
```  
class CWindowDC : public CDC  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CWindowDC::CWindowDC](../Topic/CWindowDC::CWindowDC.md)|`CWindowDC` 개체를 생성합니다.|  
  
### 보호된 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CWindowDC::m\_hWnd](../Topic/CWindowDC::m_hWnd.md)|이 `CWindowDC`가 연결된 `HWND`입니다.|  
  
## 설명  
 생성 시간에는 Windows 함수 [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)를 소멸 시간에는 Windows 함수 [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx)를 호출합니다.  즉, `CWindowDC` 개체는 [CWnd](../../mfc/reference/cwnd-class.md)의 전체 화면 영역\(클라이언트 및 비클라이언트 영역 모두\)에 액세스합니다.  
  
 `CWindowDC` 사용에 대한 자세한 내용은 [장치 컨텍스트](../../mfc/device-contexts.md)를 참조하십시오.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## 요구 사항  
 헤더: afxwin.h  
  
## 참고 항목  
 [CDC 클래스](../../mfc/reference/cdc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)