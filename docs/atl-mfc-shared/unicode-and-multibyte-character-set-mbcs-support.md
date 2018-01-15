---
title: "유니코드 및 멀티 바이트 문자 집합 (MBCS) 지원 | Microsoft Docs"
ms.custom: 
ms.date: 1/09/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- MFC [C++], character set support
- MBCS [C++], strings and MFC support
- strings [C++], MBCS support in MFC
- character sets [C++], multibyte
- Unicode [C++], MFC strings
- Unicode [C++], string objects
- strings [C++], Unicode
- strings [C++], character set support
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adbe6ca25afd31c0aba853fde8b503dc333f63f4
ms.sourcegitcommit: 56f6fce7d80e4f61d45752f4c8512e4ef0453e58
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>유니코드 및 MBCS(멀티바이트 문자 집합) 지원

예를 들어 일본어 및 중국어와 일부 언어에서는 있는 큰 문자 집합. Microsoft Foundation 클래스 라이브러리 (MFC)에서는 이러한 시장을 겨냥 한 프로그래밍을 지원 하기 위해 큰 문자 집합을 처리 하는 두 가지 방법을:

- [유니코드](#mfc-support-for-unicode-strings), `wchar_t` 와이드 문자 및 u t F-16으로 인코딩된 문자열을 기반으로 합니다.

- [멀티 바이트 문자 집합 (MBCS)](#mfc-support-for-mbcs-strings), `char` 작은따옴표나 더블 바이트 문자 및 로캘별 문자 집합으로 인코딩된 문자열을 기반으로 합니다.

Microsoft가 새로운 개발에 대 한 유니코드 MFC 라이브러리를 권장 및 MBCS 라이브러리는 Visual Studio 2013과 Visual Studio 2015에서 더 이상 사용 되었습니다. 물론 이에 해당하는 경우는 더 이상 없습니다. Visual Studio 2017에서 MBCS 사용 중단 경고 제거 되었습니다.

## <a name="mfc-support-for-unicode-strings"></a>유니코드 문자열에 대 한 MFC 지원

전체 MFC 클래스 라이브러리는 유니코드 문자 및 와이드 문자에 u t F-16으로 저장 된 문자열에 대 한 조건에 따라 사용 됩니다. 특히 클래스 [CString](../atl-mfc-shared/reference/cstringt-class.md) 는 유니코드를 지원 합니다.

이러한 라이브러리, 디버거 및 DLL 파일은 MFC에서 유니코드를 지 원하는 데 사용 됩니다.

|||||
|-|-|-|-|
|UAFXCW 합니다. LIB|UAFXCW 합니다. PDB|UAFXCWD 합니다. LIB|UAFXCWD 합니다. PDB|
|MFC*버전*U.LIB|MFC*버전*U.PDB|MFC*버전*U.DLL|MFC*버전*UD 합니다. LIB|
|MFC*버전*UD 합니다. PDB|MFC*버전*UD 합니다. DLL|MFCS*버전*U.LIB|MFCS*버전*U.PDB|
|MFCS*버전*UD 합니다. LIB|MFCS*버전*UD 합니다. PDB|MFCM*버전*U.LIB|MFCM*버전*U.PDB|
|MFCM*버전*U.DLL|MFCM*버전*UD 합니다. LIB|MFCM*버전*UD 합니다. PDB|MFCM*버전*UD 합니다. DLL|

(*버전* 에서 파일의 버전 번호를 나타내는 예를 들어 '140' 의미 버전 14.0.)

`CString`에 따라는 `TCHAR` 데이터 형식입니다. 경우 기호 `_UNICODE` 프로그램의 빌드에 대해 정의 된 `TCHAR` 유형으로 정의 된 `wchar_t`, 16 비트 문자 인코딩 형식을 합니다. 그렇지 않으면 `TCHAR` 로 정의 됩니다 `char`, 일반 8 비트 문자 인코딩입니다. 유니코드, 따라서 아래는 `CString` 는 16 비트 문자를 구성 합니다. 유니코드, 없이 이루어져 있는지 형식의 문자 `char`합니다.

응용 프로그램의 전체 유니코드 프로그래밍에 다음을 수행 해야합니다.

- 사용 하 여 `_T` 매크로 리터럴 문자열을 유니코드로 이동 가능 하도록 조건에 따라 코드를 합니다.

- 문자열을 전달 하는 경우에 함수 인수 문자에서 길이 또는 길이 (바이트) 필요한 지 여부에 주의 해야 합니다. 차이점은 유니코드 문자열을 사용 하는 중요 합니다.

- 이식 가능한 버전의 C 런타임 문자열 처리 함수를 사용 합니다.

- 문자 및 문자 포인터에 대 한 다음 데이터 형식을 사용 합니다.

   - 사용 하 여 `TCHAR` 사용 되는 `char`합니다.

   - 사용 하 여 `LPTSTR` 사용 되는 `char*`합니다.

   - 사용 하 여 `LPCTSTR` 사용 되는 `const char*`합니다. `CString`연산자를 제공 `LPCTSTR` 사이 변환할 `CString` 및 `LPCTSTR`합니다.

`CString`또한 유니코드 인식 생성자, 대입 연산자 및 비교 연산자를 제공합니다.

[런타임 라이브러리 참조](../c-runtime-library/c-run-time-library-reference.md) 휴대용 버전의 모든 문자열 처리 함수를 정의 합니다. 자세한 내용은 참조는 범주 [국제화](../c-runtime-library/internationalization.md)합니다.

## <a name="mfc-support-for-mbcs-strings"></a>MBCS 문자열에 대 한 MFC 지원

클래스 라이브러리도 멀티 바이트 문자 집합을 사용할 수 있지만 더블 바이트 문자에 대 한 설정 (DBCS).

멀티 바이트 문자 집합에는 문자 하나 또는 두 개의 바이트 수 있습니다. 2 바이트, 첫 번째 바이트의 경우 특별 한 "선행 바이트"는 코드에 따라 페이지 사용 중인 특정 범위의 즉 선택 합니다. 전체적으로 볼 때, 겹치는 및 "후행 바이트가"는 고유 문자 인코딩을 지정 합니다.

경우 기호 `_MBCS` 형식 프로그램의 빌드에 대해 정의 된 `TCHAR`, 기반이 `CString` 삼고, 매핑됩니다 `char`합니다. 바이트 수를 결정 하는 한 `CString` 는 선행 바이트와 후행 바이트입니다. 이 확인할 수 있도록 하는 함수를 제공 하는 C 런타임 라이브러리입니다.

Dbcs에서 지정 된 문자열은 모든 단일 바이트 ANSI 문자, 모든 더블 바이트 문자 또는 두의 조합을 포함할 수 있습니다. 이러한 가능성에 문자열을 구문 분석할 때는 특별히 주의 해야 합니다. 여기에 `CString` 개체입니다.

> [!NOTE]
> MFC의 유니코드 문자열 serialization 실행 중인 응용 프로그램의 버전에 관계 없이 유니코드와 MBCS 문자열을 읽을 수 있습니다. 데이터 파일은 프로그램의 유니코드 및 MBCS 버전 간에 이식 가능 합니다.

`CString`C 런타임 함수 호출의 특별 한 "일반 텍스트" 버전을 사용 하는 멤버 함수 또는 유니코드 인식 함수를 사용 합니다. 따라서 예를 들어, 하는 경우는 `CString` 함수 호출 `strcmp`, 해당 일반 텍스트 함수를 호출 `_tcscmp` 대신 합니다. 방법에 따라 기호 `_MBCS` 및 `_UNICODE` 정의 된 `_tcscmp` 다음과 같이 매핑합니다.

|||
|-|-|
|`_MBCS`정의|`_mbscmp`|
|`_UNICODE`정의|`wcscmp`|
|정의 된 두 기호|`strcmp`|

> [!NOTE]
> 기호 `_MBCS` 및 `_UNICODE` 함께 사용할 수 없습니다.

모든 런타임 문자열 처리 루틴에 대 한 일반 텍스트 함수 매핑을에 대해서는 설명 [C 런타임 라이브러리 참조](../c-runtime-library/c-run-time-library-reference.md)합니다. 목록에 대 한 참조 [국제화](../c-runtime-library/internationalization.md)합니다.

마찬가지로, `CString` 메서드는 일반 데이터 형식 매핑을 사용 하 여 구현 됩니다. MFC MBCS 및 유니코드 모두를 사용 하려면 사용 하 여 `TCHAR` 에 대 한 `char` 또는 `wchar_t`, `LPTSTR` 에 대 한 `char*` 또는 `wchar_t*`, 및 `LPCTSTR` 에 대 한 `const char*` 또는 `const wchar_t*`합니다. 이러한 MBCS 또는 유니코드 중 하나에 대 한 올바른 매핑을 확인 하십시오.

## <a name="see-also"></a>참고 항목

[문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
[문자열 조작](../c-runtime-library/string-manipulation-crt.md)  
