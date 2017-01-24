---
title: "CD2DSizeU 클래스 | Microsoft Docs"
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
  - "CD2DSizeU"
  - "afxrendertarget/CD2DSizeU"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DSizeU 클래스"
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DSizeU 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

D2D1\_SIZE\_U에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DSizeU : public D2D1_SIZE_U;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DSizeU::CD2DSizeU](../Topic/CD2DSizeU::CD2DSizeU.md)|오버로드.  생성 된 `CD2DSizeU` 개체에서 `D2D1_SIZE_U` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DSizeU::IsNull](../Topic/CD2DSizeU::IsNull.md)|반환 된 `boolean` 식에 유효한 데이터가 포함 되어 있는지 여부를 나타내는 값 \(`null`\).|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DSizeU::operator CSize](../Topic/CD2DSizeU::operator%20CSize.md)|변환 `CD2DSizeU` 에 `CSize` 개체입니다.|  
  
## 상속 계층 구조  
 `D2D1_SIZE_U`  
  
 [CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)