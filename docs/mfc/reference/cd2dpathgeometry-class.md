---
title: "CD2DPathGeometry 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DPathGeometry"
  - "CD2DPathGeometry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DPathGeometry 클래스"
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DPathGeometry 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1PathGeometry에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DPathGeometry : public CD2DGeometry;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DPathGeometry::CD2DPathGeometry](../Topic/CD2DPathGeometry::CD2DPathGeometry.md)|CD2DPathGeometry 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DPathGeometry::Attach](../Topic/CD2DPathGeometry::Attach.md)|개체에 기존 리소스 인터페이스를 연결합니다.|  
|[CD2DPathGeometry::Create](../Topic/CD2DPathGeometry::Create.md)|CD2DPathGeometry를 만듭니다.  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) 무시.\)|  
|[CD2DPathGeometry::Destroy](../Topic/CD2DPathGeometry::Destroy.md)|CD2DPathGeometry 개체를 소멸시킵니다.  \([CD2DGeometry::Destroy](../Topic/CD2DGeometry::Destroy.md) 무시.\)|  
|[CD2DPathGeometry::Detach](../Topic/CD2DPathGeometry::Detach.md)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DPathGeometry::GetFigureCount](../Topic/CD2DPathGeometry::GetFigureCount.md)|기하학적 경로에서 그림 수를 검색합니다.|  
|[CD2DPathGeometry::GetSegmentCount](../Topic/CD2DPathGeometry::GetSegmentCount.md)|기하학적 경로에서 세그먼트 수를 검색합니다.|  
|[CD2DPathGeometry::Open](../Topic/CD2DPathGeometry::Open.md)|기하학적 경로를 수치 및 세그먼트로 채우는 데 사용되는 기하 도형 싱크를 검색합니다.|  
|[CD2DPathGeometry::Stream](../Topic/CD2DPathGeometry::Stream.md)|기하학적 경로의 내용을 지정된 ID2D1GeometrySink에 복사합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DPathGeometry::m\_pPathGeometry](../Topic/CD2DPathGeometry::m_pPathGeometry.md)|ID2D1PathGeometry에 대한 포인터입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)  
  
 [CD2DPathGeometry](../../mfc/reference/cd2dpathgeometry-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)