---
title: "CComAutoThreadModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComAutoThreadModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "apartment model modules"
  - "CComAutoThreadModule class"
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComAutoThreadModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL 7.0 기준으로 `CComAutoThreadModule` 사용 되지 않습니다: 참조  [ATL 모듈 클래스](../../atl/atl-module-classes.md) 에 대 한 자세한 내용은.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template<  
class ThreadAllocator= CComSimpleThreadAllocator   
>  
class CComAutoThreadModule :  
public CComModule  
```  
  
#### 매개 변수  
 `ThreadAllocator`  
 \[in\] 선택 스레드를 관리 하는 클래스입니다.  기본값은  [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[CreateInstance](../Topic/CComAutoThreadModule::CreateInstance.md)|스레드를 선택 하 고 연결 된 아파트에 있는 개체를 만듭니다.|  
|[GetDefaultThreads](../Topic/CComAutoThreadModule::GetDefaultThreads.md)|\(정적\) 프로세서 수에 따라 모듈에 대 한 스레드 수를 동적으로 계산 합니다.|  
|[초기화](../Topic/CComAutoThreadModule::Init.md)|모듈의 스레드를 만듭니다.|  
|[잠금](../Topic/CComAutoThreadModule::Lock.md)|현재 스레드 및 모듈의 잠금 횟수를 늘립니다.|  
|[잠금 해제](../Topic/CComAutoThreadModule::Unlock.md)|잠금 횟수를 줄입니다 현재 스레드 및 모듈.|  
  
### 데이터 멤버  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[dwThreadID](../Topic/CComAutoThreadModule::dwThreadID.md)|현재 스레드의 식별자를 포함 합니다.|  
|[m\_Allocator](../Topic/CComAutoThreadModule::m_Allocator.md)|선택한 스레드를 관리합니다.|  
|[m\_nThreads](../Topic/CComAutoThreadModule::m_nThreads.md)|모듈에 대 한 스레드 수가 포함 됩니다.|  
|[m\_pApartments](../Topic/CComAutoThreadModule::m_pApartments.md)|모듈의 아파트를 관리합니다.|  
  
## 설명  
  
> [!NOTE]
>  이 클래스에서 교체한 것 되지는  [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 및  [CAtlModule](../../atl/reference/catlmodule-class.md) 파생 클래스입니다.  뒤에 오는 정보에 이전 버전의 ATL. 사용 됩니다.  
  
 `CComAutoThreadModule`파생 된  [CComModule](../../atl/reference/ccommodule-class.md) 아파트 모델 스레드 풀링, COM 서버 Exe 및 Windows 서비스를 구현 합니다.  `CComAutoThreadModule`사용 하 여  [CComApartment](../../atl/reference/ccomapartment-class.md) 모듈에서 각 스레드에 대 한 아파트를 관리 합니다.  
  
 파생 모듈에서 `CComAutoThreadModule` 여러 아파트에 개체를 만드는 데 사용할.  또한 포함 해야는  [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) 매크로 지정할 개체의 클래스 정의에서  [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리로.  
  
 기본적으로 ATL COM 응용 \(Visual Studio.net의 ATL 프로젝트 마법사\) 모듈에서 파생 됩니다 `CComModule`.  사용 `CComAutoThreadModule`, 클래스 정의 수정 합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/CPP/ccomautothreadmodule-class_1.cpp)]  
  
## 상속 계층 구조  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `IAtlAutoThreadModule`  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 [CComModule](../../atl/reference/ccommodule-class.md)  
  
 `CComAutoThreadModule`  
  
## 요구 사항  
 **헤더:**  atlbase.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)