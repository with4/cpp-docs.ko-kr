---
title: "보안이 강화된 CRT 함수 버전 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CRT, 강화된 보안 기능"
  - "보안[CRT]"
  - "보안이 강화된 CRT"
ms.assetid: f87e5a01-4cb2-4379-9e8f-d4693828c55a
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 보안이 강화된 CRT 함수 버전
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

런타임 라이브러리 루틴의 더 안전한 버전을 사용할 수 있습니다. CRT의 강화된 보안 기능과 관련된 자세한 내용은 [CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md)를 참조하세요.  
  
 **보안 함수**  
  
|CRT 함수|보안이 강화된 함수|기능|  
|------------|----------------|--------|  
|[\_access, \_waccess](../c-runtime-library/reference/access-waccess.md)|[\_access\_s, \_waccess\_s](../c-runtime-library/reference/access-s-waccess-s.md)|파일 액세스 권한을 결정합니다.|  
|[\_alloca](../c-runtime-library/reference/alloca.md)|[\_malloca](../c-runtime-library/reference/malloca.md)|스택에 메모리를 할당합니다.|  
|[asctime, \_wasctime](../c-runtime-library/reference/asctime-wasctime.md)|[asctime\_s, \_wasctime\_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|`struct tm` 형식에서 문자열로 시간을 변환합니다.|  
|[bsearch](../c-runtime-library/reference/bsearch.md)|[bsearch\_s](../c-runtime-library/reference/bsearch-s.md)|정렬된 배열의 이진 검색을 수행합니다.|  
|사용되지 않는 함수|[\_cgets\_s, \_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|콘솔에서 문자열을 가져옵니다.|  
|[\_chsize](../c-runtime-library/reference/chsize.md)|[\_chsize\_s](../c-runtime-library/reference/chsize-s.md)|파일 크기를 변경합니다.|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|[clearerr\_s](../c-runtime-library/reference/clearerr-s.md)|스트림 오류 표시기를 다시 설정합니다.|  
|[\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md)|[\_controlfp\_s](../c-runtime-library/reference/controlfp-s.md)|부동 소수점 제어 단어를 가져오고 설정합니다.|  
|[\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|[\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|형식을 지정하고 콘솔에 출력합니다.|  
|[\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)|[\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|콘솔에서 형식이 지정된 데이터를 읽습니다.|  
|[ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)|[\_ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|`time_t`, `__time32_t` 또는 `__time64_t` 형식에서 문자열로 시간을 변환합니다.|  
|[\_ecvt](../c-runtime-library/reference/ecvt.md)|[\_ecvt\_s](../c-runtime-library/reference/ecvt-s.md)|`double` 숫자를 문자열로 변환합니다.|  
|[\_fcvt](../c-runtime-library/reference/fcvt.md)|[\_fcvt\_s](../c-runtime-library/reference/fcvt-s.md)|부동 소수점 숫자를 문자열로 변환합니다.|  
|[fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)|[fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|파일을 엽니다.|  
|[fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|형식이 지정된 데이터를 스트림에 출력합니다.|  
|[fread](../c-runtime-library/reference/fread.md)|[fread\_s](../c-runtime-library/reference/fread-s.md)|파일에서 읽습니다.|  
|[\_fread\_nolock](../c-runtime-library/reference/fread-nolock.md)|[\_fread\_nolock\_s](../c-runtime-library/reference/fread-nolock-s2.md)|다중 스레드 쓰기 잠금을 사용하지 않고 파일에서 읽습니다.|  
|[freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)|[freopen\_s, \_wfreopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|파일을 다시 엽니다.|  
|[fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)|스트림에서 형식이 지정된 데이터를 읽습니다.|  
|[\_ftime, \_ftime32, \_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md)|[\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)|현재 시간을 가져옵니다.|  
|[\_gcvt](../c-runtime-library/reference/gcvt.md)|[\_gcvt\_s](../c-runtime-library/reference/gcvt-s.md)|부동 소수점 값을 문자열로 변환하고 버퍼에 저장합니다.|  
|[getenv, \_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)|[getenv\_s, \_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|현재 환경에서 값을 가져옵니다.|  
|사용되지 않는 함수|[gets\_s, \_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md)|`stdin` 스트림에서 한 줄을 가져옵니다.|  
|[gmtime, \_gmtime32, \_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)|[\_gmtime32\_s, \_gmtime64\_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|`time_t` 형식에서 `struct``tm`으로 또는 `__time64_t` 형식에서 `struct tm`으로 시간을 변환합니다.|  
|[\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)|[\_itoa\_s, \_i64toa\_s, \_ui64toa\_s, \_itow\_s, \_i64tow\_s, \_ui64tow\_s](../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)|정수를 문자열로 변환합니다.|  
|[\_lfind](../c-runtime-library/reference/lfind.md)|[\_lfind\_s](../c-runtime-library/reference/lfind-s.md)|지정된 키에 대한 선형 검색을 수행합니다.|  
|[localtime, \_localtime32, \_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md)|[localtime\_s, \_localtime32\_s, \_localtime64\_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|`time_t` 형식에서 `struct tm`으로 또는 `__time64_t` 형식에서 `struct tm`\(로컬 수정 포함\)으로 시간을 변환합니다.|  
|[\_lsearch](../c-runtime-library/reference/lsearch.md)|[\_lsearch\_s](../c-runtime-library/reference/lsearch-s.md)|값에 대한 선형 검색을 수행합니다. 찾을 수 없는 경우 목록의 끝에 추가합니다.|  
|[\_ltoa, \_ltow](../c-runtime-library/reference/ltoa-ltow.md)|[\_ltoa\_s, \_ltow\_s](../c-runtime-library/reference/ltoa-s-ltow-s.md)|long 정수를 문자열로 변환합니다.|  
|[\_makepath, \_wmakepath](../c-runtime-library/reference/makepath-wmakepath.md)|[\_makepath\_s, \_wmakepath\_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|구성 요소에서 경로 이름을 만듭니다.|  
|[\_mbccpy, \_mbccpy\_l](../c-runtime-library/reference/mbccpy-mbccpy-l.md)|[\_mbccpy\_s, \_mbccpy\_s\_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|한 문자열에서 다른 문자열로 멀티바이트 문자를 복사합니다.|  
|[\_mbsnbcat, \_mbsnbcat\_l](../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)|[\_mbsnbcat\_s, \_mbsnbcat\_s\_l](../c-runtime-library/reference/mbsnbcat-s-mbsnbcat-s-l.md)|한 멀티바이트 문자열의 처음 `n`바이트 이하를 다른 문자열에 추가합니다.|  
|[\_mbsnbcpy, \_mbsnbcpy\_l](../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)|[\_mbsnbcpy\_s, \_mbsnbcpy\_s\_l](../c-runtime-library/reference/mbsnbcpy-s-mbsnbcpy-s-l.md)|문자열의 `n`바이트를 대상 문자열에 복사합니다.|  
|[\_mbsnbset, \_mbsnbset\_l](../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)|[\_mbsnbset\_s, \_mbsnbset\_s\_l](../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md)|문자열의 처음 `n`바이트를 지정된 문자로 설정합니다.|  
|[mbsrtowcs](../c-runtime-library/reference/mbsrtowcs.md)|[mbsrtowcs\_s](../c-runtime-library/reference/mbsrtowcs-s.md)|멀티바이트 문자열을 해당 와이드 문자열로 변환합니다.|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)|[mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|멀티바이트 문자 시퀀스를 해당 와이드 문자 시퀀스로 변환합니다.|  
|[memcpy, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)|[memcpy\_s, wmemcpy\_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|버퍼 간에 문자를 복사합니다.|  
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md)|[memmove\_s, wmemmove\_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|한 버퍼를 다른 버퍼로 이동합니다.|  
|[\_mktemp, \_wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md)|[\_mktemp\_s, \_wmktemp\_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|고유한 파일 이름을 만듭니다.|  
|[printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|형식이 지정된 출력을 표준 출력 스트림에 출력합니다.|  
|[\_putenv, \_wputenv](../c-runtime-library/reference/putenv-wputenv.md)|[\_putenv\_s, \_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|환경 변수를 생성, 수정 또는 제거합니다.|  
|[qsort](../c-runtime-library/reference/qsort.md)|[qsort\_s](../c-runtime-library/reference/qsort-s.md)|빠른 정렬을 수행합니다.|  
|[rand](../c-runtime-library/reference/rand.md)|[rand\_s](../c-runtime-library/reference/rand-s.md)|의사 난수를 생성합니다.|  
|[scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)|[scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|표준 입력 스트림에서 형식이 지정된 데이터를 읽습니다.|  
|[\_searchenv, \_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md)|[\_searchenv\_s, \_wsearchenv\_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|환경 경로를 사용하여 파일을 검색합니다.|  
|[snprintf, \_snprintf, \_snprintf\_l, \_snwprintf, \_snwprintf\_l](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|[\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)|문자열에 형식이 지정된 데이터를 씁니다.|  
|[\_snscanf, \_snscanf\_l, \_snwscanf, \_snwscanf\_l](../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md)|[\_snscanf\_s, \_snscanf\_s\_l, \_snwscanf\_s, \_snwscanf\_s\_l](../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)|문자열에서 지정된 길이의 형식이 지정된 데이터를 읽습니다.|  
|[\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)|[\_sopen\_s, \_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|공유할 파일을 엽니다.|  
|[\_splitpath, \_wsplitpath](../c-runtime-library/reference/splitpath-wsplitpath.md)|[\_splitpath\_s, \_wsplitpath\_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|경로 이름을 구성 요소로 분해합니다.|  
|[sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|[sprintf\_s, \_sprintf\_s\_l, swprintf\_s, \_swprintf\_s\_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|문자열에 형식이 지정된 데이터를 씁니다.|  
|[sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)|[sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)|문자열에서 형식이 지정된 데이터를 읽습니다.|  
|[strcat, wcscat, \_mbscat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)|[strcat\_s, wcscat\_s, \_mbscat\_s](../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)|문자열을 추가합니다.|  
|[strcpy, wcscpy, \_mbscpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|[strcpy\_s, wcscpy\_s, \_mbscpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)|문자열을 복사합니다.|  
|[\_strdate, \_wstrdate](../c-runtime-library/reference/strdate-wstrdate.md)|[\_strdate\_s, \_wstrdate\_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|현재 시스템 날짜를 문자열로 반환합니다.|  
|[strerror, \_strerror, \_wcserror, \_\_wcserror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)|[strerror\_s, \_strerror\_s, \_wcserror\_s, \_\_wcserror\_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|시스템 오류 메시지\(`strerror`, `_wcserror`\)를 가져오거나, 사용자가 제공한 오류 메시지\(`_strerror`, `__wcserror`\)를 출력합니다.|  
|[\_strlwr, \_wcslwr, \_mbslwr, \_strlwr\_l, \_wcslwr\_l, \_mbslwr\_l](../c-runtime-library/reference/strlwr-wcslwr-mbslwr-strlwr-l-wcslwr-l-mbslwr-l.md)|[\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|문자열을 소문자로 변환합니다.|  
|[strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|[strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|문자열에 문자를 추가합니다.|  
|[strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)|[strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)|한 문자열의 문자를 다른 문자열에 복사합니다.|  
|[\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)|[\_strnset\_s, \_strnset\_s\_l, \_wcsnset\_s, \_wcsnset\_s\_l, \_mbsnset\_s, \_mbsnset\_s\_l](../c-runtime-library/reference/strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md)|문자열의 처음 n자를 지정된 문자로 설정합니다.|  
|[\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[\_strset\_s, \_strset\_s\_l, \_wcsset\_s, \_wcsset\_s\_l, \_mbsset\_s, \_mbsset\_s\_l](../c-runtime-library/reference/strset-s-strset-s-l-wcsset-s-wcsset-s-l-mbsset-s-mbsset-s-l.md)|문자열의 모든 문자를 지정된 문자로 설정합니다.|  
|[\_strtime, \_wstrtime](../c-runtime-library/reference/strtime-wstrtime.md)|[\_strtime\_s, \_wstrtime\_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|현재 시스템 시간을 문자열로 반환합니다.|  
|[strtok, \_strtok\_l, wcstok, \_wcstok\_l, \_mbstok, \_mbstok\_l](../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md)|[strtok\_s, \_strtok\_s\_l, wcstok\_s, \_wcstok\_s\_l, \_mbstok\_s, \_mbstok\_s\_l](../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)|현재 로캘이나 전달된 로캘을 사용하여 문자열에서 다음 토큰을 찾습니다.|  
|[\_strupr, \_strupr\_l, \_mbsupr, \_mbsupr\_l, \_wcsupr\_l, \_wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md)|[\_strupr\_s, \_strupr\_s\_l, \_mbsupr\_s, \_mbsupr\_s\_l, \_wcsupr\_s, \_wcsupr\_s\_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|문자열을 대문자로 변환합니다.|  
|[tmpfile](../c-runtime-library/reference/tmpfile.md)|[tmpfile\_s](../c-runtime-library/reference/tmpfile-s.md)|임시 파일을 만듭니다.|  
|[\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|[tmpnam\_s, \_wtmpnam\_s](../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)|임시 파일을 만드는 데 사용할 수 있는 이름을 생성합니다.|  
|[\_ultoa, \_ultow](../c-runtime-library/reference/ultoa-ultow.md)|[\_ultoa\_s, \_ultow\_s](../c-runtime-library/reference/ultoa-s-ultow-s.md)|부호 없는 long 정수를 문자열로 변환합니다.|  
|[\_umask](../c-runtime-library/reference/umask.md)|[\_umask\_s](../c-runtime-library/reference/umask-s.md)|기본 파일 사용 권한 마스크를 설정합니다.|  
|[\_vcprintf, \_vcprintf\_l, \_vcwprintf, \_vcwprintf\_l](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[\_vcprintf\_s, \_vcprintf\_s\_l, \_vcwprintf\_s, \_vcwprintf\_s\_l](../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)|인수 목록에 대한 포인터를 사용하여 콘솔에 형식이 지정된 출력을 씁니다.|  
|[vfprintf, \_vfprintf\_l, vfwprintf, \_vfwprintf\_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|[vfprintf\_s, \_vfprintf\_s\_l, vfwprintf\_s, \_vfwprintf\_s\_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|인수 목록에 대한 포인터를 사용하여 형식이 지정된 출력을 씁니다.|  
|[vfscanf, vfwscanf](../c-runtime-library/reference/vfscanf-vfwscanf.md)|[vfscanf\_s, vfwscanf\_s](../c-runtime-library/reference/vfscanf-s-vfwscanf-s.md)|스트림에서 형식이 지정된 데이터를 읽습니다.|  
|[vprintf, \_vprintf\_l, vwprintf, \_vwprintf\_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[vprintf\_s, \_vprintf\_s\_l, vwprintf\_s, \_vwprintf\_s\_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|인수 목록에 대한 포인터를 사용하여 형식이 지정된 출력을 씁니다.|  
|[vscanf, vwscanf](../c-runtime-library/reference/vscanf-vwscanf.md)|[vscanf\_s, vwscanf\_s](../c-runtime-library/reference/vscanf-s-vwscanf-s.md)|표준 입력 스트림에서 형식이 지정된 데이터를 읽습니다.|  
|[vsnprintf, \_vsnprintf, \_vsnprintf\_l, \_vsnwprintf, \_vsnwprintf\_l](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|[vsnprintf\_s, \_vsnprintf\_s, \_vsnprintf\_s\_l, \_vsnwprintf\_s, \_vsnwprintf\_s\_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)|인수 목록에 대한 포인터를 사용하여 형식이 지정된 출력을 씁니다.|  
|[vsprintf, \_vsprintf\_l, vswprintf, \_vswprintf\_l, \_\_vswprintf\_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|[vsprintf\_s, \_vsprintf\_s\_l, vswprintf\_s, \_vswprintf\_s\_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|인수 목록에 대한 포인터를 사용하여 형식이 지정된 출력을 씁니다.|  
|[vsscanf, vswscanf](../c-runtime-library/reference/vsscanf-vswscanf.md)|[vsscanf\_s, vswscanf\_s](../c-runtime-library/reference/vsscanf-s-vswscanf-s.md)|문자열에서 형식이 지정된 데이터를 읽습니다.|  
|[wcrtomb](../c-runtime-library/reference/wcrtomb.md)|[wcrtomb\_s](../c-runtime-library/reference/wcrtomb-s.md)|와이드 문자를 멀티바이트 문자 표현으로 변환합니다.|  
|[wcsrtombs](../c-runtime-library/reference/wcsrtombs.md)|[wcsrtombs\_s](../c-runtime-library/reference/wcsrtombs-s.md)|와이드 문자열을 멀티바이트 문자열 표현으로 변환합니다.|  
|[wcstombs, \_wcstombs\_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md)|[wcstombs\_s, \_wcstombs\_s\_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|와이드 문자 시퀀스를 해당 멀티바이트 문자 시퀀스로 변환합니다.|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md)|[wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|와이드 문자를 해당 멀티바이트 문자로 변환합니다.|  
  
## 참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)