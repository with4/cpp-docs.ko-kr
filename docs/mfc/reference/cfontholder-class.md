---
title: "CFontHolder Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFontHolder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFontHolder class"
  - "custom fonts"
  - "글꼴, ActiveX 컨트롤"
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CFontHolder Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스톡 Font 속성을 구현 하 고 Windows 글꼴 개체의 기능을 캡슐화 하는 `IFont` 인터페이스.  
  
## 구문  
  
```  
class CFontHolder  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFontHolder::CFontHolder](../Topic/CFontHolder::CFontHolder.md)|`CFontHolder` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFontHolder::GetDisplayString](../Topic/CFontHolder::GetDisplayString.md)|컨테이너의 속성 브라우저에 표시 되는 문자열을 검색 합니다.|  
|[CFontHolder::GetFontDispatch](../Topic/CFontHolder::GetFontDispatch.md)|글꼴의 반환 `IDispatch` 인터페이스.|  
|[CFontHolder::GetFontHandle](../Topic/CFontHolder::GetFontHandle.md)|Windows 글꼴에는 핸들을 반환합니다.|  
|[CFontHolder::InitializeFont](../Topic/CFontHolder::InitializeFont.md)|`CFontHolder` 개체를 초기화합니다.|  
|[CFontHolder::QueryTextMetrics](../Topic/CFontHolder::QueryTextMetrics.md)|관련된 된 글꼴에 대 한 정보를 검색합니다.|  
|[CFontHolder::ReleaseFont](../Topic/CFontHolder::ReleaseFont.md)|연결 해제는 `CFontHolder` 에서 개체는 `IFont` 및 `IFontNotification` 인터페이스.|  
|[CFontHolder::Select](../Topic/CFontHolder::Select.md)|글꼴 리소스를 디바이스 컨텍스트로 선택합니다.|  
|[CFontHolder::SetFont](../Topic/CFontHolder::SetFont.md)|연결 되는 `CFontHolder` 개체는 `IFont` 인터페이스.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CFontHolder::m\_pFont](../Topic/CFontHolder::m_pFont.md)|에 대 한 포인터는 `CFontHolder` 개체의 `IFont` 인터페이스.|  
  
## 설명  
 `CFontHolder`기본 클래스에 없는 것입니다.  
  
 컨트롤에 대해 사용자 지정 font 속성을 구현 하려면이 클래스를 사용 합니다.  이러한 속성을 만드는 방법에 대 한 내용은  [ActiveX 컨트롤: 글꼴을 사용 하 여](../../mfc/mfc-activex-controls-using-fonts.md).  
  
## 상속 계층 구조  
 `CFontHolder`  
  
## 요구 사항  
 **헤더:**  afxctl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPropExchange Class](../../mfc/reference/cpropexchange-class.md)