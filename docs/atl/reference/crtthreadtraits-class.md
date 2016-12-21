---
title: "CRTThreadTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CRTThreadTraits"
  - "ATL.CRTThreadTraits"
  - "CRTThreadTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRTThreadTraits class"
  - "스레딩[ATL], creation functions"
  - "스레딩[ATL], CRT threads"
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRTThreadTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 생성 함수는 CRT 스레드를 제공합니다.  스레드 CRT 함수를 사용 하려는 경우이 클래스를 사용 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CRTThreadTraits  
  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRTThreadTraits::CreateThread](../Topic/CRTThreadTraits::CreateThread.md)|\(정적\) CRT 함수를 사용 하는 스레드를 만들려면이 함수를 호출 합니다.|  
  
## 설명  
 스레드 특성은 특정 유형의 스레드를 생성 하는 함수를 제공 하는 클래스입니다.  생성 함수를 Windows로 서명과 의미 있는  [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) 함수입니다.  
  
 스레드 특성은 다음 클래스에서 사용 됩니다.  
  
-   [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
-   [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 사용 하는 스레드 CRT 함수를 사용 하지 않는 경우  [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) 대신 합니다.  
  
## 요구 사항  
 **헤더:** atlbase.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)