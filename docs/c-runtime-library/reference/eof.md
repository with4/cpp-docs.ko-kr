---
title: "_eof | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_eof"
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
  - "_eof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_eof 함수"
  - "파일의 끝"
  - "파일의 끝, 테스트"
  - "eof 함수"
  - "파일[C++], 끝"
  - "테스트, 파일의 끝"
ms.assetid: 265703f4-d07e-4005-abf3-b1d0cdd9e0b0
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _eof
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일의 끝\(EOF\)을 테스트 합니다.  
  
## 구문  
  
```  
int _eof(   
   int fd   
);  
```  
  
#### 매개 변수  
 `fd`  
 열려 있는 파일을 나타내는 파일 기술자입니다.  
  
## 반환 값  
 `_eof` 는 현재 위치가 파일의 끝인 경우 \`을 반환하고 그렇지 않은 경우 0을 반환합니다.  반환 값 \-1 은 오류를 나타냅니다. 이 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 잘못된 매개 변수 처리기가 호출 됩니다.  실행이 계속해서 허용 되는 경우 `errno` 는잘못된 파일 설명자를 나타내는 `EBADF` 로 설정됩니다.  
  
## 설명  
 `_eof` 함수는 `fd` 와 관련된 파일의 끝에 도달 했는지 여부를 결정합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|선택적 헤더|  
|--------------|-----------|------------|  
|`_eof`|\<io.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## Input: crt\_eof.txt  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### Output  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [오류 처리](../../c-runtime-library/error-handling-crt.md)   
 [하위 수준 I\/O](../../c-runtime-library/low-level-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)