---
title: "Tchar.h의 제네릭 텍스트 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ""tchar.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "문자 집합[C++], 일반 텍스트 매핑"
  - "일반 텍스트 매핑[C++]"
  - "일반 텍스트 매핑"
  - "매핑[C++], TCHAR.H"
  - "MBCS[C++], 일반 텍스트 매핑"
  - "TCHAR.H 데이터 형식, 매핑"
  - "유니코드[C++], 일반 텍스트 매핑"
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
caps.latest.revision: 12
caps.handback.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Tchar.h의 제네릭 텍스트 매핑
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

국제적으로 사용할 수 있도록 코드 전송을 단순화하기 위해 [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] 런타임 라이브러리는 많은 데이터 형식, 루틴 및 기타 개체에 대해 [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] 고유의 제네릭 텍스트 매핑을 제공합니다.  Tchar.h에 정의되는 이러한 매핑을 사용하여 제네릭 코드를 작성할 수 있으며, 이러한 제네릭 코드는 `#define` 문을 사용하여 정의하는 명시적 상수에 따라 싱글바이트, 멀티바이트 또는 [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)] 문자 집합에 맞게 컴파일됩니다.  제네릭 텍스트 매핑은 [!INCLUDE[vcpransi](../preprocessor/includes/vcpransi_md.md)]와 호환되지 않는 [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] 확장입니다.  
  
 Tchar.h를 사용하면 동일한 소스로부터 싱글바이트, MBCS\(멀티바이트 문자 집합\) 및 [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)] 응용 프로그램을 빌드할 수 있습니다.  Tchar.h는 `_tcs` 접두사가 있는 매크로를 정의하며, 이 매크로는 전처리기 정의가 올바를 경우 `str`, `_mbs` 또는 `wcs` 함수에 적절하게 매핑됩니다.  MBCS를 빌드하려면 `_MBCS` 기호를 정의합니다.  [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)]를 빌드하려면 `_UNICODE` 기호를 정의합니다.  싱글바이트 응용 프로그램을 빌드하려면 기본적으로 아무 것도 정의하지 않습니다.  MFC 응용 프로그램의 경우 기본적으로 `_MBCS`가 정의됩니다.  
  
 `_TCHAR` 데이터 형식은 Tchar.h에서 조건부로 정의됩니다.  빌드에 대해 `_UNICODE` 기호를 정의하면 `_TCHAR`는 `wchar_t`로 정의됩니다. 싱글바이트 빌드와 MBCS 빌드의 경우에는 `char`로 정의됩니다. 기본 유니코드 와이드 문자의 데이터 형식인 `wchar_t`는 부호 있는 8비트 `char`의 16비트 형식입니다. 국가별 응용 프로그램에서는 바이트 단위가 아니라 `_TCHAR` 단위로 작동하는 `_tcs` 함수 패밀리를 사용합니다.  예를 들어, `_tcsncpy`는 `n` 바이트가 아니라 `n` `_TCHARs`를 복사합니다.  
  
 일부 SBCS\(싱글바이트 문자 집합\) 문자열 처리 함수는 \(부호 있는\) `char*` 매개 변수를 사용하기 때문에 `_MBCS`가 정의되면 형식이 일치하지 않는다는 컴파일러 경고가 표시됩니다.  다음과 같은 세 가지 방법으로 이 경고를 방지할 수 있습니다.  
  
1.  Tchar.h에 형식이 안전한 인라인 함수 썽크를 사용합니다.  이것은 기본적인 동작입니다.  
  
2.  명령줄에서 `_MB_MAP_DIRECT`를 정의하여 Tchar.h에 직접 매크로를 사용합니다.  이 경우 수동으로 형식을 일치시켜야 합니다.  속도가 가장 빠른 방법이지만 형식이 안전하지 않습니다.  
  
3.  Tchar.h에 형식이 안전한 정적 링크 라이브러리 함수 썽크를 사용합니다.  이렇게 하려면 명령줄에서 상수 `_NO_INLINING`을 정의합니다.  속도가 가장 느린 방법이지만 형식은 가장 안전합니다.  
  
### 일반 텍스트 매핑을 위한 전처리기 지시문  
  
|\#define|컴파일 버전|예제|  
|--------------|------------|--------|  
|`_UNICODE`|[!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)]\(와이드 문자\)|`_tcsrev`가 `_wcsrev`로 매핑|  
|`_MBCS`|멀티바이트 문자|`_tcsrev` 가 `_mbsrev`로 매핑|  
|없음\(기본값: `_UNICODE`와 `_MBCS` 모두 정의되지 않음\)|SBCS\([!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)]\)|`_tcsrev`가 `strrev`로 매핑|  
  
 예를 들어, Tchar.h에 정의되는 일반 텍스트 함수인 `_tcsrev`는 프로그램에 `_MBCS`가 정의된 경우 `_mbsrev`로 매핑되고, `_UNICODE`가 정의된 경우 `_wcsrev`로 매핑됩니다.  그렇지 않으면 `_tcsrev`가 `strrev`로 매핑됩니다.  간편하게 프로그래밍할 수 있도록 Tchar.h에 다른 데이터 형식 매핑도 제공되지만 `_TCHAR`가 가장 유용합니다.  
  
### 제네릭 텍스트 데이터 형식 매핑  
  
|제네릭 텍스트<br /><br /> 데이터 형식 이름|\_UNICODE &<br /><br /> \_MBCS가 정의되지 않음|\_MBCS<br /><br /> 정의됨|\_UNICODE<br /><br /> 정의됨|  
|---------------------------|-------------------------------------|--------------------|-----------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`unsigned int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` 또는 `_TEXT`|적용 안 됨\(전처리기에서 제거\)|적용 안 됨\(전처리기에서 제거\)|`L`\(다음 문자 또는 문자열을 해당 [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)]로 변환\)|  
  
 루틴, 변수 및 기타 개체에 대한 제네릭 텍스트 매핑의 목록을 보려면 Run\-Time Library Reference의 [일반 텍스트 매핑](../c-runtime-library/generic-text-mappings.md)을 참조하십시오.  
  
> [!NOTE]
>  유니코드 문자열과 `str` 함수 패밀리를 함께 사용하지 마십시오. 포함 Null 바이트가 들어 있을 수 있습니다.  마찬가지로 MBCS\(또는 SBCS\) 문자열과 `wcs` 함수 패밀리를 함께 사용하지 마십시오.  
  
 다음 코드 부분은 MBCS, [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)] 및 SBCS 모델에 매핑하기 위한 `_TCHAR` 및 `_tcsrev`의 사용에 대해 설명합니다.  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 `_MBCS`가 정의되어 있으면 전처리기는 다음 부분을 코드에 매핑합니다.  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 `_UNICODE`가 정의되어 있으면 전처리기는 다음 부분을 코드에 매핑합니다.  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 `_MBCS`와 `_UNICODE`가 모두 정의되지 않았으면 전처리기는 다음과 같이 해당 부분을 싱글바이트 [!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)] 코드에 매핑합니다.  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 따라서 사용자는 세 종류의 문자 집합 중 하나와 관련된 루틴을 사용하여 실행할 단일 코드 파일을 작성, 유지 관리 및 컴파일할 수 있습니다.  
  
## 참고 항목  
 [텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)   
 [\_MBCS 코드와 TCHAR.H 데이터 형식 사용](../text/using-tchar-h-data-types-with-mbcs-code.md)