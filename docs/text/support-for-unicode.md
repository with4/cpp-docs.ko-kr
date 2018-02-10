---
title: "유니코드에 대 한 지원 | Microsoft Docs"
ms.custom: 
ms.date: 1/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fde7674d30d84385eb1f94f42056a82bfaac99fe
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="support-for-unicode"></a>유니코드 지원

유니코드는 모든 문자 집합을 포함 하 여 표현할 수 없는 1 바이트 (즉, 대부분의)에 지원에 대 한 사양입니다. 국제 시장을 프로그래밍 하는 경우 유니코드를 사용 하는 것이 좋습니다 또는 [멀티 바이트 문자 집합](../text/support-for-multibyte-character-sets-mbcss.md) (MBCS) 하거나 스위치 변경을 통해 빌드할 수 있도록 프로그램을 코딩 합니다.

와이드 문자는 2바이트 다국어 문자 코드입니다. 단일 차원으로 유니코드 사양에 따라 수만 기술 기호 및 특수 게시 문자를 포함 하 여 전 세계의 현대식 컴퓨팅 환경에서 사용 되는 거의 모든 문자에 구성 된 문자를 나타낼 수 있습니다 하 여 문자를 인코딩할 u t F-16을 사용합니다. 와이드 문자 하나로 표현할 수 없는 문자는 유니코드 서로게이트 쌍 기능을 사용 하 여 유니코드 쌍으로 표현할 수 있습니다. 일반적으로 사용 거의 모든 문자는 u t F-16 단일 16 비트 와이드 문자로 표현, 때문에 국가별 문자 집합을 사용한 프로그래밍을 간소화 와이드 문자를 사용 하 여 합니다. 와이드 문자 (little endian)에 대 한 u t F-16LE를 사용 하 여 인코딩된 Windows 용 네이티브 문자 형식이 됩니다.

와이드 문자열은 `wchar_t[]` 배열로 표현되며 `wchar_t*` 포인터가 가리킵니다. 모든 ASCII 문자는 문자 앞에 접두사로 문자 L을 붙여 와이드 문자로 표현할 수 있습니다. 예를 들어 L'\ \0'은 종결 와이드 (16 비트) **NULL** 문자입니다. 마찬가지로, ASCII 문자열 리터럴은 ASCII 리터럴에 접두사로 문자 L을 붙여(예: L"Hello") 와이드 문자열 리터럴로 표현할 수 있습니다.

일반적으로 와이드 문자는 멀티바이트 문자보다 더 많은 메모리 공간을 차지하지만 프로세스 속도는 더 빠릅니다. 또한 1 개 로캘만 멀티 바이트 인코딩에서 한 번에 나타낼 수 있습니다, 그리고 전 세계에서 모든 문자 집합은 유니코드 표현으로 동시에 표시 됩니다.

MFC 프레임워크 전체에서는 유니코드를 사용할 수 있으며 MFC에서는 다음 테이블에 표시된 것처럼 이식 가능한 매크로를 사용하여 유니코드를 사용할 수 있습니다.

## <a name="portable-data-types-in-mfc"></a>MFC의 이식 가능한 데이터 형식

|이식 불가능한 데이터 형식|다음 매크로로 바뀜|
|-----------------------------|----------------------------|
|`char`, `wchar_t`|`_TCHAR`|
|`char*``LPSTR` (Win32 데이터 형식)`LPWSTR`|`LPTSTR`|
|`const char*``LPCSTR` (Win32 데이터 형식)`LPCWSTR`|`LPCTSTR`|

클래스 `CString` 사용 하 여 `_TCHAR` 의 기반으로 하 고 쉬운 변환을 위해 생성자 및 연산자를 제공 합니다. 유니코드에 대한 대부분의 문자열 작업은 Windows ANSI 문자 집합을 처리하는 데 사용되는 것과 동일한 논리를 사용하여 작성할 수 있습니다. 이러한 논리는 작업의 기본 단위가 8비트 바이트 대신 16비트 문자라는 점이 다릅니다. 멀티바이트 문자 집합을 사용하는 것과 달리 유니코드 문자를 별도의 2바이트인 것처럼 처리할 필요가 없습니다. 그러나 필요가 가능성을 와이드 문자의 서로게이트 쌍으로 표현 하는 단일 문자를 처리 합니다. 일반적으로 문자열의 길이 문자의 번호와 동일 하 게 좁거나 넓은 포함 되어 있는지 여부를 가정 하는 코드를 작성 하지 마십시오.

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [MFC의 유니코드 및 멀티 바이트 문자 집합 (MBCS) 지원 사용](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)

- [프로그램에서 유니코드 사용](../text/international-enabling.md)

- [유니코드와 MBCS 프로그램에서 사용](../text/internationalization-strategies.md)

- [유니코드를 사용 하 여 국제화 된 프로그램 만들기](../text/unicode-programming-summary.md)

- [유니코드의 이점에 알아보기](../text/benefits-of-character-set-portability.md)

- [와이드 문자 인수를 프로그램에 전달할 수 있도록 wmain 사용](../text/support-for-using-wmain.md)

- [유니코드 프로그래밍 요약 참조](../text/unicode-programming-summary.md)

- [바이트 너비 이식성에 대 한 제네릭 텍스트 매핑에 대 한 자세한 내용은](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>참고 항목

[텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)  
[wmain 사용 지원](../text/support-for-using-wmain.md)  
