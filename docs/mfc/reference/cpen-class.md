---
title: "CPen Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "HPEN"
  - "CPen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPen class"
  - "HPEN"
  - "펜, MFC"
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CPen Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 그래픽 장치 인터페이스 \(GDI\) 펜을 캡슐화합니다.  
  
## 구문  
  
```  
class CPen : public CGdiObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPen::CPen](../Topic/CPen::CPen.md)|`CPen` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPen::CreatePen](../Topic/CPen::CreatePen.md)|지정 된 스타일, 너비 및 브러쉬 특성을 논리 코스메틱 또는 형상 펜 만들고를 연결의 `CPen` 개체.|  
|[CPen::CreatePenIndirect](../Topic/CPen::CreatePenIndirect.md)|펜, 스타일, 너비 및 색에서 만듭니다는  [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) 구조, 및 연결 하는 `CPen` 개체.|  
|[CPen::FromHandle](../Topic/CPen::FromHandle.md)|반환에 대 한 포인터는 `CPen` 개체는 Windows를 지정한 경우 `HPEN`.|  
|[CPen::GetExtLogPen](../Topic/CPen::GetExtLogPen.md)|가져옵니다는  [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) 구조를 원본으로 사용 합니다.|  
|[CPen::GetLogPen](../Topic/CPen::GetLogPen.md)|가져옵니다는  [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) 구조를 원본으로 사용 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CPen::operator HPEN](../Topic/CPen::operator%20HPEN.md)|연결에 대 한 Windows 핸들을 반환의 `CPen` 개체입니다.|  
  
## 설명  
 사용에 대 한 자세한 내용은 `CPen`를 참조 하십시오  [그래픽 개체](../../mfc/graphic-objects.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CBrush Class](../../mfc/reference/cbrush-class.md)