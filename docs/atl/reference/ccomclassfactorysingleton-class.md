---
title: "CComClassFactorySingleton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComClassFactorySingleton"
  - "ATL.CComClassFactorySingleton<T>"
  - "ATL::CComClassFactorySingleton"
  - "ATL::CComClassFactorySingleton<T>"
  - "CComClassFactorySingleton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactorySingleton class"
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComClassFactorySingleton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에서 파생 되  [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 사용 하 여  [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 는 단일 개체를 생성 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template<  
class T  
>  
class CComClassFactorySingleton :  
public CComClassFactory  
```  
  
#### 매개 변수  
 `T`  
 클래스입니다.  
  
 `CComClassFactorySingleton`파생  [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 사용 하 여  [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 는 단일 개체를 생성 합니다.  각 호출에는 `CreateInstance` 메서드는이 개체에 대 한 인터페이스 포인터를 간단 하 게 쿼리 합니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComClassFactorySingleton::CreateInstance](../Topic/CComClassFactorySingleton::CreateInstance.md)|쿼리 `m_spObj` 에 대 한 인터페이스 포인터입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CComClassFactorySingleton::m\_spObj](../Topic/CComClassFactorySingleton::m_spObj.md)|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 개체에서 생성 된 `CComClassFactorySingleton`.|  
  
## 설명  
 ATL 개체 정상적으로 취득 팩터리 클래스에서 파생 하 여  [CComCoClass](../../atl/reference/ccomcoclass-class.md).  이 클래스는 매크로 포함  [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)는 선언 `CComClassFactory` 기본 클래스 팩터리로.  사용할 `CComClassFactorySingleton`, 지정 된  [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md) 매크로 개체의 클래스 정의에.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/CPP/ccomclassfactorysingleton-class_1.h)]  
  
## 상속 계층 구조  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)  
  
 `CComClassFactorySingleton`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 Class](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactoryAutoThread Class](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)