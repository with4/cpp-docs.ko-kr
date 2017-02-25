---
title: "CRuntimeClass Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRuntimeClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRuntimeClass structure"
  - "dynamic class information"
  - "run-time class, CRuntimeClass structure"
  - "런타임, class information"
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CRuntimeClass Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

각 클래스에서 파생 된 `CObject` 와 관련 된는 `CRuntimeClass` 구조는 런타임 시 개체 또는 해당 기본 클래스에 대 한 정보를 얻을 수 있습니다.  
  
## 구문  
  
```  
struct CRuntimeClass  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRuntimeClass::CreateObject](../Topic/CRuntimeClass::CreateObject.md)|런타임에 개체를 만듭니다.|  
|[CRuntimeClass::FromName](../Topic/CRuntimeClass::FromName.md)|익숙한 클래스 이름을 사용 하 여 런타임에 개체를 만듭니다.|  
|[CRuntimeClass::IsDerivedFrom](../Topic/CRuntimeClass::IsDerivedFrom.md)|지정 된 클래스에서 클래스가 파생 된 경우 결정 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CRuntimeClass::m\_lpszClassName](../Topic/CRuntimeClass::m_lpszClassName.md)|클래스의 이름입니다.|  
|[CRuntimeClass::m\_nObjectSize](../Topic/CRuntimeClass::m_nObjectSize.md)|바이트로 표기한 개체 크기|  
|[CRuntimeClass::m\_pBaseClass](../Topic/CRuntimeClass::m_pBaseClass.md)|에 대 한 포인터는 `CRuntimeClass` 구조체의 기본 클래스입니다.|  
|[CRuntimeClass::m\_pfnCreateObject](../Topic/CRuntimeClass::m_pfnCreateObject.md)|동적으로 개체를 만드는 함수 포인터입니다.|  
|[CRuntimeClass::m\_pfnGetBaseClass](../Topic/CRuntimeClass::m_pfnGetBaseClass.md)|반환 된 `CRuntimeClass` 구조를 사용할 때 동적으로 \(연결에\).|  
|[CRuntimeClass::m\_wSchema](../Topic/CRuntimeClass::m_wSchema.md)|스키마 클래스 개수입니다.|  
  
## 설명  
 `CRuntimeClass`구조 이며 따라서 기본 클래스에 없습니다.  
  
 런타임에 개체의 클래스를 결정 하는 기능 검사 함수 인수의 추가 형식 필요 하거나 개체의 클래스를 기반으로 하는 특수 코드를 작성 해야 할 때 유용 합니다.  런타임 클래스 정보는 C\+\+ 언어에서 직접 지원 되지 않습니다.  
  
 `CRuntimeClass`C\+\+ 관련 개체에 대 한 포인터와 같은 정보를 제공 된 `CRuntimeClass` 기본 클래스 및 관련된 클래스의 클래스 이름을 ASCII.  또한이 구조는 친숙 한 이름을 사용 하 고 관련된 클래스는 특정 클래스에서 파생 된 경우 확인 하 여 개체의 형식을 지정 하는 개체를 동적으로 만드는 데 사용할 수 있는 다양 한 기능을 구현 합니다.  
  
 사용에 대 한 자세한 내용은 `CRuntimeClass`, 문서를 참조 하십시오.  [런타임 클래스 정보 액세스](../../mfc/accessing-run-time-class-information.md).  
  
## 상속 계층 구조  
 `CRuntimeClass`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CObject::GetRuntimeClass](../Topic/CObject::GetRuntimeClass.md)   
 [CObject::IsKindOf](../Topic/CObject::IsKindOf.md)   
 [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md)   
 [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md)   
 [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md)   
 [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md)