---
title: "CD2DSizeF 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DSizeF"
  - "CD2DSizeF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DSizeF 클래스"
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CD2DSizeF 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

D2D1\_SIZE\_F에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DSizeF : public D2D1_SIZE_F;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DSizeF::CD2DSizeF](../Topic/CD2DSizeF::CD2DSizeF.md)|오버로드.  생성 된 `CD2DSizeF` 개체에서 `D2D1_SIZE_F` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DSizeF::IsNull](../Topic/CD2DSizeF::IsNull.md)|반환 된 `boolean` 식에 유효한 데이터가 포함 되어 있는지 여부를 나타내는 값 \(`null`\).|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DSizeF::operator CSize](../Topic/CD2DSizeF::operator%20CSize.md)|변환 `CD2DSizeF` 에 `CSize` 개체입니다.|  
  
## 상속 계층 구조  
 `D2D1_SIZE_F`  
  
 [CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)