---
title: "CComVariant Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComVariant"
  - "ATL::CComVariant"
  - "CComVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComVariant class"
  - "VARIANT macro"
  - "VARIANT macro, ATL"
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CComVariant Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 래핑하는 `VARIANT` 형식에 저장 된 데이터의 형식을 나타내는 멤버를 제공 합니다.  
  
## 구문  
  
```  
  
class CComVariant : public tagVARIANT  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComVariant::CComVariant](../Topic/CComVariant::CComVariant.md)|생성자입니다.|  
|[CComVariant::~CComVariant](../Topic/CComVariant::~CComVariant.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComVariant::Attach](../Topic/CComVariant::Attach.md)|첨부는  **변형** 에 `CComVariant` 개체입니다.|  
|[CComVariant::ChangeType](../Topic/CComVariant::ChangeType.md)|변환 된 `CComVariant` 개체를 새로운 형식.|  
|[CComVariant::Clear](../Topic/CComVariant::Clear.md)|취소는 `CComVariant` 개체입니다.|  
|[CComVariant::Copy](../Topic/CComVariant::Copy.md)|복사본을  **변형** 에 `CComVariant` 개체.|  
|[CComVariant::CopyTo](../Topic/CComVariant::CopyTo.md)|내용을 복사 하는 `CComVariant` 개체입니다.|  
|[CComVariant::Detach](../Topic/CComVariant::Detach.md)|내부 분리  **변형** 에서 `CComVariant` 개체입니다.|  
|[CComVariant::GetSize](../Topic/CComVariant::GetSize.md)|크기의 내용을 바이트 수로 반환 된 `CComVariant` 개체입니다.|  
|[CComVariant::ReadFromStream](../Topic/CComVariant::ReadFromStream.md)|로드는  **변형** 스트림에서.|  
|[CComVariant::SetByRef](../Topic/CComVariant::SetByRef.md)|초기화는 `CComVariant` 집합 및 개체의  **vt** 멤버를  **VT\_BYREF**.|  
|[CComVariant::WriteToStream](../Topic/CComVariant::WriteToStream.md)|기본 저장  **변형** 스트림을 합니다.|  
  
### Public 연산자  
  
|||  
|-|-|  
|[CComVariant::operator \<](../Topic/CComVariant::operator%20%3C.md)|표시 여부를 `CComVariant` 개체 보다 작으면 지정 된  **변형**.|  
|[CComVariant::operator \>](../Topic/CComVariant::operator%20%3E.md)|표시 여부를 `CComVariant` 개체는 지정 된 보다 큰  **변형**.|  
|[연산자\! \=](../Topic/CComVariant::operator%20!=.md)|표시 여부를 `CComVariant` 개체는 지정 된 동일 하지 않습니다  **변형**.|  
|[연산자 \=](../Topic/CComVariant::operator%20=.md)|값에 할당 된 `CComVariant` 개체입니다.|  
|[연산자 \= \=](../Topic/CComVariant::operator%20==.md)|나타냅니다 여부는 `CComVariant` 개체에 지정 된 해당  **변형**.|  
  
## 설명  
 `CComVariant`래핑하는 `VARIANT and VARIANTARG` 형식의 공용 구조체 및 공용 구조체에 저장 된 데이터의 형식을 나타내는 구성원으로 구성 됩니다.  **변형**s 자동화에서 일반적으로 사용 됩니다.  
  
 `CComVariant`파생 되는  **변형** 입력 될 수 있도록 어디에 사용 되는  **변형** 사용할 수 있습니다.  예를 들어, 사용할 수 있습니다는  **V\_VT** 형식을 추출 하는 매크로 `CComVariant` 또는 액세스할 수는  **vt** 에서처럼 직접 단지 멤버는  **변형**.  
  
## 상속 계층 구조  
 `tagVARIANT`  
  
 `CComVariant`  
  
## 요구 사항  
 **헤더:**  atlcomcli.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)