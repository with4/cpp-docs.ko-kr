---
title: "_open_osfhandle | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_open_osfhandle"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_open_osfhandle"
  - "open_osfhandle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "open_osfhandle 함수"
  - "파일 핸들[C++], 연결"
  - "_open_osfhandle 함수"
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _open_osfhandle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기존 운영 체제 파일 핸들을 사용하는 C 런타임 파일 기술자 연합  
  
## 구문  
  
```  
  
      int _open_osfhandle (  
   intptr_t osfhandle,  
   int flags   
);  
```  
  
#### 매개 변수  
 `osfhandle`  
 운영 체제 파일 핸들입니다.  
  
 `flags`  
 허용 된 작업의 유형입니다.  
  
## 반환 값  
 성공 하면, `_open_osfhandle` 는 C 런타임 파일 설명자를 반환 합니다.  그렇지 않으면 \-1이 반환됩니다.  
  
## 설명  
 `_open_osfhandle`  함수는 C 런타임 파일 설명자를 할당 하고  `osfhandle`  가 지정하는 운영 체제 파일 핸들을 사용하여 연걸합니다.  `flags` 인수는 Fcntl.h에 정의 된 매니페스트 상수 중 하나 이상에서 형성 하는 정수 식입니다.  둘 이상의 매니페스트 상수가 `flags` 인자를 형성하기 위해 사용될 때, 상수는 비트 단위 OR 연산자 \( 와 결합합니다.  **&#124;** \).  
  
 Fcntl.h 은 다음 매니페스트 상수를 정의합니다.  
  
 **\_O\_APPEND**  
 매번 쓰기 작업을 하기 전에 파일의 끝에 파일 포인터를 설정합니다.  
  
 **\_O\_RDONLY**  
 파일을 읽기 전용으로 엽니다.  
  
 **\_O\_TEXT**  
 텍스트\(변환됨\) 모드에서 파일을 엽니다.  
  
 **\_O\_WTEXT**  
 Unicode \(UTF\-16 으로 변환됨\) 모드에서 파일을 엽니다.  
  
 `_open_osfhandle` 을 사용하여 열린 파일을 닫으려면 `_close` 을 호출하십시오.  기본 핸들도 `_close` 에 대한 호출로 닫힙니다. 따라서 원래 핸들에 대해 Win32 함수 `CloseHandle` 를 호출할 필요가 없습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_open_osfhandle`|\<io.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)