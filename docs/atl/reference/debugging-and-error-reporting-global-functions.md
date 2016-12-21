---
title: "Debugging and Error Reporting Global Functions | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "함수[ATL], 오류 보고"
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Debugging and Error Reporting Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 기능은 유용한 디버깅 및 추적 기능을 제공합니다.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](../Topic/AtlHresultFromLastError.md)|반환 된 `GetLastError` 오류 코드는 HRESULT 형식의.|  
|[AtlHresultFromWin32](../Topic/AtlHresultFromWin32.md)|Win32 오류 코드 HRESULT로 변환합니다.|  
|[AtlReportError](../Topic/AtlReportError.md)|설정  **IErrorInfo** 클라이언트에 오류 정보를 제공 합니다.|  
|[AtlThrow](../Topic/AtlThrow.md)|`CAtlException`을 throw합니다.|  
|[AtlThrowLastWin32](../Topic/AtlThrowLastWin32.md)|Windows 함수의 결과에 따라 오류를 알리기 위해이 함수를 호출 합니다. `GetLastError`.|  
|[AtlTraceLoadSettings](../../misc/atltraceloadsettings.md)|추적 설정 파일을 로드 하려면이 함수를 호출 합니다.|  
|[AtlTraceSaveSettings](../../misc/atltracesavesettings.md)|현재 추적 설정을 파일에 저장 하려면이 함수를 호출 합니다.|  
  
## 참고 항목  
 [함수](../../atl/reference/atl-functions.md)   
 [Debugging and Error Reporting Macros](../../atl/reference/debugging-and-error-reporting-macros.md)