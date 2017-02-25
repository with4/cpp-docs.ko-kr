---
title: "CDebugReportHook Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CDebugReportHook"
  - "CDebugReportHook"
  - "ATL::CDebugReportHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDebugReportHook class"
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDebugReportHook Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스를 사용 하 여 디버그 보고서를 보내려면 명명 된 파이프에.  
  
## 구문  
  
```  
  
class CDebugReportHook  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDebugReportHook::CDebugReportHook](../Topic/CDebugReportHook::CDebugReportHook.md)|호출  [SetPipeName](../Topic/CDebugReportHook::SetPipeName.md),  [SetTimeout](../Topic/CDebugReportHook::SetTimeout.md), 및  [SetHook](../Topic/CDebugReportHook::SetHook.md).|  
|[CDebugReportHook::~CDebugReportHook](../Topic/CDebugReportHook::~CDebugReportHook.md)|호출  [CDebugReportHook::RemoveHook](../Topic/CDebugReportHook::RemoveHook.md).|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDebugReportHook::CDebugReportHookProc](../Topic/CDebugReportHook::CDebugReportHookProc.md)|\(정적\) 사용자 지정 보고 함수는 C 런타임에 연결 보고 프로세스를 디버깅 합니다.|  
|[CDebugReportHook::RemoveHook](../Topic/CDebugReportHook::RemoveHook.md)|명명 된 파이프에 디버그 보고서를 보내지 않도록 하려면이 메서드를 호출 하 고 보고서 후크 이전 복원 합니다.|  
|[CDebugReportHook::SetHook](../Topic/CDebugReportHook::SetHook.md)|명명 된 파이프에 디버그 보고서를 보내기 시작 하는이 메서드를 호출 합니다.|  
|[CDebugReportHook::SetPipeName](../Topic/CDebugReportHook::SetPipeName.md)|디버그 보고서를 보내야 하는 파이프 이름과 컴퓨터를 설정 하려면이 메서드를 호출 합니다.|  
|[CDebugReportHook::SetTimeout](../Topic/CDebugReportHook::SetTimeout.md)|이 클래스는 명명 된 파이프를 사용할 수 있게 대기 시간을 밀리초 단위로 시간을 설정 하려면이 메서드를 호출 합니다.|  
  
## 설명  
 디버그 빌드에서 디버그 보고서를 보내려면 명명 된 파이프에 응용 프로그램 또는 서비스에서이 클래스의 인스턴스를 만듭니다.  디버그 보고서 생성 호출 하 여  [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 또는 래퍼 같이이 함수를 사용 하 여  [ATLTRACE](../Topic/ATLTRACE%20\(ATL\).md) 및  [ATLASSERT](../Topic/ATLASSERT.md) 매크로.  
  
 이 클래스를 사용 하면 대화형으로 비 대화형으로 실행 구성 요소를 디버깅 하려면  [윈도우 스테이션](http://msdn.microsoft.com/library/windows/desktop/ms687096).  
  
 Note 스레드의 기본 보안 컨텍스트를 사용 하 여 디버그 보고서가 전송 됩니다.  가장 위치 가장 낮은 권한의 사용자를 같은 웹 응용 프로그램에서 수행 되는 경우에서 디버그 보고서를 볼 수 있도록 일시적으로 사용할 수 없습니다.  
  
## 요구 사항  
 **헤더:** atlutil.h  
  
## 참고 항목  
 [클래스](../../atl/reference/atl-classes.md)