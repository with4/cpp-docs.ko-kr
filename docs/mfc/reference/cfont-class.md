---
title: "CFont Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFont"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFont class"
  - "글꼴, MFC 클래스"
  - "GDI, font classes"
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CFont Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 그래픽 장치 인터페이스 \(GDI\) 글꼴을 캡슐화 하 고 글꼴을 조작 하기 위한 멤버 함수를 제공 합니다.  
  
## 구문  
  
```  
class CFont : public CGdiObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFont::CFont](../Topic/CFont::CFont.md)|`CFont` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFont::CreateFont](../Topic/CFont::CreateFont.md)|초기화는 `CFont` 지정 된 특성을 가진.|  
|[CFont::CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md)|초기화는 `CFont` 에서 특성을 가진 개체는 `LOGFONT` 구조.|  
|[CFont::CreatePointFont](../Topic/CFont::CreatePointFont.md)|초기화는 `CFont` 지정 된 높이를 측정 지점 및 서체를 10 배로.|  
|[CFont::CreatePointFontIndirect](../Topic/CFont::CreatePointFontIndirect.md)|동일 `CreateFontIndirect` 글꼴 높이 논리 단위 보다는 지점에 10 단위로 측정을 제외 하 고.|  
|[CFont::FromHandle](../Topic/CFont::FromHandle.md)|반환에 대 한 포인터는 `CFont` 개체는 Windows에 주어 지 면  **HFONT**.|  
|[CFont::GetLogFont](../Topic/CFont::GetLogFont.md)|채우기는 `LOGFONT` 연결 논리 글꼴에 대 한 정보는 `CFont` 개체.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CFont::operator HFONT](../Topic/CFont::operator%20HFONT.md)|Windows GDI 글꼴 핸들에 연결 된 반환 된 `CFont` 개체입니다.|  
  
## 설명  
 사용 하는 `CFont` 개체, 구성는 `CFont` 개체 및 Windows 글꼴에 연결  [CreateFont](../Topic/CFont::CreateFont.md),  [CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md),  [CreatePointFont](../Topic/CFont::CreatePointFont.md), 또는  [CreatePointFontIndirect](../Topic/CFont::CreatePointFontIndirect.md), 및 개체의 멤버 함수를 사용 하 여 글꼴을 조작할 수 있습니다.  
  
 `CreatePointFont` 및 `CreatePointFontIndirect` 함수는 자주 사용 하 여 보다 쉽게 `CreateFont` 또는 `CreateFontIndirect` 글꼴의 높이 대 한 변환 크기에서 논리 단위를 자동으로 하지 않으므로.  
  
 에 대 한 자세한 내용은 `CFont`를 참조 하십시오  [그래픽 개체](../../mfc/graphic-objects.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [HIERSVR MFC 샘플](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)