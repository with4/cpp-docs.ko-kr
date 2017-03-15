---
title: "유니코드 프로그래밍 요약 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "유니코드[C++], MFC 및 C 런타임 함수"
  - "유니코드[C++], 프로그래밍"
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# 유니코드 프로그래밍 요약
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

유니코드에 대한 MFC 및 C 런타임 지원을 활용하려면 다음을 수행해야 합니다.  
  
-   **\_UNICODE**를 정의합니다.  
  
     프로그램을 빌드하기 전에 **\_UNICODE** 기호를 정의합니다.  
  
-   진입점을 지정합니다.  
  
     프로젝트의 [속성 페이지](../ide/property-pages-visual-cpp.md) 대화 상자에 있는 링커 폴더의 **출력** 페이지에서 진입점 기호를 **wWinMainCRTStartup**으로 설정합니다.  
  
-   이식 가능한 런타임 함수와 형식을 사용합니다.  
  
     유니코드 문자열 처리에 적합한 C 런타임 함수를 사용합니다.  **wcs** 함수 패밀리를 사용해도 되지만 국가별 기능이 활성화되어 완전히 이식 가능한 **\_TCHAR** 매크로를 사용할 수도 있습니다.  이 매크로들은 모두 **\_tcs** 접두사가 붙으며 **str** 함수 패밀리의 해당 함수 대신 사용됩니다.  이러한 함수에 대한 자세한 내용은 Run\-Time Library Reference의 [국제화](../c-runtime-library/internationalization.md) 단원을 참조하십시오.  자세한 내용은 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)을 참조하십시오.  
  
     [유니코드 지원](../text/support-for-unicode.md)에서 설명한 이식 가능한 관련 데이터 형식과 **\_TCHAR**를 사용합니다.  
  
-   리터럴 문자열을 적절하게 처리합니다.  
  
     Visual C\+\+ 컴파일러는 다음 리터럴 문자열을 처리합니다.  
  
    ```  
    L"this is a literal string"  
    ```  
  
     이와 같이 코딩된 문자열이 유니코드 문자열을 의미하도록 해석합니다.  리터럴 문자에 대해 동일한 접두사를 사용할 수 있습니다.  **\_T** 매크로를 사용하여 리터럴 문자열을 일반적으로 코딩합니다. 이렇게 하면 문자열이 유니코드에서는 유니코드 문자열로 컴파일되고 유니코드가 아니면 ANSI 문자열\(MBCS 포함\)로 컴파일됩니다.  예를 들면, 다음과 같습니다.  
  
    ```  
    pWnd->SetWindowText( "Hello" );  
    ```  
  
     이 코드 대신에 다음 코드가 사용됩니다.  
  
    ```  
    pWnd->SetWindowText( _T("Hello") );  
    ```  
  
     **\_UNICODE**가 정의되어 있으면 **\_T**는 리터럴 문자열을 L 접두사가 있는 형식으로 변환하고, 그렇지 않으면 L 접두사가 없는 문자열로 변환합니다.  
  
    > [!TIP]
    >  **\_T** 매크로는 `_TEXT` 매크로와 동일합니다.  
  
-   문자열 길이를 함수로 전달할 때에는 주의해야 합니다.  
  
     일부 함수는 문자열의 문자 수를 요구하지만 바이트 수를 요구하는 함수도 있습니다.  예를 들어, **\_UNICODE**가 정의되어 있으면 `CArchive` 개체에 대한 다음 호출은 수행되지 않습니다. 여기서 `str`은 `CString`입니다.  
  
    ```  
    archive.Write( str, str.GetLength( ) );    // invalid  
    ```  
  
     각 문자는 2바이트이기 때문에 유니코드 응용 프로그램에서의 길이는 정확한 바이트 수가 아니라 문자 수를 나타냅니다.  대신 다음과 같이 사용해야 합니다.  
  
    ```  
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid  
    ```  
  
     위의 호출은 기록할 정확한 바이트 수를 지정합니다.  
  
     그러나 MFC 멤버 함수는 바이트를 대상으로 하기보다는 문자를 대상으로 하므로 다음과 같은 별도의 코딩을 하지 않아도 제대로 수행됩니다.  
  
    ```  
    pDC->TextOut( str, str.GetLength( ) );  
    ```  
  
     `CDC::TextOut`은 바이트 수가 아니라 문자 수를 가져옵니다.  
  
-   [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)를 사용하여 유니코드 파일을 엽니다.  
  
 요약하면 MFC와 런타임 라이브러리는 Windows 2000에서 유니코드 프로그래밍에 대해 다음을 지원합니다.  
  
-   데이터베이스 클래스 멤버 함수를 제외하고 `CString`을 포함한 모든 MFC 함수는 유니코드를 지원합니다.  `CString`은 유니코드\/ANSI 변환 기능도 제공합니다.  
  
-   런타임 라이브러리는 모든 문자열 처리 함수의 유니코드 버전을 제공합니다. 런타임 라이브러리는 또한 유니코드나 MBCS에 적합한 이식 가능 버전도 제공합니다.  이것이 **\_tcs** 매크로입니다.  
  
-   Tchar.h는 리터럴 문자열과 문자를 변환하기 위해 이식 가능한 데이터 형식과 **\_T** 매크로를 제공합니다.  자세한 내용은 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)을 참조하십시오.  
  
-   런타임 라이브러리는 **main**의 와이드 문자 버전을 제공합니다.  **wmain**을 사용하면 응용 프로그램이 유니코드를 인식하도록 만들 수 있습니다.  
  
## 참고 항목  
 [유니코드 지원](../text/support-for-unicode.md)