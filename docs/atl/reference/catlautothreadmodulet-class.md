---
title: "CAtlAutoThreadModuleT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlAutoThreadModuleT"
  - "ATL::CAtlAutoThreadModuleT"
  - "CAtlAutoThreadModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlAutoThreadModuleT class"
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CAtlAutoThreadModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 스레드 풀링, 아파트 모델 COM 서버를 구현 하는 방법을 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template <  
class T,  
class ThreadAllocator= CComSimpleThreadAllocator,  
DWORD dwWait= INFINITE   
>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT :  
public IAtlAutoThreadModule  
```  
  
#### 매개 변수  
 `T`  
 COM 서버를 구현 하는 클래스입니다.  
  
 `ThreadAllocator`  
 선택 스레드를 관리 하는 클래스입니다.  기본값은  [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 시간 제한 간격을 밀리초 단위로 지정합니다.  기본 메서드의 시간 제한 간격 경과 전혀 의미 하는 무한입니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](../Topic/CAtlAutoThreadModuleT::GetDefaultThreads.md)|이 정적 함수는 동적으로 계산 하 고 EXE 모듈 프로세서 수에 따라 스레드의 최대 수를 반환 합니다.|  
  
## 설명  
 클래스  [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 에서 파생 된 `CAtlAutoThreadModuleT` 아파트 모델 스레드 풀링, COM 서버를 구현 하기 위해.  사용 되지 않는 클래스를 대체  [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  이 클래스는 DLL의 기본으로 사용할 수 없습니다 `dwWait` 무한 값 DLL을 언로드할 때 교착 상태가 발생할 수 있습니다.  
  
## 상속 계층 구조  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [IAtlAutoThreadModule Class](../../atl/reference/iatlautothreadmodule-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule Class](../../atl/reference/iatlautothreadmodule-class.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)