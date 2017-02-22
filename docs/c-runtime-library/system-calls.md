---
title: "시스템 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.system"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "시스템 호출"
  - "Windows[C++], 시스템 호출"
ms.assetid: 0255f2ec-a5a0-487e-8b09-9dad001d81ed
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 시스템 호출
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 기능은 Windows 운영 체제를 호출 합니다.  
  
### 시스템 호출 함수  
  
|Function|기능|해당 .NET Framework|  
|--------------|--------|-----------------------|  
|[\_findclose](../c-runtime-library/reference/findclose.md)|이전 찾기 작업에서 리소스 해제|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_findfirst, \_findfirst32, \_findfirst64, \_findfirsti64, \_findfirst32i64, \_findfirst64i32, \_wfindfirst, \_wfindfirst32, \_wfindfirst64, \_wfindfirsti64, \_wfindfirst32i64, \_wfindfirst64i32](../c-runtime-library/reference/findfirst-functions.md)|지정 된 특성을 사용 하여 파일 찾기|[\<caps:sentence id\="tgt12" sentenceid\="e22cfa910fbeac637b6aba4ed3f9dc48" class\="tgtSentence"\>System::IO::Directory::GetFiles\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.getfiles.aspx)|  
|[\_findnext, \_findnext32, \_findnext64, \_findnexti64, \_findnext32i64, \_findnext64i32, \_wfindnext, \_wfindnext32, \_wfindnexti64, \_wfindnext64, \_wfindnexti64](../c-runtime-library/reference/findnext-functions.md)|지정 된 특성을 사용 하여 다음 파일 찾기|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)   
 [파일 처리](../c-runtime-library/file-handling.md)   
 [디렉터리 제어](../c-runtime-library/directory-control.md)   
 [하위 수준 I\/O](../c-runtime-library/low-level-i-o.md)