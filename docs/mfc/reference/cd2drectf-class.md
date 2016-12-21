---
title: "CD2DRectF 클래스 | Microsoft Docs"
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
  - "afxrendertarget/CD2DRectF"
  - "CD2DRectF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DRectF 클래스"
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DRectF 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

래퍼에 대 한 `D2D1_RECT_F`.  
  
## 구문  
  
```  
class CD2DRectF : public D2D1_RECT_F;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DRectF::CD2DRectF](../Topic/CD2DRectF::CD2DRectF.md)|오버로드.  생성 된 `CD2DRectF` 개체에서 `D2D1_RECT_F` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DRectF::IsNull](../Topic/CD2DRectF::IsNull.md)|반환 된 `boolean` 식에 유효한 데이터가 포함 되어 있는지 여부를 나타내는 값 \(`null`\).|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DRectF::operator CRect](../Topic/CD2DRectF::operator%20CRect.md)|변환 `CD2DRectF` 에 `CRect` 개체입니다.|  
  
## 상속 계층 구조  
 `D2D1_RECT_F`  
  
 [CD2DRectF](../../mfc/reference/cd2drectf-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)