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
ms.openlocfilehash: 2a378d46c517dfc0fbb5857ad54bc31f4c34287b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859679"
---
# <a name="unicode-programming-summary"></a>유니코드 프로그래밍 요약
유니코드에 대 한 MFC 및 C 런타임 지원을 활용 하려면:  
  
-   정의 **_UNICODE**합니다.  
  
     기호를 정의 **_UNICODE** 프로그램을 빌드하기 전에 합니다.  
  
-   진입점을 지정 합니다.  
  
     에 **출력** 프로젝트의 링커 폴더의 페이지 [속성 페이지](../ide/property-pages-visual-cpp.md) 대화 상자에서 진입점 기호 설정 **wWinMainCRTStartup**합니다.  
  
-   이식 가능한 런타임 함수 및 형식을 사용 합니다.  
  
     유니코드 문자열 처리에 대 한 적절 한 C 런타임 함수를 사용 합니다. 사용할 수는 **wcs** 함수의 제품군 완전히 이식 가능한 (국가별 설정을 사용 하도록 설정)를 선호할 수 **_TCHAR** 매크로입니다. 이러한 매크로 모두와 앞에 **_tcs**;은 대체, 하나, 하나에 대 한는 **str** 함수 패밀리입니다. 이러한 함수에 자세히 설명는 [국제화](../c-runtime-library/internationalization.md) 의 섹션은 *런타임 라이브러리 참조*합니다. 자세한 내용은 참조 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)합니다.  
  
     사용 하 여 **_TCHAR** 에 설명 된 관련된 이식 가능한 데이터 형식 및 [유니코드에 대 한 지원을](../text/support-for-unicode.md)합니다.  
  
-   리터럴 문자열을 올바르게 처리 합니다.  
  
     Visual c + + 컴파일러는 리터럴 문자열을 해석 합니다.  
  
    ```  
    L"this is a literal string"  
    ```  
  
     유니코드 문자의 문자열을 의미 합니다. 리터럴 문자에 대 한 동일한 접두사를 사용할 수 있습니다. 사용 하 여는 **_T** 유니코드에서 유니코드 문자열 또는 유니코드 없는 ANSI 문자열 (MBCS 포함)로 컴파일됩니다 하므로 일반적으로, 리터럴 문자열을 코딩 하는 매크로입니다. 예를 들어 대신의:  
  
    ```  
    pWnd->SetWindowText( "Hello" );  
    ```  
  
     사용 합니다.  
  
    ```  
    pWnd->SetWindowText( _T("Hello") );  
    ```  
  
     와 **_UNICODE** 정의 **_T** 변환 하는 리터럴 문자열을 L 접두사 폼 그렇지 않으면 **_T** 에 L 접두사 없이 문자열을 변환 합니다.  
  
    > [!TIP]
    >  **_T** 매크로는 `_TEXT` 매크로입니다.  
  
-   주의 해야 함수에 문자열 길이 전달 합니다.  
  
     일부 함수는 문자열의 문자 수를 원합니다 다른 할 바이트 수입니다. 예를 들어 경우 **_UNICODE** 정의 된 다음에 대 한 호출을 `CArchive` 개체 작동 하지 것입니다 (`str` 는 `CString`):  
  
    ```  
    archive.Write( str, str.GetLength( ) );    // invalid  
    ```  
  
     유니코드 응용 프로그램에서 길이 하면 문자의 수 있지만 올바른 바이트 수가 아니라 각 문자는 2 바이트 때문에 있습니다. 대신, 사용 해야 합니다.  
  
    ```  
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid  
    ```  
  
     올바른 개수의 쓸 바이트 수를 지정 합니다.  
  
     그러나 MFC 멤버 함수는 바이트 지향적 이며, 아닌 문자 지향는 작동 이렇게 하지 않으면 별도 코딩 합니다.  
  
    ```  
    pDC->TextOut( str, str.GetLength( ) );  
    ```  
  
     `CDC::TextOut` 바이트 수가 아니라 문자의 수를 사용 합니다.  
  
-   사용 하 여 [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) 유니코드 파일을 열 수 있습니다.  
  
 요약 하면, MFC 및 런타임 라이브러리 유니코드 프로그래밍에 대 한 다음과 같은 지원을 제공 합니다.  
  
-   데이터베이스 클래스 멤버 함수를 제외한 모든 MFC 함수는 유니코드를 사용할 수를 포함 하 여 `CString`합니다. `CString` 또한 유니코드/ANSI 변환 함수를 제공합니다.  
  
-   런타임 라이브러리는 유니코드 버전의 모든 문자열 처리 함수를 제공합니다. (런타임 라이브러리 버전도 제공 휴대용 적합 한 유니코드 또는 MBCS에 대 한 합니다. 이들은 **_tcs** 매크로.)  
  
-   Tchar.h에서는 이식 가능한 데이터 형식을 제공 및 **_T** 매크로 대 한 문자열 리터럴 및 문자를 변환 합니다. 자세한 내용은 참조 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)합니다.  
  
-   런타임 라이브러리의 와이드 문자 버전을 제공 **주**합니다. 사용 하 여 **wmain** 유니코드 인식 응용 프로그램을 쉽게 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [유니코드 지원](../text/support-for-unicode.md)