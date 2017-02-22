---
title: "디렉터리 제어 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨트롤[C++], 디렉터리"
  - "디렉터리 제어 루틴"
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 디렉터리 제어
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이러한 루틴들은 디렉터리 구조체에 대한 정보를 얻고, 수정 및 액세스를 합니다.  
  
### 디렉터리 제어 루틴  
  
|루틴|기능|해당 .NET Framework|  
|--------|--------|-----------------------|  
|[\_chdir, \_wchdir](../c-runtime-library/reference/chdir-wchdir.md)|현재 작업 디렉터리를 변경합니다.|[\<caps:sentence id\="tgt8" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_chdrive](../c-runtime-library/reference/chdrive.md)|현재 드라이브를 변경합니다.|[\<caps:sentence id\="tgt11" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getcwd, \_wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|기본 드라이브에 대한 현재 작업 디렉터리를 가져옵니다.|[\<caps:sentence id\="tgt14" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdcwd, \_wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|지정된 드라이브에 대한 현재 작업 디렉터리를 가져옵니다.|[\<caps:sentence id\="tgt16" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|디스크 드라이브에 관한 정보를 사용하여 `_diskfree_t` 구조체를 만듭니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_getdrive](../c-runtime-library/reference/getdrive.md)|현재 \(기본\) 드라이브를 가져옵니다.|[\<caps:sentence id\="tgt23" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdrives](../c-runtime-library/reference/getdrives.md)|현재 사용할 수 있는 디스크 드라이브를 나타내는 비트 마스크를 반환합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_mkdir, \_wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|새 디렉터리 만들기|[System::IO::Directory::CreateDirectory](https://msdn.microsoft.com/en-us/library/system.io.directory.createdirectory.aspx),  [System::IO::DirectoryInfo::CreateSubdirectory](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.createsubdirectory.aspx)|  
|[\_rmdir, \_wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|디렉터리를 제거합니다.|[\<caps:sentence id\="tgt32" sentenceid\="de5c5e84e86fdd3cd99296d3b2518f57" class\="tgtSentence"\>System::IO::Directory::Delete\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)|  
|[\_searchenv, \_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [\_searchenv\_s, \_wsearchenv\_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|지정된 경로에서 주어진 파일을 검색합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)   
 [파일 처리](../c-runtime-library/file-handling.md)   
 [시스템 호출](../c-runtime-library/system-calls.md)