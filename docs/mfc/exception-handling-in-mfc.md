---
title: "MFC의 예외 처리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DAO [MFC], exceptions
- assertions [MFC], When to use exceptions
- exception handling [MFC], MFC
- resource allocation exception
- resources [MFC], allocating
- keywords [MFC], exception handling
- errors [MFC], detected by assertions
- ODBC exceptions [MFC]
- serialization [MFC], exceptions
- Automation [MFC], exceptions
- exception macros [MFC]
- predefined exceptions [MFC]
- C++ exception handling [MFC], enabling
- C++ exception handling [MFC], MFC applications
- requests for unsupported services [MFC]
- database exceptions [MFC]
- archive exceptions [MFC]
- MFC, exceptions
- C++ exception handling [MFC], types of
- macros [MFC], exception handling
- abnormal program execution [MFC]
- OLE exceptions [MFC], MFC exception handling
- error handling [MFC], exceptions and
- class libraries [MFC], exception support
- exceptions [MFC], MFC macros vs. C++ keywords
- memory [MFC], out-of-memory exceptions
- Windows [MFC], resource allocation exceptions
- macros [MFC], MFC exception macros
- function calls [MFC], results
- out-of-memory exceptions [MFC]
ms.assetid: 0926627d-2ba7-44a6-babe-d851a4a2517c
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 544130f27fb01d0d29652087351c8a5bbc5bd5c7
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="exception-handling-in-mfc"></a>MFC의 예외 처리
이 문서에서는 MFC에서 제공 되는 예외 처리 메커니즘에 설명 합니다. 두 가지 메커니즘을 사용할 수 있습니다.  
  
-   MFC 버전 3.0에서에서 사용할 수 있는 이상 c + + 예외  
  
-   MFC 버전 1.0에서에서 사용할 수 있는 이상 MFC 예외 매크로  
  
 MFC를 사용 하 여 새 응용 프로그램을 작성 하는 경우 c + + 메커니즘을 사용 해야 합니다. 기존 응용 프로그램이 이미이 메커니즘을 광범위 하 게 사용 하는 경우 매크로 기반으로 하는 메커니즘을 사용할 수 있습니다.  
  
 MFC 예외 매크로 대신 c + + 예외를 사용 하도록 기존 코드를 쉽게 변환할 수 있습니다. 코드와 작업에 대 한 지침을 변환의 이점 문서에 설명 된 [예외: MFC 예외 매크로에서 변환](../mfc/exceptions-converting-from-mfc-exception-macros.md)합니다.  
  
 MFC 예외 매크로 사용 하 여 응용 프로그램을 미리 만들어 둔 경우 기존 코드에서 이러한 매크로 사용 하 여 새 코드에서 c + + 예외를 사용 하는 동안 계속 수 있습니다. 문서 [예외: 버전 3.0의 예외 매크로 변경](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) 이렇게 하는 것에 대 한 지침을 제공 합니다.  
  
> [!NOTE]
>  C + +에서에서 예외 처리 코드를 사용 하려면 프로젝트의 C/c + + 폴더에 코드 생성 페이지에서 c + + 예외 처리 가능 선택 [속성 페이지](../ide/property-pages-visual-cpp.md) 대화 상자나 /GX 컴파일러 옵션을 사용 합니다. 기본값은 /GX-예외 처리를 사용 하지 않도록 설정 합니다.  
  
 이 문서에서는 다음 항목을 다룹니다.  
  
-   [예외를 사용 하는 경우](#_core_when_to_use_exceptions)  
  
-   [MFC 예외 지원](#_core_mfc_exception_support)  
  
-   [예외에 대 한 추가 정보](#_core_further_reading_about_exceptions)  
  
##  <a name="_core_when_to_use_exceptions"></a>예외를 사용 하는 경우  
 결과의 세 가지 범주는 프로그램 실행 시 함수를 호출 하는 경우에 발생할 수 있습니다: 정상적인 실행, 잘못 된 실행 또는 비정상 실행 합니다. 각 범주에 대 한 설명은 다음과 같습니다.  
  
-   정상적인 실행  
  
     함수가는 정상적으로 실행 하 고 반환할 수 있습니다. 일부 함수는 함수의 결과 나타내는 호출자에 게 결과 코드를 반환 합니다. 수 있는 결과 코드가 함수에 대해 엄격 하 게 정의 하 고 함수의 결과 범위를 나타냅니다. 결과 코드는 성공 또는 실패를 나타낼 수 있습니다 또는 특정 유형의 기대 범위 내에 있는 오류를 나타낼 수도 있습니다. 예를 들어 파일 상태 함수 파일이 존재 하지 않는 나타내는 코드를 반환할 수 있습니다. 결과 코드는 예상 된 여러 결과 중 하나를 나타내기 때문에 "오류 코드" 라는 용어는 사용 되지 않음을 note 합니다.  
  
-   잘못 된 실행  
  
     호출자에 게 잘못이 함수에 인수를 전달 하거나 잘못 된 컨텍스트에서 함수를 호출 합니다. 이 경우에는 오류를 발생 하 고 프로그램을 개발 하는 동안 어설션에 의해 검색 됩니다. (어설션에 대 한 자세한 내용은 참조 하십시오. [C/c + + 어설션](/visualstudio/debugger/c-cpp-assertions).)  
  
-   비정상 실행  
  
     I/O 오류 또는 메모리 부족 같은 프로그램의 제어를 벗어나는 조건은 함수의 결과 영향 있는 상황을 포함 하는 비정상 실행 합니다. Catch 및 예외를 throw 하 여 비정상적인 상황을 처리 되어야 합니다.  
  
 예외를 사용 하는 것은 비정상 실행 특히 적합 합니다.  
  
##  <a name="_core_mfc_exception_support"></a>MFC 예외 지원  
 사용할 것인지를 c + + 예외를 직접 사용 하거나 MFC 예외 매크로 사용 하 여 [CException 클래스](../mfc/reference/cexception-class.md) 또는 `CException`-응용 프로그램 또는 프레임 워크에 의해 throw 될 수 있는 개체를 파생 합니다.  
  
 다음 표에서 MFC에서 제공 하는 미리 정의 된 예외를 보여 줍니다.  
  
|Exception 클래스|의미|  
|---------------------|-------------|  
|[CMemoryException 클래스](../mfc/reference/cmemoryexception-class.md)|메모리 부족|  
|[CFileException 클래스](../mfc/reference/cfileexception-class.md)|파일 예외|  
|[CArchiveException 클래스](../mfc/reference/carchiveexception-class.md)|보관/Serialization 예외|  
|[CNotSupportedException 클래스](../mfc/reference/cnotsupportedexception-class.md)|지원 되지 않는 서비스에 대 한 요청에 대 한 응답|  
|[CResourceException 클래스](../mfc/reference/cresourceexception-class.md)|Windows 리소스 할당 예외|  
|[CDaoException 클래스](../mfc/reference/cdaoexception-class.md)|데이터베이스 예외 (DAO 클래스)|  
|[CDBException 클래스](../mfc/reference/cdbexception-class.md)|데이터베이스 예외 (ODBC 클래스)|  
|[COleException 클래스](../mfc/reference/coleexception-class.md)|OLE 예외|  
|[COleDispatchException 클래스](../mfc/reference/coledispatchexception-class.md)|디스패치 (자동화) 예외|  
|[CUserException 클래스](../mfc/reference/cuserexception-class.md)|메시지 상자를 사용 하 여 경고는 예외를 throw 합니다. 제네릭 [CException 클래스](../mfc/reference/cexception-class.md)|  
  
> [!NOTE]
>  MFC는 c + + 예외와 MFC 예외 매크로 모두 지원합니다. MFC에서 직접 지원 하지 Windows NT 구조적 예외 처리기 (SEH)에 설명 된 대로 [구조적 예외 처리](http://msdn.microsoft.com/library/windows/desktop/ms680657)합니다.  
  
##  <a name="_core_further_reading_about_exceptions"></a>예외에 대 한 추가 정보  
 MFC 라이브러리를 사용 하 여 예외 처리를 위해 다음 문서에서 설명 합니다.  
  
-   [예외: 예외 Catch 및 삭제](../mfc/exceptions-catching-and-deleting-exceptions.md)  
  
-   [예외: 예외 내용 검사](../mfc/exceptions-examining-exception-contents.md)  
  
-   [예외: 예외의 개체 해제](../mfc/exceptions-freeing-objects-in-exceptions.md)  
  
-   [예외: 자체 함수에서 예외 Throw](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)  
  
-   [예외: 데이터베이스 예외](../mfc/exceptions-database-exceptions.md)  
  
-   [예외: OLE 예외](../mfc/exceptions-ole-exceptions.md)  
  
 다음 문서는 c + + 예외 키워드로 MFC 예외 매크로 비교 하 고 코드를 조정 하는 방법에 대해 설명 합니다.  
  
-   [예외: 버전 3.0의 예외 매크로 변경 사항](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)  
  
-   [예외: MFC 예외 매크로에서 변환](../mfc/exceptions-converting-from-mfc-exception-macros.md)  
  
-   [예외: MFC 매크로 및 C++ 예외 사용](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)  
  
## <a name="see-also"></a>참고 항목  
 [C + + 예외 처리](../cpp/cpp-exception-handling.md)   
 [I: 나만의 사용자 지정 예외 클래스를 만드는 방법](http://go.microsoft.com/fwlink/p/?linkid=128045)

