---
title: "_CrtSetReportFile | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportFile"
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
apitype: "DLLExport"
f1_keywords: 
  - "CrtSetReportFile"
  - "_CrtSetReportFile"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtSetReportFile 함수"
  - "_CrtSetReportFile 함수"
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtSetReportFile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 는 `_CRTDBG_MODE_FILE` 를 지정하려고 사용한 후, 텍스트 메시지를 수신하여 파일 핸들을 지정할 수 있습니다.  `_CrtSetReportFile` 는 [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) 에 의해텍스트 \(디버그 버전에만 해당\)의 대상을 지정할 수 있는데 사용되곤 합니다.  
  
## 구문  
  
```  
_HFILE _CrtSetReportFile(   
   int reportType,  
   _HFILE reportFile   
);  
```  
  
#### 매개 변수  
 `reportType`  
 보고서 형식: `_CRT_WARN`, `_CRT_ERROR`, 및 `_CRT_ASSERT`.  
  
 `reportFile`  
 `reportType`에 대한 새 보고서 파일  
  
## 반환 값  
 성공적으로 완료되면, `_CrtSetReportFile` 는 `reportType`로 지정된 보고서 형식에 대해 전 보고서 파일을 반환합니다.  잘못 된 값 전달 된 경우 `reportType` 를 이 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md).  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `_CRTDBG_HFILE_ERROR` 을 반환합니다.  자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_CrtSetReportFile` 와 함께 사용 되는 [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) 대상 또는 대상에 의해 생성 된 보고서를 특정 형식에 대해 정의 하는 함수 `_CrtDbgReport`입니다.  `_CrtSetReportMode` 는 특정 보고서형식에 대한 모드를 보고하는 `_CRTDBG_MODE_FILE` 를 호출할 경우, `_CrtSetReportFile` 는 특정 파일 또는 대상으로 사용 하는 스트림을 정의 호출합니다.  이러한 [\_DEBUG](../../c-runtime-library/debug.md) 가 정의되어 있지 않으면 프로세싱중에 `_CrtSetReportFile` 에 대한 호출을 제거 됩니다.  
  
 다음 표에서 사용 가능한 선택 목록이 `reportFile` 의 동작 결과 `_CrtDbgReport`입니다.  이러한 옵션은 비트 플래그로 Crtdbg.h에 정의됩니다.  
  
 `file handle`  
 대상 메시지를 파일에 대한 핸들입니다.  핸들의 유효성을 확인 하는 시도 되지 않았습니다.  연 파일 핸들을 닫습니다.  예를 들면 다음과 같습니다.  
  
```  
HANDLE hLogFile;  
hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,   
   FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,   
   FILE_ATTRIBUTE_NORMAL, NULL);  
_CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_WARN, hLogFile);  
  
_RPT0(_CRT_WARN,"file message\n");  
CloseHandle(hLogFile);  
```  
  
 `_CRTDBG_FILE_STDERR`  
 쓰기 메시지를 `stderr` 에 다음과 같은 리디렉션할 수 있습니다.  
  
```  
freopen( "c:\\log2.txt", "w", stderr);  
_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);  
  
_RPT0(_CRT_ERROR,"1st message\n");  
```  
  
 `_CRTDBG_FILE_STDOUT`  
 메시지를 쓰는 `stdout`를 리디렉션할 수 있습니다.  
  
 `_CRTDBG_REPORT_FILE`  
 현재 선택 모드를 반환합니다.  
  
 각 보고서 유형에 사용되는 보고서 파일을 개별적으로 제어할 수 있습니다.  등을 지정할 수는 한 `reportType` 의 `_CRT_ERROR` 에 보고 `stderr`, 동안에 `reportType` 의 `_CRT_ASSERT` 사용자 정의 파일 핸들 또는 스트림을 보고합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_CrtSetReportFile`|\<crtdbg.h\>|\<\<errno.h\>\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
 **라이브러리:** [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)