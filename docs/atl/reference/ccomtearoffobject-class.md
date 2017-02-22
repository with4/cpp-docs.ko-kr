---
title: "CComTearOffObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComTearOffObject<Base>"
  - "ATL::CComTearOffObject"
  - "ATL.CComTearOffObject"
  - "ATL.CComTearOffObject<Base>"
  - "CComTearOffObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComTearOffObject class"
  - "tear-off interfaces"
  - "tear-off interfaces, ATL"
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComTearOffObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 분리 된 인터페이스를 구현합니다.  
  
## 구문  
  
```  
  
      template<  
   class Base   
>  
class CComTearOffObject :  
   public Base  
```  
  
#### 매개 변수  
 `Base`  
 분리 된 클래스를 파생 하는에서 `CComTearOffObjectBase` 인터페이스를 지원 하 여 분리 개체 원하는.  
  
 ATL 두 단계로 분리 된 인터페이스를 구현 등의 `CComTearOffObjectBase` 메서드 핸들 참조 카운트 및 `QueryInterface`, 동안 `CComTearOffObject` 구현  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComTearOffObject::CComTearOffObject](../Topic/CComTearOffObject::CComTearOffObject.md)|생성자입니다.|  
|[CComTearOffObject::~CComTearOffObject](../Topic/CComTearOffObject::~CComTearOffObject.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComTearOffObject::AddRef](../Topic/CComTearOffObject::AddRef.md)|참조 횟수를 증가 `CComTearOffObject` 개체입니다.|  
|[CComTearOffObject::QueryInterface](../Topic/CComTearOffObject::QueryInterface.md)|분리 된 클래스 또는 소유자 클래스에서 요청한 인터페이스에 포인터를 반환합니다.|  
|[CComTearOffObject::Release](../Topic/CComTearOffObject::Release.md)|참조 횟수를 감소는 `CComTearOffObject` 및 개체를 삭제 합니다.|  
  
### CComTearOffObjectBase 메서드  
  
|||  
|-|-|  
|[CComTearOffObjectBase](../Topic/CComTearOffObject::CComTearOffObjectBase.md)|생성자입니다.|  
  
### CComTearOffObjectBase 데이터 멤버  
  
|||  
|-|-|  
|[m\_pOwner](../Topic/CComTearOffObject::m_pOwner.md)|에 대 한 포인터는 `CComObject` 소유자 클래스에서 파생 됩니다.|  
  
## 설명  
 `CComTearOffObject`만 해당 인터페이스를 쿼리할 때 인스턴스화되지는 별도 개체로 분리 한 인터페이스를 구현 합니다.  참조 횟수가 0이 되는 경우는 절취 삭제 됩니다.  일반적으로 인터페이스 사용은 절취 vtable 포인터에서 기본 개체의 모든 인스턴스 저장 하기 때문에 거의 사용 하지 않습니다에 대 한 분리 된 인터페이스를 빌드합니다.  
  
 분리형에서 구현 하는 클래스를 파생 시키는 `CComTearOffObjectBase` 에서 지원 하 여 분리 된 개체의 어떤 인터페이스 원하는.  `CComTearOffObjectBase`\(를\) 소유자 클래스와 스레드 모델을 처리할 수 있습니다.  소유자 클래스에는 절취 구현 되는 경우 개체의 클래스가입니다.  스레드 모델을 지정 하지 않으면 기본 스레드 모델이 사용 됩니다.  
  
 분리 된 클래스의 COM 맵을 만들어야 합니다.  ATL의 분리를 인스턴스화하면 만들기  **CComTearOffObject \<CYourTearOffClass\>** 또는  **CComCachedTearOffObject \<CYourTearOffClass\>**.  
  
 BEEPER 샘플의 예는 `CBeeper2` 클래스는 분리 된 클래스 및 `CBeeper` 클래스는 소유자 클래스:  
  
 [!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/CPP/ccomtearoffobject-class_1.h)]  
  
## 상속 계층 구조  
 `Base`  
  
 `CComTearOffObject`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComCachedTearOffObject Class](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)