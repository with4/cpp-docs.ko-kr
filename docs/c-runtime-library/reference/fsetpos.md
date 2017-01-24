---
title: "fsetpos | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fsetpos"
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
  - "fsetpos"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fsetpos 함수"
  - "스트림, 위치 표시기 설정"
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fsetpos
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림 위치 표시기를 설정합니다.  
  
## 구문  
  
```  
int fsetpos(   
   FILE *stream,  
   const fpos_t *pos   
);  
```  
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
 `pos`  
 저장소 위치 표시기입니다.  
  
## 반환 값  
 성공하면 `fsetpos`는 0을 반환합니다.  오류시, 함수는 0이 아닌 값을 반환하고 `errno`를 다음 매니페스트 상수\(ERRNO.H에 정의된\) 중 하나로 설정합니다. `EBADF`, 즉 파일이 액세스 가능하지 않거나 `stream`이 가리키는 개체가 올바른 파일 구조체가 아닌 것을 의미하거나 `EINVAL`, 즉 `stream`의 값이 잘못되었거나 `pos`가 전달된 것을 의미합니다.  만일 잘못된 매개변수가 전달된 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 나타난 것처럼 이 함수는 잘못된 매개변수 처리기를 호출합니다.  
  
 이러한 반환 코드와 다른 반환코드에 대한 자세한 정보는 [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 를 참조하십시오.  
  
## 설명  
 `fsetpos` 함수는 `stream`의 파일위치 표시기를*,* `stream`을 향한 `fgetpos`의 호출에 앞에 얻어지는 `pos`의 값으로 설정합니다*.* 이 함수는 파일 끝 표시기를 지우고 `stream`에서 [ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md)의 모든 효과를 취소합니다*.* `fsetpos`를 호출한 이후에는, `stream`에서의 다음 작업은 입력 또는 출력이 될 수 있습니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fsetpos`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)의 예제를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)