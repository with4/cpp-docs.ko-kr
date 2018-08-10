---
title: 유니코드 프로그래밍 요약 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Unicode [C++], programming with
- Unicode [C++], MFC and C run-time functions
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 65db0889b36cafa4b3942b7834229d1a7d9f5783
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010362"
---
# <a name="unicode-programming-summary"></a>유니코드 프로그래밍 요약
유니코드에 대 한 MFC 및 C 런타임 지원을 활용 하려면를 지정 해야 합니다.  
  
-   정의 `_UNICODE`합니다.  
  
     기호를 정의 `_UNICODE` 프로그램을 빌드하기 전에 합니다.  
  
-   진입점을 지정 합니다.  
  
     에 **출력** 페이지의 **링커** 프로젝트의 폴더 [속성 페이지](../ide/property-pages-visual-cpp.md) 대화 상자에서를 **진입점** 기호`wWinMainCRTStartup`.  
  
-   이식 가능한 런타임 함수 및 형식을 사용 합니다.  
  
     유니코드 문자열 처리에 대 한 적절 한 C 런타임 함수를 사용 합니다. 사용할 수는 `wcs` 있지만 함수 제품군 (국가별 설정을 사용 하도록 설정)를 완전히 이식 가능한 것을 선호할 수 `_TCHAR` 매크로입니다. 이러한 매크로 모두 사용 하 여 앞에 `_tcs`; 이러한 대체를을 하나에 대 한는 `str` 함수 패밀리입니다. 이러한 함수에서 자세히 설명 되어 있습니다 합니다 [국제화](../c-runtime-library/internationalization.md) 섹션을 *런타임 라이브러리 참조*합니다. 자세한 내용은 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)합니다.  
  
     사용 하 여 `_TCHAR` 에 설명 된 관련된 이식 가능한 데이터 형식을 [유니코드 지원](../text/support-for-unicode.md)합니다.  
  
-   리터럴 문자열을 올바르게 처리 합니다.  
  
     Visual c + + 컴파일러는 리터럴 문자열을 해석 합니다.  
  
    ```  
    L"this is a literal string"  
    ```  
  
     유니코드 문자의 문자열을 의미 합니다. 리터럴 문자에 대 한 동일한 접두사를 사용할 수 있습니다. 사용 하 여는 `_T` 을 유니코드에서 유니코드 문자열 또는 유니코드 없는 ANSI 문자열 (MBCS 포함)으로 컴파일됩니다 하므로 일반적으로 리터럴 문자열을 코딩 하는 매크로입니다. 예를 들어, 대신입니다.  
  
    ```  
    pWnd->SetWindowText( "Hello" );  
    ```  
  
     사용:  
  
    ```  
    pWnd->SetWindowText( _T("Hello") );  
    ```  
  
     사용 하 여 `_UNICODE` 정의 `_T` L 접두사 폼; 리터럴 문자열을 변환이 고, 그렇지 `_T` L 접두사 없이 문자열을 변환 합니다.  
  
    > [!TIP]
    >  합니다 `_T` 매크로 동일 합니다 `_TEXT` 매크로입니다.  
  
-   주의 함수에 문자열 길이 전달 합니다.  
  
     일부 함수는 문자열의 문자 수를 원합니다 다른 사용자가 원하는 바이트 수입니다. 예를 들어 경우 `_UNICODE` 정의 된 다음 호출을 `CArchive` 개체는 작동 하지 않습니다 (`str` 는 `CString`):  
  
    ```  
    archive.Write( str, str.GetLength( ) );    // invalid  
    ```  
  
     유니코드 응용 프로그램에서 길이 사용 하면 문자의 수 있지만 올바른 바이트 수가 아니라 각 문자가 2 바이트 이므로 합니다. 대신, 사용 해야 합니다.  
  
    ```  
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid  
    ```  
  
     쓸 바이트의 올바른 수를 지정 합니다.  
  
     그러나 MFC 멤버 함수는 바이트 지향적 이며, 하는 것이 아니라 문자 지향는 작동 이렇게 하지 않으면 추가 코딩 합니다.  
  
    ```  
    pDC->TextOut( str, str.GetLength( ) );  
    ```  
  
     `CDC::TextOut` 된 수의 문자, 바이트 수가 아니라를 사용합니다.  
  
-   사용 하 여 [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) 유니코드 파일을 열 수 있습니다.  
  
 요약 하자면, MFC 및 런타임 라이브러리 유니코드 프로그래밍에 대 한 다음 지원을 제공 합니다.  
  
-   데이터베이스 클래스 멤버 함수를 제외 하 고 모든 MFC 함수는 유니코드-를 포함 하 여 `CString`입니다. `CString` 또한 유니코드/ANSI 변환 함수를 제공합니다.  
  
-   런타임 라이브러리는 유니코드 버전의 모든 문자열 처리 함수를 제공합니다. (런타임 라이브러리 버전도 제공 휴대용 적합 한 MBCS 또는 유니코드에 대 한 합니다. 이들은 `_tcs` 매크로입니다.)  
  
-   Tchar.h에서는 이식 가능한 데이터 형식을 제공 하며 `_T` 매크로 리터럴 문자열 및 문자를 변환 합니다. 자세한 내용은 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)합니다.  
  
-   런타임 라이브러리의 와이드 문자 버전을 제공 `main`합니다. 사용 하 여 `wmain` 유니코드 인식 응용 프로그램을 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [유니코드 지원](../text/support-for-unicode.md)