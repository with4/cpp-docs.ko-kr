---
title: "_unlock_file | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_unlock_file"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_unlock_file"
  - "unlock_file"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_unlock_file 함수"
  - "파일[C++], 잠금 해제"
  - "unlock_file 함수"
  - "파일 잠금 해제"
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# _unlock_file
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다른 프로세스가 파일을 액세스할 수 있도록 잠금을 해제합니다.  
  
## 구문  
  
```  
void _unlock_file(  
   FILE* file  
);  
```  
  
#### 매개 변수  
 `file`  
 파일 처리기입니다.  
  
## 설명  
 `_unlock_file` 함수에는 `file`에 의해 지정된 파일의 잠금을 해제합니다.  다른 프로세스가 파일을 액세스할 수 있도록 잠금을 해제합니다.  함수는 `_lock_file` 이 `file` 포인터에서 이전에 호출되지 않았다면, 호출되어질 수 없습니다.  보호되지 않은 파일에서 `_unlock_file` 호출은 교착상태를 발생시킬 수 있습니다.  예제를 보려면 [\_lock\_file](../../c-runtime-library/reference/lock-file.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_unlock_file`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_lock\_file](../../c-runtime-library/reference/lock-file.md)