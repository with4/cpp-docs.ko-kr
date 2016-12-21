---
title: "CPictureHolder Class | Microsoft Docs"
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
  - "Picture"
  - "CPictureHolder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨트롤[MFC], OLE"
  - "CPictureHolder class"
  - "OLE 컨트롤, 이미지"
  - "Picture property"
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPictureHolder Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

그림 컨트롤을 표시할 수 있도록 하는 Picture 속성을 구현 합니다.  
  
## 구문  
  
```  
class CPictureHolder  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPictureHolder::CPictureHolder](../Topic/CPictureHolder::CPictureHolder.md)|`CPictureHolder` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPictureHolder::CreateEmpty](../Topic/CPictureHolder::CreateEmpty.md)|빈 `CPictureHolder` 개체를 만듭니다.|  
|[CPictureHolder::CreateFromBitmap](../Topic/CPictureHolder::CreateFromBitmap.md)|생성 한 `CPictureHolder` 에서 비트맵 개체.|  
|[CPictureHolder::CreateFromIcon](../Topic/CPictureHolder::CreateFromIcon.md)|생성 한 `CPictureHolder` 개체 아이콘에서.|  
|[CPictureHolder::CreateFromMetafile](../Topic/CPictureHolder::CreateFromMetafile.md)|생성 한 `CPictureHolder` 개체에서 메타 파일.|  
|[CPictureHolder::GetDisplayString](../Topic/CPictureHolder::GetDisplayString.md)|컨트롤 컨테이너의 속성 브라우저에 표시 되는 문자열을 검색 합니다.|  
|[CPictureHolder::GetPictureDispatch](../Topic/CPictureHolder::GetPictureDispatch.md)|반환 된 `CPictureHolder` 개체의 `IDispatch` 인터페이스.|  
|[CPictureHolder::GetType](../Topic/CPictureHolder::GetType.md)|지시 여부는 `CPictureHolder` 개체는 메타 파일, 비트맵, 아이콘입니다.|  
|[CPictureHolder::Render](../Topic/CPictureHolder::Render.md)|그림을 렌더링합니다.|  
|[CPictureHolder::SetPictureDispatch](../Topic/CPictureHolder::SetPictureDispatch.md)|집합의 `CPictureHolder` 개체의 `IDispatch` 인터페이스.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPictureHolder::m\_pPict](../Topic/CPictureHolder::m_pPict.md)|그림 개체에 대 한 포인터입니다.|  
  
## 설명  
 `CPictureHolder`기본 클래스에 없는 것입니다.  
  
 스톡 Picture 속성에 비트맵, 아이콘 또는 메타 파일 표시에 대 한 개발자를 지정할 수 있습니다.  
  
 사용자 지정 그림 속성 만들기에 대 한 자세한 내용은  [ActiveX MFC 컨트롤: ActiveX 컨트롤에서을 사용 하 여 그림](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md).  
  
## 상속 계층 구조  
 `CPictureHolder`  
  
## 요구 사항  
 **헤더:**  afxctl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFontHolder Class](../../mfc/reference/cfontholder-class.md)