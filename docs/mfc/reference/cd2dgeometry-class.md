---
title: "CD2DGeometry 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DGeometry"
  - "afxrendertarget/CD2DGeometry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DGeometry 클래스"
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DGeometry 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1Geometry에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DGeometry : public CD2DResource;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DGeometry::CD2DGeometry](../Topic/CD2DGeometry::CD2DGeometry.md)|CD2DGeometry 개체를 생성합니다.|  
|[CD2DGeometry::~CD2DGeometry](../Topic/CD2DGeometry::~CD2DGeometry.md)|소멸자  D2D 기하 도형 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DGeometry::Attach](../Topic/CD2DGeometry::Attach.md)|개체에 기존 리소스 인터페이스를 연결합니다.|  
|[CD2DGeometry::CombineWithGeometry](../Topic/CD2DGeometry::CombineWithGeometry.md)|이 기하 도형을 지정된 기하 도형과 결합하고 결과를 ID2D1SimplifiedGeometrySink에 저장합니다.|  
|[CD2DGeometry::CompareWithGeometry](../Topic/CD2DGeometry::CompareWithGeometry.md)|이 기하 도형과 지정된 기하 도형 사이의 교집합을 설명합니다.  지정한 평면화 허용 오차를 사용하여 비교가 수행됩니다.|  
|[CD2DGeometry::ComputeArea](../Topic/CD2DGeometry::ComputeArea.md)|지정된 매트릭스에 의해 변환되고 지정된 내결함성을 사용하여 결합된 후에 기하 도형의 영역을 계산합니다.|  
|[CD2DGeometry::ComputeLength](../Topic/CD2DGeometry::ComputeLength.md)|각 세그먼트가 선으로 펼쳐진 것처럼 기하 도형의 길이를 계산합니다.|  
|[CD2DGeometry::ComputePointAtLength](../Topic/CD2DGeometry::ComputePointAtLength.md)|지정된 매트릭스에 의해 변환되고 지정된 내결함성을 사용하여 결합된 후에 기하 도형을 따라 지정된 거리에서 점과 탄젠트 벡터를 계산합니다.|  
|[CD2DGeometry::Destroy](../Topic/CD2DGeometry::Destroy.md)|CD2DGeometry 개체를 소멸시킵니다.  \([CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md) 무시.\)|  
|[CD2DGeometry::Detach](../Topic/CD2DGeometry::Detach.md)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DGeometry::FillContainsPoint](../Topic/CD2DGeometry::FillContainsPoint.md)|지정된 결합 내결함성이 있는 경우 기하 도형에서 채운 영역이 지정된 지점을 포함하지 않음을 나타냅니다.|  
|[CD2DGeometry::Get](../Topic/CD2DGeometry::Get.md)|ID2D1Geometry 인터페이스를 반환합니다.|  
|[CD2DGeometry::GetBounds](../Topic/CD2DGeometry::GetBounds.md)||  
|[CD2DGeometry::GetWidenedBounds](../Topic/CD2DGeometry::GetWidenedBounds.md)|지정된 스트로크 너비와 스타일로 확장되고 지정된 매트릭스에 의해 변환된 후에 기하 도형의 범위를 가져옵니다.|  
|[CD2DGeometry::IsValid](../Topic/CD2DGeometry::IsValid.md)|리소스 유효성 검사\([CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md) 무시\)|  
|[CD2DGeometry::Outline](../Topic/CD2DGeometry::Outline.md)|기하 도형의 윤곽을 계산하고 결과를 ID2D1SimplifiedGeometrySink에 기록합니다.|  
|[CD2DGeometry::Simplify](../Topic/CD2DGeometry::Simplify.md)|선 및\(선택적으로\) 입방형 3차원 곡선을 포함하는 기하 도형의 단순화된 버전을 만들고 결과를 ID2D1SimplifiedGeometrySink에 씁니다.|  
|[CD2DGeometry::StrokeContainsPoint](../Topic/CD2DGeometry::StrokeContainsPoint.md)|기하 도형에 지정된 스트로크 두께, 스타일 및 변환이 주어진 지정된 점이 포함되는지 여부를 확인합니다.|  
|[CD2DGeometry::Tessellate](../Topic/CD2DGeometry::Tessellate.md)|지정된 매트릭스를 사용하여 변환되고 지정된 내결함성을 사용하여 결합된 후에 기하 도형을 포함하는 시계 방향으로 감긴 삼각형 집합을 만듭니다.|  
|[CD2DGeometry::Widen](../Topic/CD2DGeometry::Widen.md)|지정된 스트로크만큼 기하 도형을 넓히고 지정된 매트릭스로 변환하고 지정된 허용 오차를 사용하여 결합한 후에 결과를 ID2D1SimplifiedGeometrySink에 씁니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DGeometry::operator ID2D1Geometry\*](../Topic/CD2DGeometry::operator%20ID2D1Geometry*.md)|ID2D1Geometry 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DGeometry::m\_pGeometry](../Topic/CD2DGeometry::m_pGeometry.md)|ID2D1Geometry에 대한 포인터입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)