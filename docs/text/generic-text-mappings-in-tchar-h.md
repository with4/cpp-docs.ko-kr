---
title: "Tchar.h의 제네릭 텍스트 매핑 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: tchar.h
dev_langs: C++
helpviewer_keywords:
- mapping generic-text
- generic-text mappings [C++]
- character sets [C++], generic-text mappings
- Unicode [C++], generic-text mappings
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 6fe2773ab5a6429f2ab2c863598dabb4dddef628
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="generic-text-mappings-in-tcharh"></a>Tchar.h의 제네릭 텍스트 매핑
국가별 사용에 대 한 코드의 전송을 단순화 하기 위해는 [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] 런타임 라이브러리는 [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)]-다양 한 데이터 형식을, 루틴 및 다른 개체에 대 한 특정 일반 텍스트 매핑. 1 바이트의 멀티 바이트에 대해 컴파일할 수 있는 제네릭 코드를 작성 하려면 Tchar.h에 정의 된 이러한 매핑을 사용 하 여 또는 [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] 문자를 사용 하 여 정의 하는 매니페스트 상수에 따라 집합을 `#define` 문. 제네릭 텍스트 매핑은 [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] 없는 확장 [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] 호환 됩니다.  
  
 Tchar.h를 사용 하 여 싱글바이트 멀티 바이트 문자 집합 (MBCS)를 빌드할 수 있습니다 및 [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] 에서 동일한 원인에서 응용 프로그램입니다. Tchar.h 매크로 정의 하며 (접두사가 있는 `_tcs`)를 매핑할 올바른 전처리기 정의가 있는 `str`, `_mbs`, 또는 `wcs` 함수 적절 하 게 합니다. MBCS를 빌드하려면 기호를 정의 `_MBCS`합니다. 만들려는 [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)], 기호 정의 `_UNICODE`합니다. 단일 바이트 응용 프로그램을 빌드하려면 모두 (기본값)을 정의 합니다. 기본적으로 `_MBCS` MFC 응용 프로그램에 대해 정의 됩니다.  
  
 `_TCHAR` tchar.h에서 데이터 형식 조건에 따라 정의 됩니다. 경우 기호 `_UNICODE` 빌드에 대해 정의 된 `_TCHAR` 로 정의 `wchar_t`, 그렇지 않으면으로 정의 되어 단일 바이트 및 MBCS 빌드에 대 한 `char`합니다. (`wchar_t`, 기본 유니코드 와이드 문자 데이터 형식에는 8 비트 부호 있는 16 비트 관련 `char`.) 국가별 응용 프로그램에 대 한 사용는 `_tcs` 작동 하는 함수 패밀리 `_TCHAR` 단위, 바이트가 아닙니다. 예를 들어 `_tcsncpy` 복사본 `n` `_TCHARs`이 아니라 `n` 바이트입니다.  
  
 일부 단일 바이트 문자 집합 (SBCS) 문자열 처리 함수는 (부호 있음) 하기 때문에 `char*` 매개 변수, 형식이 일치 하지 않습니다 컴파일러 경고가 표시 때 `_MBCS` 정의 됩니다. 이 경고를 방지 하는 방법은 세 가지가 있습니다.  
  
1.  Tchar.h에 형식이 안전한 인라인 함수 썽크를 사용 합니다. 이것은 기본적인 동작입니다.  
  
2.  Tchar.h에 직접 매크로 사용 하 여 정의 하 여 `_MB_MAP_DIRECT` 명령줄에서. 이렇게 하는 경우 형식을 수동으로 일치시켜야 합니다. 가장 빠른 방법 이지만 형식이 안전 하지 않습니다.  
  
3.  Tchar.h에 형식이 안전한 정적으로 연결 된 라이브러리 함수 썽크를 사용 합니다. 이렇게 하려면 명령줄에서 `_NO_INLINING` 상수를 정의합니다. 이는 속도가 가장 느린 방법이지만 형식은 가장 안전합니다.  
  
### <a name="preprocessor-directives-for-generic-text-mappings"></a>일반 텍스트 매핑용 전처리기 지시문  
  
|# 정의|컴파일 버전|예제|  
|---------------|----------------------|-------------|  
|`_UNICODE`|[!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)](와이드 문자)|`_tcsrev`는 `_wcsrev`에 매핑됩니다.|  
|`_MBCS`|멀티바이트 문자|`_tcsrev`는 `_mbsrev`에 매핑됩니다.|  
|None (기본값에 `_UNICODE` 나 `_MBCS` 정의)|SBCS ([!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)])|`_tcsrev`는 `strrev`에 매핑됩니다.|  
  
 예를 들어 일반 텍스트 함수 `_tcsrev`, Tchar.h에 정의 된 매핑됩니다 `_mbsrev` 정의한 경우 `_MBCS` 프로그램에서 또는 `_wcsrev` 정의한 경우 `_UNICODE`합니다. 그렇지 않으면 `_tcsrev`는 `strrev`로 매핑됩니다. 다른 데이터 형식 매핑은 Tchar.h 프로그래밍 편의 위해 제공 되지만 `_TCHAR` 가장 유용 합니다.  
  
### <a name="generic-text-data-type-mappings"></a>일반 텍스트 데이터 형식 매핑  
  
|일반 텍스트<br /><br /> 데이터 형식 이름|_UNICODE &<br /><br /> _MBCS 정의 되지 않음|_MBCS<br /><br /> 정의됨|_UNICODE<br /><br /> 정의됨|  
|--------------------------------------|----------------------------------------|------------------------|---------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`unsigned int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` 또는 `_TEXT`|효과 없음(전처리기에 의해 제거됨)|효과 없음(전처리기에 의해 제거됨)|`L`(다음 문자 또는 문자열을 변환의 [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] 테이블에 해당)|  
  
 제네릭 텍스트 매핑 루틴, 변수 및 기타 개체의 목록이 참조 [제네릭 텍스트 매핑](../c-runtime-library/generic-text-mappings.md) 런타임 라이브러리 참조에서.  
  
> [!NOTE]
>  사용 하지 않는 `str` 포함 하는 유니코드 문자열에 있는 함수 제품군 null 바이트를 포함 합니다. 마찬가지로, 사용 하지 않는 `wcs` 함수 패밀리를 함께 MBCS 이동해 왔거나 SBCS 문자열입니다.  
  
 다음 코드 조각은 사용법을 보여 줍니다. `_TCHAR` 및 `_tcsrev` MBCS에 매핑하는 데 [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)], 및 SBCS 모델.  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 경우 `_MBCS` 되었습니다 정의 전처리기는 다음이 부분 매핑합니다이 코드에:  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 경우 `_UNICODE` 되었습니다 정의 전처리기는 다음이 부분 매핑합니다이 코드에:  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 모두 `_MBCS` 또는 `_UNICODE` 된 정의 전처리기 조각에 매핑됩니다 단일 바이트 [!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)] 코드를 다음과 같이 합니다.  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 따라서 작성할 수 있습니다. 유지 관리 및 세 가지 문자 집합 중 하나에 적용 되는 루틴을 사용 하 여 실행을 단일 소스 코드 파일을 컴파일하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)   
 [_MBCS 코드와 TCHAR.H 데이터 형식 사용](../text/using-tchar-h-data-types-with-mbcs-code.md)