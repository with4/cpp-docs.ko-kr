---
title: "CGdiObject Class | Microsoft Docs"
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
  - "CGdiObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "브러시, base class for"
  - "CGdiObject class"
  - "글꼴, base class for"
  - "GDI 개체, base class for"
  - "색상표, base class for"
  - "펜, base class for"
  - "영역, base class for"
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGdiObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 클래스에 대 한 다양 한 종류의 Windows 그래픽 비트맵, 영역, 브러시, 펜, 팔레트, 글꼴 및 장치 인터페이스 \(GDI\) 개체를 제공합니다.  
  
## 구문  
  
```  
class CGdiObject : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CGdiObject::CGdiObject](../Topic/CGdiObject::CGdiObject.md)|`CGdiObject` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CGdiObject::Attach](../Topic/CGdiObject::Attach.md)|Windows GDI 객체에 첨부 된 `CGdiObject` 개체입니다.|  
|[CGdiObject::CreateStockObject](../Topic/CGdiObject::CreateStockObject.md)|Windows의 미리 정의 된 스톡 펜, 브러시, 글꼴 중 하나에 대 한 핸들을 검색합니다.|  
|[CGdiObject::DeleteObject](../Topic/CGdiObject::DeleteObject.md)|삭제 Windows GDI 개체를 연결 하는 `CGdiObject` 개체와 관련 된 모든 시스템 저장소를 해제 하 여 메모리에서에서 개체를.|  
|[CGdiObject::DeleteTempMap](../Topic/CGdiObject::DeleteTempMap.md)|모든 임시 삭제 `CGdiObject` 개체에서 만든 `FromHandle`.|  
|[CGdiObject::Detach](../Topic/CGdiObject::Detach.md)|Windows GDI 개체에서 분리 된 `CGdiObject` 개체와 Windows GDI 개체에 핸들을 반환 합니다.|  
|[CGdiObject::FromHandle](../Topic/CGdiObject::FromHandle.md)|반환에 대 한 포인터는 `CGdiObject` Windows GDI 개체에 핸들을 지정 하는 개체입니다.|  
|[CGdiObject::GetObject](../Topic/CGdiObject::GetObject.md)|채우기 Windows GDI 개체를 설명 하는 데이터를 버퍼에 연결 된 `CGdiObject` 개체입니다.|  
|[CGdiObject::GetObjectType](../Topic/CGdiObject::GetObjectType.md)|GDI 개체를 검색합니다.|  
|[CGdiObject::GetSafeHandle](../Topic/CGdiObject::GetSafeHandle.md)|반환 `m_hObject` 하지 않으면 `this` 는 `NULL`경우에, `NULL` 반환 됩니다.|  
|[CGdiObject::UnrealizeObject](../Topic/CGdiObject::UnrealizeObject.md)|브러시의 원점을 다시 설정 하거나 논리 색상표를 다시 설정 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CGdiObject::operator \!\=](../Topic/CGdiObject::operator%20!=.md)|두 개의 GDI 개체가 다르면 논리적으로 결정 합니다.|  
|[CGdiObject::operator \=\=](../Topic/CGdiObject::operator%20==.md)|논리적으로 동일한 두 개의 GDI 개체가 있는지 확인 합니다.|  
|[CGdiObject::operator HGDIOBJ](../Topic/CGdiObject::operator%20HGDIOBJ.md)|검색은 `HANDLE` Windows GDI 개체를 연결 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CGdiObject::m\_hObject](../Topic/CGdiObject::m_hObject.md)|A `HANDLE` containing the `HBITMAP`, `HPALETTE`, `HRGN`, `HBRUSH`, `HPEN`, or `HFONT` attached to this object.|  
  
## 설명  
 절대로 생성 된 `CGdiObject` 직접.  대신 개체의 파생된 클래스 중 하나에서 같은 만듭니다 `CPen` 또는 `CBrush`.  
  
 `CGdiObject`에 대한 자세한 내용은 [그래픽 개체](../../mfc/graphic-objects.md)을 참조하십시오.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CBitmap Class](../../mfc/reference/cbitmap-class.md)   
 [CBrush Class](../../mfc/reference/cbrush-class.md)   
 [CFont Class](../../mfc/reference/cfont-class.md)   
 [CPalette Class](../../mfc/reference/cpalette-class.md)   
 [CPen Class](../../mfc/reference/cpen-class.md)   
 [CRgn 클래스](../../mfc/reference/crgn-class.md)