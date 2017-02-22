---
title: "CComPtrBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComPtrBase"
  - "ATL::CComPtrBase<T>"
  - "ATL.CComPtrBase<T>"
  - "ATL::CComPtrBase"
  - "CComPtrBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComPtrBase class"
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComPtrBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 COM 기반 메모리 루틴을 사용 하 여 스마트 포인터 클래스를 제공 합니다.  
  
## 구문  
  
```  
  
      template <  
   class T   
> class CComPtrBase  
```  
  
#### 매개 변수  
 `T`  
 스마트 포인터에서 참조 하는 개체 형식입니다.  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComPtrBase::~CComPtrBase](../Topic/CComPtrBase::~CComPtrBase.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md)|간의 연결을 만들려면이 메서드를 호출 하는 `CComPtrBase`의 연결 지점 및 클라이언트의 싱크입니다.|  
|[CComPtrBase::Attach](../Topic/CComPtrBase::Attach.md)|기존 포인터의 소유권을 가져오려면이 메서드를 호출 합니다.|  
|[CComPtrBase::CoCreateInstance](../Topic/CComPtrBase::CoCreateInstance.md)|이 메서드는 지정 된 클래스 ID 또는 프로그램 id가 연결 된 클래스의 개체를 만들 수|  
|[CComPtrBase::CopyTo](../Topic/CComPtrBase::CopyTo.md)|복사 하려면이 메서드를 호출 하는 `CComPtrBase` 다른 포인터 변수에 대 한 포인터입니다.|  
|[CComPtrBase::Detach](../Topic/CComPtrBase::Detach.md)|소유권에 대 한 포인터를 해제 하려면이 메서드를 호출 합니다.|  
|[CComPtrBase::IsEqualObject](../Topic/CComPtrBase::IsEqualObject.md)|경우 확인 하려면이 메서드를 호출 하는 지정 된  **IUnknown** 관련 동일한 개체를 가리키는 `CComPtrBase` 개체.|  
|[CComPtrBase::QueryInterface](../Topic/CComPtrBase::QueryInterface.md)|지정한 인터페이스에 포인터를 반환 하도록이 메서드를 호출 합니다.|  
|[CComPtrBase::Release](../Topic/CComPtrBase::Release.md)|인터페이스를 해제 하려면이 메서드를 호출 합니다.|  
|[CComPtrBase::SetSite](../Topic/CComPtrBase::SetSite.md)|사이트를 설정 하려면이 메서드를 호출 하 여 `CComPtrBase` 개체의  **IUnknown** 부모 개체의.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CComPtrBase::operator T\*](../Topic/CComPtrBase::operator%20T*.md)|캐스트 연산자입니다.|  
|[CComPtrBase::operator \!](../Topic/CComPtrBase::operator%20!.md)|NOT 연산자.|  
|[CComPtrBase::operator &](../Topic/CComPtrBase::operator%20&.md)|& 연산자.|  
|[CComPtrBase::operator \*](../Topic/CComPtrBase::operator%20*.md)|\* 연산자.|  
|[CComPtrBase::operator \<](../Topic/CComPtrBase::operator%20%3C.md)|보다\-작음 연산자입니다.|  
|[CComPtrBase::operator \=\=](../Topic/CComPtrBase::operator%20==.md)|같음 연산자입니다.|  
|[CComPtrBase::operator \-\>](../Topic/CComPtrBase::operator%20-%3E.md)|포인터\-멤버 연산자입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CComPtrBase::p](../Topic/CComPtrBase::p.md)|포인터 데이터 멤버 변수입니다.|  
  
## 설명  
 이 클래스는 COM 메모리 관리 루틴을 사용 하는 다른 스마트 포인터에 대 한 기초가  [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 및  [CComPtr](../../atl/reference/ccomptr-class.md).  파생된 클래스는 자신의 생성자와 연산자를 추가 하지만에서 제공 하는 방법에 의존 `CComPtrBase`.  
  
## 요구 사항  
 **헤더:** atlcomcli.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)