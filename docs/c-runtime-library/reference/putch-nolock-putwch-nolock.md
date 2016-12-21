---
title: "_putch_nolock, _putwch_nolock | Microsoft Docs"
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
  - "_putwch_nolock"
  - "_putch_nolock"
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
  - "_putch_nolock"
  - "_puttch_nolock"
  - "putch_nolock"
  - "putwch_nolock"
  - "_putwch_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_putch_nolock 함수"
  - "_puttch_nolock 함수"
  - "_putwch_nolock 함수"
  - "문자, 작성"
  - "콘솔, 문자 쓰기"
  - "putch_nolock 함수"
  - "puttch_nolock 함수"
  - "putwch_nolock 함수"
ms.assetid: edbc811d-bac6-47fa-a872-fe4f3a1590b0
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _putch_nolock, _putwch_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스레드를 잠그지 않고 콘솔에 문자를 씁니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
  
      int _putch_nolock(  
int c   
);  
wint_t _putwch_nolock(  
wchar_t c  
);  
```  
  
#### 매개 변수  
 *c*  
 테스트할 문자입니다.  
  
## 반환 값  
 성공하면 *c* 를 반환합니다.  만약 **\_putch\_nolock** 가 실패하면, **EOF** 를 반환합니다; **\_putwch\_nolock** 가 실패하면 **WEOF** 를 반환합니다.  
  
## 설명  
 **\_putch\_nolock** 및 **\_putwch\_nolock** 는 **\_putch** 및 **\_putwch** 으로 동일합니다. 각각 제외하고 다른 스레드에서 간섭에서 보호 되지 않습니다.  이들은 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다.  단일 스레드 응용 프로그램과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|**\_puttch\_nolock**|**\_putch\_nolock**|**\_putch\_nolock**|**\_putwch\_nolock**|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|**\_putch\_nolock**|\<conio.h\>|  
|**\_putwch\_nolock**|\<conio.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 참고 항목  
 [콘솔 및 포트 I\/O](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)