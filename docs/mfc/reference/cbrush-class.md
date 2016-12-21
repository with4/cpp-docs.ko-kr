---
title: "CBrush Class | Microsoft Docs"
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
  - "CBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "브러시, CBrush class"
  - "CBrush class"
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBrush Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 그래픽 장치 인터페이스 \(GDI\) 브러시를 캡슐화합니다.  
  
## 구문  
  
```  
class CBrush : public CGdiObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CBrush::CBrush](../Topic/CBrush::CBrush.md)|`CBrush` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CBrush::CreateBrushIndirect](../Topic/CBrush::CreateBrushIndirect.md)|스타일, 색 및 무늬 지정 브러시로 초기화는  [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) 구조.|  
|[CBrush::CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md)|장치 독립적 비트맵 \(DIB\)에서 지정한 패턴 브러시를 초기화 합니다.|  
|[CBrush::CreateHatchBrush](../Topic/CBrush::CreateHatchBrush.md)|지정 된 해치 패턴 및 색 브러시를 초기화합니다.|  
|[CBrush::CreatePatternBrush](../Topic/CBrush::CreatePatternBrush.md)|비트맵에서 지정한 패턴 브러시를 초기화 합니다.|  
|[CBrush::CreateSolidBrush](../Topic/CBrush::CreateSolidBrush.md)|지정 된 단색 브러시를 초기화합니다.|  
|[CBrush::CreateSysColorBrush](../Topic/CBrush::CreateSysColorBrush.md)|기본 시스템 색은 브러시를 만듭니다.|  
|[CBrush::FromHandle](../Topic/CBrush::FromHandle.md)|반환에 대 한 포인터는 `CBrush` 개체 핸들은 Windows에 지정 되 면 `HBRUSH` 개체.|  
|[CBrush::GetLogBrush](../Topic/CBrush::GetLogBrush.md)|가져옵니다는  [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) 구조.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CBrush::operator HBRUSH](../Topic/CBrush::operator%20HBRUSH.md)|연결에 대 한 Windows 핸들을 반환의 `CBrush` 개체입니다.|  
  
## 설명  
 사용 하는 `CBrush` 개체, 구성 된 `CBrush` 개체에 전달 하 고 `CDC` 브러시를 필요로 하는 멤버 함수.  
  
 부 화, 또는 무늬 브러시 단색을 수 있습니다.  
  
 에 대 한 자세한 내용은 `CBrush`를 참조 하십시오  [그래픽 개체](../../mfc/graphic-objects.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [PROPDLG MFC 샘플](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CBitmap Class](../../mfc/reference/cbitmap-class.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)