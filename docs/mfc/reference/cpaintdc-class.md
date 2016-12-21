---
title: "CPaintDC Class | Microsoft Docs"
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
  - "CPaintDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaintDC class"
  - "OnPaint handler"
  - "WM_PAINT message"
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPaintDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

디바이스 컨텍스트 클래스에서 파생 된  [CDC](../../mfc/reference/cdc-class.md).  
  
## 구문  
  
```  
class CPaintDC : public CDC  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPaintDC::CPaintDC](../Topic/CPaintDC::CPaintDC.md)|생성 된 `CPaintDC` 에 지정 된 연결  [CWnd](../../mfc/reference/cwnd-class.md).|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPaintDC::m\_ps](../Topic/CPaintDC::m_ps.md)|포함 된  [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) 클라이언트 영역을 그리는 데 사용 합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPaintDC::m\_hWnd](../Topic/CPaintDC::m_hWnd.md)|`HWND` 이 `CPaintDC` 개체를 연결 합니다.|  
  
## 설명  
 수행 된  [CWnd::BeginPaint](../Topic/CWnd::BeginPaint.md) 생성할 때 및  [CWnd::EndPaint](../Topic/CWnd::EndPaint.md) 소멸 시.  
  
 A `CPaintDC` 개체에 응답할 때만 사용할 수 있습니다는  [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) 에 일반적으로 메시지를 `OnPaint` 메시지 처리기 멤버 함수입니다.  
  
 사용에 대 한 자세한 내용은 `CPaintDC`를 참조 하십시오  [장치 컨텍스트](../../mfc/device-contexts.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [MDI MFC 샘플](../../top/visual-cpp-samples.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)