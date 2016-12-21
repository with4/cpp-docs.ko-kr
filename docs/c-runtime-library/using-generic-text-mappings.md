---
title: "일반 텍스트 매핑 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_UNICODE"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_MBCS 데이터 형식"
  - "_T 형식"
  - "_TCHAR 형식"
  - "_TEXT 형식"
  - "_TINT 형식"
  - "_TSCHAR 형식"
  - "_TUCHAR 형식"
  - "_TXCHAR 형식"
  - "_UNICODE 상수"
  - "일반 텍스트 데이터 형식"
  - "일반 텍스트 매핑"
  - "매핑, 일반 텍스트"
  - "MBCS 데이터 형식"
  - "T 형식"
  - "TCHAR 형식"
  - "TCHAR.H 데이터 형식, 정의된 매핑"
  - "TEXT 형식"
  - "TINT 형식"
  - "TSCHAR 형식"
  - "TUCHAR 형식"
  - "TXCHAR 형식"
  - "UNICODE 상수"
ms.assetid: 2848121c-e51f-4b9b-a2e6-833ece4b0cb3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 일반 텍스트 매핑 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 다양한 국제 시장을 위한 코드 개발을 단순화하기 위해, Microsoft 런타임 라이브러리는 많은 데이터 형식, 루틴 및 기타 개체에 대한 Microsoft 고유의 "일반 텍스트"매핑을 제공합니다.  이러한 매핑은 TCHAR.H에 정의 되어 있습니다.  이러한 이름 매핑을 `#define` 명세서를 사용해서 지정한 매니페스트 상수에 따른 문자 집합: ASCII \(SBCS\), MBCS, 또는 Unicode 중 세 종류에 대해 컴파인 될 수 있는 일반 코드에 쓰기 위해 사용할 수 있습니다.  제네릭 텍스트 매핑은 ANSI와 호환 되지 않는 Microsoft 확장입니다.  
  
### 일반 텍스트 매핑을 위한 전처리기 지시문  
  
|\#define|컴파일 버전|예제|  
|--------------|------------|--------|  
|`_UNICODE`|Unicode \(wide\-character\)|`_tcsrev`가 `_wcsrev`로 매핑|  
|`_MBCS`|멀티바이트 문자|`_tcsrev`가 `_mbsrev`로 매핑|  
|없음\(기본값: `_UNICODE`와 `_MBCS` 모두 정의되지 않음\)|SBCS \(ASCII\)|`_tcsrev`  는 `strrev` 에 매핑합니다.|  
  
 예를 들어, TCHAR.H 에 정의된 일반 텍스트 함수 `_tcsrev` 는 `MBCS` 가 프로그램에 정의 된 경우 `mbsrev` 에 매핑 되고 `_UNICODE`  가 정의된 경우 `_wcsrev`  로 매핑 됩니다.  그렇지 않으면 `_tcsrev` 가 `strrev`로 매핑됩니다.  
  
 TCHAR.H 에 정의 된 일반 텍스트 형식은 `_MBCS` 가 정의된 경우 `_TCHAR` 는 `char` 형에 매핑 되고 `_UNICODE` 가 정의 된 경우 `wchar_t` 형에 매핑되며 상수가 정의되지 않은 경우 `char` 로 매핑됩니다.  간편한 프로그래밍을 위해 TCHAR.H 에서는 다른 데이터 형식의 매핑도 지원하지만 `_TCHAR` 가 가장 유용합니다.  
  
### 제네릭 텍스트 데이터 형식 매핑  
  
|일반 텍스트 형식 이름|SBCS \(\_UNICODE, \_MBCS not defined\)|\_MBCS 정의됨|\_UNICODE 정의됨|  
|------------------|--------------------------------------------|----------------|-------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` 또는 `_TEXT`|적용 안 됨\(전처리기에서 제거\)|적용 안 됨\(전처리기에서 제거\)|`L`\(다음 문자 또는 문자열을 해당 Unicode 로 변환\)|  
  
 루틴, 변수 및 다른 개체의 일반 텍스트 매핑의 전체 목록은 [Generic\-Text Mappings](../c-runtime-library/generic-text-mappings.md) 를 참조하십시오.  
  
 다음 코드 부분은 MBCS, Unicode, 및 SBCS 모델에 매핑하기 위한 `_TCHAR` 및 `_tcsrev` 의 사용을 설명합니다.  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 `MBCS` 가 정의된 경우, 전처리기는 다음 코드에 조각코드를 매핑합니다.  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 `_UNICODE` 가 정의된 경우, 전처리기는 다음 코드에 같은 코드를 매핑합니다.  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 `_MBCS`와 `_UNICODE`가 모두 정의되지 않았으면 전처리기는 다음과 같이 해당 부분을 싱글바이트 ASCII 코드에 매핑합니다.  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 따라서 사용자는 세 종류의 문자 집합 중 하나와 관련된 루틴을 사용하여 실행할 단일 코드 파일을 작성, 유지 관리 및 컴파일할 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [일반 텍스트 매핑](../c-runtime-library/generic-text-mappings.md)   
 [데이터 형식 매핑](../c-runtime-library/data-type-mappings.md)   
 [상수 및 전역 변수 매핑](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [루틴 매핑](../c-runtime-library/routine-mappings.md)   
 [샘플 일반 텍스트 프로그램](../c-runtime-library/a-sample-generic-text-program.md)