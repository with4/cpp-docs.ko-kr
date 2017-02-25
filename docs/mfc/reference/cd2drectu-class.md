---
title: "CD2DRectU 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DRectU"
  - "afxrendertarget/CD2DRectU"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DRectU 클래스"
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CD2DRectU 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

래퍼에 대 한 `D2D1_RECT_U`.  
  
## 구문  
  
```  
class CD2DRectU : public D2D1_RECT_U;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DRectU::CD2DRectU](../Topic/CD2DRectU::CD2DRectU.md)|오버로드.  생성 된 `CD2DRectU` 개체에서 `D2D1_RECT_U` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DRectU::IsNull](../Topic/CD2DRectU::IsNull.md)|반환 된 `boolean` 식에 유효한 데이터가 포함 되어 있는지 여부를 나타내는 값 \(`null`\).|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DRectU::operator CRect](../Topic/CD2DRectU::operator%20CRect.md)|변환 `CD2DRectU` 에 `CRect` 개체입니다.|  
  
## 상속 계층 구조  
 `D2D1_RECT_U`  
  
 [CD2DRectU](../../mfc/reference/cd2drectu-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)