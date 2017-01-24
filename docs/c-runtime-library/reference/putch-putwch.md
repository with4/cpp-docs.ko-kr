---
title: "_putch, _putwch | Microsoft Docs"
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
  - "_putwch"
  - "_putch"
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
  - "api-ms-win-crt-conio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_putch"
  - "putwch"
  - "_putwch"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_putch 함수"
  - "_putwch 함수"
  - "문자, 작성"
  - "콘솔, 문자 쓰기"
  - "putch 함수"
  - "putwch 함수"
ms.assetid: 3babc7cf-e333-405d-8449-c788d61d51aa
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _putch, _putwch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자를 문자열에 씁니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
  
      int _putch(  
int c   
);  
wint_t _putwch(  
   wchar_t c  
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 문자입니다.  
  
## 반환 값  
 성공하면 `c`를 반환합니다.  `_putch` 가 실패할 경우, `EOF` 를 반환합니다 ; **\_putwch** 가 실패할 경우, **WEOF** 를 반환합니다.  
  
## 설명  
 이러한 함수는 문자 `c` 를 콘솔에 버퍼링 하지 않고직접 씁니다.  Windows NT **\_putwch** 는 현재 콘솔 로케일 설정을 사용한 유니코드 문자를 씁니다.  
  
 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 것을 제외하고 동일합니다.  자세한 내용은 `_putch_nolock`, `_putwch_nolock`을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|**putch**|`_putch`|`_putch`|**putwchar**|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_putch`|\<conio.h\>|  
|**putwchar**|\<conio.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
 [strtod](../../c-runtime-library/reference/getch-getwch.md)의 예제를 참조하십시오.  
  
## 참고 항목  
 [콘솔 및 포트 I\/O](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)