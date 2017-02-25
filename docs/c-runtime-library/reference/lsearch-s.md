---
title: "_lsearch_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lsearch_s"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_lsearch_s"
  - "lsearch_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_lsearch_s 함수"
  - "배열[CRT], 검색"
  - "keys, 배열에서 찾기"
  - "선형 검색"
  - "lsearch_s 함수"
  - "검색, 선형"
  - "값, 검색"
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _lsearch_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

값에 대한 선형 검색을 수행합니다.  [\_lsearch](../../c-runtime-library/reference/lsearch.md) 의 버젼은 보안 향상과 관련된[CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)로 설명됩니다.  
  
## 구문  
  
```  
void *_lsearch_s(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### 매개 변수  
 `key`  
 검색할 개체입니다.  
  
 `base`  
 검색될 기본 배열을 가리키는 포인터입니다.  
  
 `num`  
 요소 수 입니다.  
  
 `size`  
 바이트에서 각 배열 요소의 크기입니다.  
  
 `compare`  
 비교 루틴을 가리키는 포인터입니다.  두 번째 매개 변수는 검색에 대한 키에 대한 포인터입니다.  세 번째 매개 변수는 키와 비교된 배열 요소를 가리키는 포인터입니다.  
  
 `context`  
 비교 함수에서 액세스될 수 있는 개체에 대한 포인터입니다.  
  
## 반환 값  
 만일 `key` 를 찾은 경우, `_lsearch_s`  는 `key` 와 매치되는 `base` 에서 배열의 요소에 대한 포인터를 반환합니다.  만일 `key` 가 발견되지 않으면, `_lsearch_s`  는 배열의 끝에 새롭게 추가된 항목을 가리키는 포인터를 반환합니다.  
  
 만일 잘못된 매개변수가 함수에 전달된 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 나타난 것처럼 이 함수는 잘못된 매개변수 처리기를 호출합니다.  만일 계속해서 실행하도록 허용된 경우, `errno`  를 `EINVAL` 로 설정하고 이 함수는 `NULL` 를 반환합니다.  자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
### 오류 조건  
  
|`key`|`base`|`compare`|`num`|`size`|`errno`|  
|-----------|------------|---------------|-----------|------------|-------------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|0|`EINVAL`|  
|any|any|`NULL`|입니다.|any|`EINVAL`|  
  
## 설명  
 이 `_lsearch_s` 함수는 `key` 값을 위한 선형 검색을 `num` 요소에 대하여 실행합니다. 이는 각각 `width` 바이트입니다.  이 `bsearch_s` 와 달리, `_lsearch_s` 는 배열이 저장되는 것을 필요로 하지 않습니다.  `key`가 발견되지 않으면, `_lsearch_s`는 그것을 배열의 끝에 추가하고 `num`을 증가시킵니다.  
  
 이 `compare` 함수는 사용자가 공급한 루틴의 포인터입니다. 이는 두 배열 요소를 비교하고 그때 그것의 관계를 명시하는 값을 반환합니다.  `compare` 함수 역시 첫번째 인수로써 컨텍스트에 대한 포인터를 사용합니다.  `_lsearch_s` 는 각 호출에서 두 배열 원소들에 대한 포인터를 전달하여 검색하는 동안 `compare` 을 한번 이상 호출합니다.  이 `compare` 루틴은 요소를 비교하고, 0이 아닌 값을 반환하거나\(요소가 다르단 의미\) 0을\(요소가 동일하단 의미\) 반환합니다.  
  
 이 `context` 포인터는 매우 유용합니다. 만일 검색된 데이터 구조는 개체의 파트일 경우, `compare` 함수는 개체 멤버에 접근할 필요가 있습니다.  예를 들어, `compare` 함수에서 코드는 보이드 포인터를 적절한 개체 형식에 캐스팅할 수 있고, 객체의 멤버에 접근할 수 있습니다.  이 `context` 포인터의 추가는 `_lsearch_s` 를 더욱더 안전하게 만듭니다. 왜냐하면 추가적인 컨텍스트는 재진입 버그들을 피할 수 있습니다. 이는 `compare` 함수를 데이터가 사용할 수 있게 만드는 정적 변수를 사용하는 것과 연관되어 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_lsearch_s`|\<검색\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [검색 및 정렬](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lfind\_s](../../c-runtime-library/reference/lfind-s.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)