---
title: "CComClassFactoryAutoThread Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComClassFactoryAutoThread"
  - "ATL.CComClassFactoryAutoThread"
  - "CComClassFactoryAutoThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactoryAutoThread class"
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComClassFactoryAutoThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에서 구현 된  [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) 인터페이스, 및 여러 아파트에서 만들 수 있습니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      class CComClassFactoryAutoThread : public IClassFactory,   
public CComObjectRootEx< CComGlobalsThreadModel >  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComClassFactoryAutoThread::CreateInstance](../Topic/CComClassFactoryAutoThread::CreateInstance.md)|지정한 CLSID의 개체를 만듭니다.|  
|[CComClassFactoryAutoThread::LockServer](../Topic/CComClassFactoryAutoThread::LockServer.md)|메모리에서 클래스 팩터리를 잠급니다.|  
  
## 설명  
 `CComClassFactoryAutoThread`유사한  [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), 하지만 여러 아파트에서 만들 수 있습니다.  이 지원을 활용 하 여 EXE 모듈에서 파생  [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 ATL 개체 정상적으로 취득 팩터리 클래스에서 파생 하 여  [CComCoClass](../../atl/reference/ccomcoclass-class.md).  이 클래스는 매크로 포함  [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)는 선언  [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로.  사용할 `CComClassFactoryAutoThread`, 지정 된  [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) 매크로 개체의 클래스 정의에.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/CPP/ccomclassfactoryautothread-class_1.h)]  
  
## 상속 계층 구조  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 Class](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactorySingleton Class](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)