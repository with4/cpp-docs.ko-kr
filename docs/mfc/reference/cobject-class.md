---
title: "CObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "기본 클래스, MFC 개체"
  - "CObject class"
  - "object classes"
  - "개체[C++], base class for MFC"
ms.assetid: 95e9acd3-d9eb-4ac0-b52b-ca4a501a7a3a
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mfc 라이브러리에 대 한 기본 보안 주체 클래스입니다.  
  
## 구문  
  
```  
class AFX_NOVTABLE CObject  
```  
  
## 멤버  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CObject::CObject](../Topic/CObject::CObject.md)|기본 생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CObject::AssertValid](../Topic/CObject::AssertValid.md)|이 개체의이 무결성을 확인합니다.|  
|[CObject::Dump](../Topic/CObject::Dump.md)|이 개체에 대 한 진단 덤프를 생성합니다.|  
|[CObject::GetRuntimeClass](../Topic/CObject::GetRuntimeClass.md)|반환 된 `CRuntimeClass` 이 개체의이 클래스에 해당 하는 구조입니다.|  
|[CObject::IsKindOf](../Topic/CObject::IsKindOf.md)|이 개체의 특정된 클래스의이 관계를 테스트합니다.|  
|[CObject::IsSerializable](../Topic/CObject::IsSerializable.md)|이 개체를 serialize 할 수 있는지 테스트 합니다.|  
|[CObject::Serialize](../Topic/CObject::Serialize.md)|로드 하거나 개체\/에 아카이브를 저장 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CObject::operator delete](../Topic/CObject::operator%20delete.md)|특별 한  **삭제** 연산자.|  
|[CObject::operator new](../Topic/CObject::operator%20new.md)|특별 한  **새** 연산자.|  
  
## 설명  
 뿐만 아니라 라이브러리 클래스에 대 한 루트 같은 역할 `CFile` 및 `CObList`를 작성 하는 클래스도 있지만.  `CObject`포함 하는 기본 서비스를 제공 합니다.  
  
-   Serialization 지원  
  
-   런타임 클래스 정보  
  
-   진단 출력 개체  
  
-   컬렉션 클래스와의 호환성  
  
 이때 `CObject` 다중 상속을 지원 하지 않습니다.  파생된 클래스는 하나만 가질 수 있습니다 `CObject` 기본 클래스와 `CObject` 계층 구조에서 가장 왼쪽에 있어야 합니다.  그러나 구조 하는 것 및 비\-`CObject`\-파생 클래스가 다중 상속 지점 오른쪽에 있습니다.  
  
 주요 이점이 실현 됩니다 `CObject` 파생 클래스를 구현 하 고 선언에서 선택적 매크로의 일부를 사용 하는 경우.  
  
 첫째 수준의 매크로  [DECLARE\_DYNAMIC](../Topic/DECLARE_DYNAMIC.md) 및  [클래스](../Topic/IMPLEMENT_DYNAMIC.md), 런타임 액세스 클래스 이름 및 계층 구조에서의 위치를 허용 합니다.  따라서 의미 있는 진단 덤프 있습니다.  
  
 두 번째 수준의 매크로  [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) 및  [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md)매크로 첫 번째 레벨의 모든 기능을 포함 하 고 이들을 사용 가능 "은"보관"에서 serialize 될 개체"  
  
 일반적 mfc 및 C\+\+ 클래스를 파생 하 고 사용 하는 방법에 대 한 내용은 `CObject`를 참조 하십시오  [CObject 사용](../../mfc/using-cobject.md) 및  [직렬화](../../mfc/serialization-in-mfc.md).  
  
## 상속 계층 구조  
 `CObject`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)