---
title: "fwrite | Microsoft Docs"
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
  - "fwrite"
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
  - "fwrite"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fwrite 함수"
  - "스트림, 데이터 쓰기"
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fwrite
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에 데이터를 씁니다.  
  
## 구문  
  
```  
size_t fwrite(    const void *buffer,    size_t size,    size_t count,    FILE *stream  );  
```  
  
#### 매개 변수  
 `buffer`  
 쓸 데이터에 대한 포인터입니다.  
  
 `size`  
 항목 크기입니다\(바이트\).  
  
 `count`  
 쓸 항목의 최대 수입니다.  
  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 `fwrite`는 정확하게 쓴 전체 항목의 수를 반환합니다. 오류가 발생하는 경우 이 수는 `count`보다 작을 수 있습니다.  또한 오류가 발생하면 파일 위치 표시기를 확인할 수 없습니다.  `stream` 또는 `buffer`가 null 포인터인 경우 또는 유니코드 모드에 홀수 바이트를 쓰도록 지정한 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에서 설명된 대로 이 함수가 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL` 로 설정하고 0을 반환합니다.  
  
## 설명  
 `fwrite` 함수는 `buffer`에서 출력 `stream`으로 최대 `count`개 항목\(각 길이: `size`\)을 씁니다.  `stream`\(한 개가 있는 경우\)과 연결된 파일 포인터는 실제로 기록된 바이트 수 만큼 증분됩니다.  `stream`이 텍스트 모드에서 열리면 각 줄 바꿈은 캐리지 리턴 \- 줄 바꿈 쌍으로 바뀝니다.  이렇게 바뀌더라도 반환 값에는 영향을 미치지 않습니다.  
  
 `stream`이 유니코드 변환 모드에서 열리는 경우\(예: `fopen`을 호출하고 `ccs=UNICODE`, `ccs=UTF-16LE` 또는 `ccs=UTF-8`이 포함된 모드 매개 변수를 사용하여 `stream`을 여는 경우나 `_setmode`와 `_O_WTEXT`, `_O_U16TEXT` 또는 `_O_U8TEXT`가 포함된 모드 매개 변수를 사용하여 모드를 유니코드 변환 모드로 변경한 경우\) `buffer`는 UTF\-16 데이터가 포함된 `wchar_t`의 배열에 대한 포인터로 해석됩니다.  이 모드에서 홀수 바이트를 쓰려고 하면 매개 변수 유효성 검사 오류가 발생합니다.  
  
 이 함수는 호출 스레드를 잠그기 때문에 스레드로부터 안전하게 보호됩니다.  잠기지 않는 버전의 경우 `_fwrite_nolock`을 참조하세요.  
  
## 요구 사항  
  
|함수|필수 헤더|  
|--------|-----------|  
|`fwrite`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
 [fread](../../c-runtime-library/reference/fread.md)의 예제를 참조하세요.  
  
## 해당 .NET Framework 항목  
 [System::IO::FileStream::Write](https://msdn.microsoft.com/en-us/library/system.io.filestream.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [\_fwrite\_nolock](../../c-runtime-library/reference/fwrite-nolock.md)   
 [\_write](../../c-runtime-library/reference/write.md)