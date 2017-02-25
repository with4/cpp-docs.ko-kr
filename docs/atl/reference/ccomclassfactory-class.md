---
title: "CComClassFactory Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComClassFactory"
  - "CComClassFactory"
  - "ATL::CComClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactory class"
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComClassFactory Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에서 구현 된  [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) 인터페이스.  
  
## 구문  
  
```  
  
   class CComClassFactory : public IClassFactory,   
public CComObjectRootEx< CComGlobalsThreadModel >  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComClassFactory::CreateInstance](../Topic/CComClassFactory::CreateInstance.md)|지정한 CLSID의 개체를 만듭니다.|  
|[CComClassFactory::LockServer](../Topic/CComClassFactory::LockServer.md)|메모리에서 클래스 팩터리를 잠급니다.|  
  
## 설명  
 `CComClassFactory`구현 된  [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) 클래스 팩터리 새 개체를 더 빨리 만들 수 있도록 메모리에서 잠금 뿐만 아니라 개체의 특정 CLSID 만들기 위한 메서드를 포함 하는 인터페이스입니다.  **IClassFactory** 하는 CLSID를 할당 하 고 시스템 레지스트리를 등록 하는 모든 클래스를 구현 해야 합니다.  
  
 ATL 개체 정상적으로 취득 팩터리 클래스에서 파생 하 여  [CComCoClass](../../atl/reference/ccomcoclass-class.md).  이 클래스는 매크로 포함  [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)는 선언 `CComClassFactory` 기본 클래스 팩터리로.  이 기본값을 재정의 하려면 중 하나를 지정 된 `DECLARE_CLASSFACTORY`*XXX* 매크로 클래스 정의에.  예를 들어 있는  [DECLARE\_CLASSFACTORY\_EX](../Topic/DECLARE_CLASSFACTORY_EX.md) 매크로 대 한 클래스 팩터리 사용 하 여 지정 된 클래스:  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/CPP/ccomclassfactory-class_1.h)]  
  
 위의 클래스 정의 지정  **CMyClassFactory** 개체의 기본 클래스 팩터리로 사용 됩니다.  **CMyClassFactory** 에서 파생 되어야 `CComClassFactory` 및 재정의 `CreateInstance`.  
  
 ATL 클래스 팩터리를 선언 하는 다른 세 가지 매크로 제공 합니다.  
  
-   [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) 를 사용 하 여  [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), 만들기를 통해 라이센스를 제어 합니다.  
  
-   [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) 를 사용 하 여  [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), 여러 아파트에서 개체가 만들어집니다.  
  
-   [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md) 를 사용 하 여  [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), 하나를 생성 하는  [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 개체입니다.  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)