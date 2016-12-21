---
title: "CSize Class | Microsoft Docs"
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
  - "CSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSize class"
  - "차원"
  - "차원, MFC"
  - "SIZE"
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSize Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows와 마찬가지로  [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 상대 좌표 또는 위치를 구현 하는 구조입니다.  
  
## 구문  
  
```  
class CSize : public tagSIZE  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSize::CSize](../Topic/CSize::CSize.md)|`CSize` 개체를 생성합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CSize::operator \-](../Topic/CSize::operator%20-.md)|두 개의 크기를 뺍니다.|  
|[CSize::operator \!\=](../Topic/CSize::operator%20!=.md)|다른 지 확인 `CSize` 및 크기.|  
|[CSize::operator \+](../Topic/CSize::operator%20+.md)|두 개의 크기를 추가합니다.|  
|[CSize::operator \+\=](../Topic/CSize::operator%20+=.md)|크기에 추가 `CSize`.|  
|[CSize::operator \-\=](../Topic/CSize::operator%20-=.md)|크기에서 뺀 `CSize`.|  
|[CSize::operator \=\=](../Topic/CSize::operator%20==.md)|같은지 확인 `CSize` 및 크기.|  
  
## 설명  
 이 클래스에서 파생 되는  **크기** 구조.  즉 전달 하면는 `CSize` 호출 매개 변수에서는  **크기** 와의 데이터 멤버는  **크기** 구조에 있는 데이터를 액세스할 수 있는 멤버의 `CSize`.  
  
 **Cx** 및  **cy** 멤버의  **크기** \(및 `CSize`\) 공개 됩니다.  또한 `CSize` 조작 하는 멤버 함수 구현에서  **크기** 구조.  
  
> [!NOTE]
>  공유 클래스 유틸리티에 대 한 자세한 내용은 \(와 같은 `CSize`\)를 참조 하십시오  [공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## 상속 계층 구조  
 `tagSIZE`  
  
 `CSize`  
  
## 요구 사항  
 **헤더:** atltypes.h  
  
## 참고 항목  
 [MDI MFC 샘플](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRect Class](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint Class](../../atl-mfc-shared/reference/cpoint-class.md)