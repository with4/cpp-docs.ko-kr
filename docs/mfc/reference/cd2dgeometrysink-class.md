---
title: "CD2DGeometrySink 클래스 | Microsoft Docs"
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
  - "afxrendertarget/CD2DGeometrySink"
  - "CD2DGeometrySink"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DGeometrySink 클래스"
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DGeometrySink 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1GeometrySink에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DGeometrySink;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DGeometrySink::CD2DGeometrySink](../Topic/CD2DGeometrySink::CD2DGeometrySink.md)|CD2DPathGeometry 개체에서 CD2DGeometrySink 개체를 생성합니다.|  
|[CD2DGeometrySink::~CD2DGeometrySink](../Topic/CD2DGeometrySink::~CD2DGeometrySink.md)|소멸자  D2D 기하 도형 싱크 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DGeometrySink::AddArc](../Topic/CD2DGeometrySink::AddArc.md)|단일 호를 기하학적 경로에 추가합니다.|  
|[CD2DGeometrySink::AddBezier](../Topic/CD2DGeometrySink::AddBezier.md)|현재 지점과 지정한 끝점 사이에 입방형 3차원 곡선을 만듭니다.|  
|[CD2DGeometrySink::AddBeziers](../Topic/CD2DGeometrySink::AddBeziers.md)|일련의 입방형 3차원 곡선을 만들고 기하 도형 싱크에 추가합니다.|  
|[CD2DGeometrySink::AddLine](../Topic/CD2DGeometrySink::AddLine.md)|현재 지점과 지정한 끝점 사이에 선 세그먼트를 만들고 기하 도형 싱크에 추가합니다.|  
|[CD2DGeometrySink::AddLines](../Topic/CD2DGeometrySink::AddLines.md)|지정된 점을 사용하여 일련의 선을 만들고 기하 도형 싱크에 추가합니다.|  
|[CD2DGeometrySink::AddQuadraticBezier](../Topic/CD2DGeometrySink::AddQuadraticBezier.md)|현재 지점과 지정한 끝점 사이에 정방형 3차원 곡선을 만듭니다.|  
|[CD2DGeometrySink::AddQuadraticBeziers](../Topic/CD2DGeometrySink::AddQuadraticBeziers.md)|한 번의 호출로 일련의 정방형 3차원 곡선 세그먼트를 배욜로 추가합니다.|  
|[CD2DGeometrySink::BeginFigure](../Topic/CD2DGeometrySink::BeginFigure.md)|지정한 점에서 새 그림을 시작합니다.|  
|[CD2DGeometrySink::Close](../Topic/CD2DGeometrySink::Close.md)|기하 도형 싱크를 닫습니다.|  
|[CD2DGeometrySink::EndFigure](../Topic/CD2DGeometrySink::EndFigure.md)|현재 그림을 끝내고 선택적으로 닫습니다.|  
|[CD2DGeometrySink::Get](../Topic/CD2DGeometrySink::Get.md)|ID2D1GeometrySink 인터페이스를 반환합니다.|  
|[CD2DGeometrySink::IsValid](../Topic/CD2DGeometrySink::IsValid.md)|기하 도형 싱크 유효성을 검사합니다.|  
|[CD2DGeometrySink::SetFillMode](../Topic/CD2DGeometrySink::SetFillMode.md)|어떤 점이 이 기하 도형 싱크에 의해 설명되는 기하 도형 내에 있으며 어떤 점이 밖에 있는지 결정하는 데 사용되는 메서드를 지정합니다.|  
|[CD2DGeometrySink::SetSegmentFlags](../Topic/CD2DGeometrySink::SetSegmentFlags.md)|기하 도형 싱크에 추가된 새 세그먼트에 적용할 스트로크 및 조인 옵션을 지정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DGeometrySink::operator ID2D1GeometrySink\*](../Topic/CD2DGeometrySink::operator%20ID2D1GeometrySink*.md)|ID2D1GeometrySink 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DGeometrySink::m\_pSink](../Topic/CD2DGeometrySink::m_pSink.md)|ID2D1GeometrySink에 대한 포인터입니다.|  
  
## 상속 계층 구조  
 [CD2DGeometrySink](../../mfc/reference/cd2dgeometrysink-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)