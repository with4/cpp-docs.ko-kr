---
title: "_putenv, _wputenv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_putenv"
  - "_wputenv"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tputenv"
  - "_wputenv"
  - "_putenv"
  - "wputenv"
  - "tputenv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_putenv 함수"
  - "_tputenv 함수"
  - "_wputenv 함수"
  - "환경 변수, 만들기"
  - "환경 변수, 제거"
  - "환경 변수, 수정"
  - "putenv 함수"
  - "tputenv 함수"
  - "wputenv 함수"
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _putenv, _wputenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

생성, 수정, 또는 환경 변수를 제거합니다.  이러한 기능의 더 안전한 버전을 사용할 수 있습니다. [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _putenv(  
   const char *envstring   
);  
int _wputenv(  
   const wchar_t *envstring   
);  
```  
  
#### 매개 변수  
 `envstring`  
 환경 문자열 정의입니다.  
  
## 반환 값  
 성공 하면 0 또는 오류 발생 시\-1을 반환 합니다.  
  
## 설명  
 이 `_putenv` 함수는 새 환경 변수를 추가하거나 기존 환경 변수의 값을 수정 합니다.  환경 변수 프로세스 \(예: 프로그램으로 연결 된 라이브러리에 대 한 기본 검색 경로\) 실행되는 환경을 정의합니다.  `_wputenv`는 `_putenv`의 와이드 문자 버전이며, `_wputenv`의 `envstring` 인수는 와이드 문자 문자열입니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tputenv`|`_putenv`|`_putenv`|`_wputenv`|  
  
 이 `envstring` 인수는 `varname=string` 양식의 문자열에 대한 포인터인데, `varname` 은 추가 되거나 수정된 환경 변수의 이름이고 `string` 은 값의 변수입니다.  만약 `varname` 이 환경의 부분으로 준비된 경우, 이 값은 `string` 으로 대체합니다; 그렇지 않으면, 새로운 `varname` 볌수 그리고 `string` 값은 환경을 추가합니다.  다른 단어로, `varname=` 으로 지정된 — 빈 `string` 로 지정된 환경으로 부터 변수들을 제거할 수 있습니다.  
  
 `_putenv` 및 `_wputenv` 은 현재 프로세스가 로컬 환경에만 영향을 줍니다; 명령 수준 환경 수정에 사용할 수 없습니다.  즉, 이 함수는 운영 체제에서 프로세스에 대해 생성된 환경 세그먼트가 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조에만 작동합니다.  현재 프로세스가 종료될 때 환경\(대부분의 경우 운영 체제 수준\)에서 호출하는 프로세스의 수준으로 돌아갑니다.  그러나, 수정된 환경은 `_spawn`, `_exec`, 혹은 `system` 로 생성된 모든 새로운 프로세스를 전달할 수 있고, 이러한 새로운 프로세스는 `_putenv` 과 `_wputenv` 로 추가된 모든 새로운 아이템을 얻습니다.  
  
 환경 엔트리를 직접 변경하지 마십시오: 대신, 이를 변경하기 위한 `_putenv` 혹은 `_wputenv` 을 사용하세요.  특히, 요소를 직접 확보는 `_environ[]` 전역 배열로 처리되고 잘 된 메모리 발생할 수 있습니다.  
  
 `getenv` 과 `_putenv` 은 환경 테이블에 엑세스하는 전역 변수 `_environ` 를 사용합니다; `_wgetenv` 과 `_wputenv` 는 `_wenviron` 사용합니다.  `_putenv` 과 `_wputenv` 는 `_environ` 과 `_wenviron` 의 값을 변화할 것이고, 게다가 `main` 의 `_envp` 인수와 `wmain` 의 \_`wenvp` 인수를 무효화합니다.  따라서, 환경 정보에 액세스하는 `_environ` 혹은 `_wenviron` 을 사용이 더 안전합니다.  전역 변수의 `_putenv` 과 `_wputenv` 의 관계에 대한 자세한 내용을 보시려면, [\_environ, \_wenviron](../../c-runtime-library/environ-wenviron.md)를 참조하세요.  
  
> [!NOTE]
>  `_putenv` 및 `_getenv` 함수 패밀리는 스레드로부터 안전 하지 않습니다.  `_putenv` 임의 오류가 발생 하 여 문자열을 수정하는 동안, `_getenv` 는 문자열 포인터를 반환합니다.  이러한 함수에 대한 호출은 동기화해야 합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_putenv`|\<stdlib.h\>|  
|`_wputenv`|\<stdlib.h\> 또는 \<wchar.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 `_putenv`를 사용하는 방법에 대한 예제는 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)를 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_searchenv, \_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)