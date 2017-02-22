---
title: "CD2DMesh 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DMesh"
  - "CD2DMesh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DMesh 클래스"
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DMesh 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1Mesh에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DMesh : public CD2DResource;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DMesh::CD2DMesh](../Topic/CD2DMesh::CD2DMesh.md)|CD2DMesh 개체를 생성합니다.|  
|[CD2DMesh::~CD2DMesh](../Topic/CD2DMesh::~CD2DMesh.md)|소멸자  D2D 메시 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DMesh::Attach](../Topic/CD2DMesh::Attach.md)|개체에 기존 리소스 인터페이스를 연결합니다.|  
|[CD2DMesh::Create](../Topic/CD2DMesh::Create.md)|CD2DMesh를 만듭니다.  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) 무시.\)|  
|[CD2DMesh::Destroy](../Topic/CD2DMesh::Destroy.md)|CD2DMesh 개체를 소멸시킵니다.  \([CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md) 무시.\)|  
|[CD2DMesh::Detach](../Topic/CD2DMesh::Detach.md)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DMesh::Get](../Topic/CD2DMesh::Get.md)|ID2D1Mesh 인터페이스를 반환합니다.|  
|[CD2DMesh::IsValid](../Topic/CD2DMesh::IsValid.md)|리소스 유효성 검사\([CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md) 무시\)|  
|[CD2DMesh::Open](../Topic/CD2DMesh::Open.md)|채우기 위해 메시를 엽니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DMesh::operator ID2D1Mesh\*](../Topic/CD2DMesh::operator%20ID2D1Mesh*.md)|ID2D1Mesh 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DMesh::m\_pMesh](../Topic/CD2DMesh::m_pMesh.md)|ID2D1Mesh에 대한 포인터입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DMesh](../../mfc/reference/cd2dmesh-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)