---
title: "MFC의 예외 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "비정상적인 프로그램 실행[C++]"
  - "보관 예외[C++]"
  - "어설션[C++], 예외 사용 시기"
  - "자동화[C++], 예외"
  - "C++ 예외 처리, 사용"
  - "C++ 예외 처리, MFC 응용 프로그램"
  - "C++ 예외 처리, 형식"
  - "클래스 라이브러리[C++], 예외 지원"
  - "DAO[C++], 예외"
  - "데이터베이스 예외[C++]"
  - "오류 처리[C++], 예외 및"
  - "오류[C++], 어설션에서 검색"
  - "예외 처리[C++], MFC"
  - "예외 매크로[C++]"
  - "예외[C++], MFC 매크로와 C++ 키워드 비교"
  - "함수 호출, 결과"
  - "키워드[C++], 예외 처리"
  - "매크로[C++], 예외 처리"
  - "매크로[C++], MFC 예외 매크로"
  - "메모리[C++], out-of-memory 예외"
  - "MFC[C++], 예외"
  - "ODBC 예외[C++]"
  - "OLE 예외[C++], MFC 예외 처리"
  - "out-of-memory 예외[C++]"
  - "미리 정의된 예외[C++]"
  - "지원되지 않는 서비스 요청"
  - "리소스 할당 예외"
  - "리소스[C++], 할당"
  - "serialization[C++], 예외"
  - "Windows[C++], 리소스 할당 예외"
ms.assetid: 0926627d-2ba7-44a6-babe-d851a4a2517c
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC의 예외 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC에서 사용할 수 있는 예외 처리 메커니즘에 대해 설명합니다.  두 가지 메커니즘을 사용할 수 있습니다.  
  
-   C\+\+ 예외는 MFC 3.0 버전과 그 이후 부터 사용가능 합니다.  
  
-   MFC 예외 매크로는 MFC 버전 1.0과 그 이후부터 사용할 수 있습니다.  
  
 MFC를 사용 하여 새 응용 프로그램을 작성 하는 경우 C\+\+ 메커니즘을 사용 해야 합니다.  이미 기존 응용 프로그램 메커니즘을 광범위 하게 사용 하는 경우 매크로 기반 메커니즘을 사용할 수 있습니다.  
  
 MFC 예외 매크로 대신 C\+\+ 예외를 사용 하여 기존 코드를 쉽게 변환할 수 있습니다.  그렇게 함으로서 프로그램 코드와 지침의 이점은 [예외: MFC 예외 매크로에서 변환](../mfc/exceptions-converting-from-mfc-exception-macros.md) 에 자세히 설명되어 있습니다.  
  
 MFC 예외 매크로 사용 하여 응용 프로그램을 미리 만들어 둔 경우, 존재하는 새 코드에서 C\+\+ 예외를 사용하는 경우 코드에서 이러한 매크로를 사용하여 계속할 수 있습니다.  [예외: 버전 3.0의 예외 매크로 변경 사항](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) 는 작업에 대한 지침을 제공합니다.  
  
> [!NOTE]
>  C\+\+ 예외 처리 코드를 사용 하려면 프로젝트의 C\/\+\+ 폴더에서 코드 생성 페이지에서 C\+\+ 예외 처리 가능을 선택하고 [속성 페이지](../ide/property-pages-visual-cpp.md) 대화 상자 또는 \/GX 컴파일러 옵션을 사용 합니다.  기본값은 \/GX –로 예외 처리를 사용 하지 못하도록 합니다.  
  
 이 단원에서는 다음 항목에 대해 설명합니다.  
  
-   [예외 사용 시기](#_core_when_to_use_exceptions)  
  
-   [MFC 예외 지원](#_core_mfc_exception_support)  
  
-   [예외에 대한 추가 정보](#_core_further_reading_about_exceptions)  
  
##  <a name="_core_when_to_use_exceptions"></a> 예외 사용 시기  
 프로그램 실행 중 함수를 호출할 때 세 가지 결과가 발생할 수 있습니다: 정상 실행, 잘못 된 실행 또는 비정상 실행 합니다.  각 범주에 대한 설명은 다음과 같습니다.  
  
-   일반 실행  
  
     함수는 정상적으로 실행하고 반환할 수 있습니다.  일부 함수 호출자는 함수의 결과를 나타내는 결과 코드를 반환 합니다.  결과 코드 함수에 대해 엄격 하게 정의 하고 함수의 결과 범위를 나타냅니다.  결과 코드가 성공 또는 실패 여부를 나타낼 수 또는 특정 유형의 정상적인 기대 범위 내에 있는 오류를 나타낼 수도 있습니다.  예를 들어, 파일 상태 함수는 파일이 존재 하지 않는 것을 나타내는 코드를 반환할 수 있습니다.  Note 결과 코드가 예상된 결과 중 하나를 나타내기 때문에, "오류 코드"라는 용어가 사용되지 않습니다.  
  
-   잘못 된 실행  
  
     호출자가 함수에 인수를 잘못 전달하거나 잘못 된 컨텍스트에서 함수를 호출 합니다.  이 것은 오류를 발생시킬 수 있으며, 프로그램 개발 중 어설션을 통해 감지 될 수 있어야 합니다. 어설션에 대한 자세한 내용은 [C\/C\+\+ 어설션](../Topic/C-C++%20Assertions.md)를 참조하십시오.  
  
-   일반적이지 않은 실행  
  
     비정상 실행은 조건이 함수의 결과에 영향을 미칠 수 있는 낮은 메모리 또는 I\/O 오류같은 프로그램의 컨트롤을 벗어나는 경우를 포함합니다.  비정상적인 상황을 파악 하고 예외를 throw 하여 처리 되어야 합니다.  
  
 예외를 사용 하는 비정상 실행에 특히 적합 합니다.  
  
##  <a name="_core_mfc_exception_support"></a> MFC 예외 지원  
 C\+\+ 예외를 직접적으로 사용하거나 MFC 예외 매크로를 사용하거나 프레임워크나 응용 프로그램에 의해 throw 되는 개체를 파생하는 [CException Class](../mfc/reference/cexception-class.md) 또는 `CException` 를 사용해야 합니다.  
  
 다음 표는 MFC에 의해 미리 정의된 예외를 보여줍니다.  
  
|예외 클래스|의미|  
|------------|--------|  
|[CMemoryException Class](../mfc/reference/cmemoryexception-class.md)|메모리가 부족합니다.|  
|[CFileException Class](../mfc/reference/cfileexception-class.md)|파일 예외|  
|[CArchiveException Class](../mfc/reference/carchiveexception-class.md)|보관\/직렬화 예외|  
|[CNotSupportedException Class](../mfc/reference/cnotsupportedexception-class.md)|지원 되지 않는 서비스에 대한 요청에 대한 응답|  
|[CResourceException Class](../mfc/reference/cresourceexception-class.md)|Windows 리소스 할당 예외|  
|[CDaoException Class](../mfc/reference/cdaoexception-class.md)|데이터베이스 예외 \(DAO 클래스\)|  
|[CDBException Class](../mfc/reference/cdbexception-class.md)|데이터베이스 예외 \(ODBC 클래스\)|  
|[COleException Class](../mfc/reference/coleexception-class.md)|OLE 예외|  
|[COleDispatchException Class](../mfc/reference/coledispatchexception-class.md)|디스패치 \(자동화\) 예외|  
|[CUserException Class](../mfc/reference/cuserexception-class.md)|메세지 박스를 사용하여 사용자를 바꾸는 예외는 일반 [CException Class](../mfc/reference/cexception-class.md) 를 throw합니다.|  
  
> [!NOTE]
>  MFC는 MFC 예외 매크로 및 C\+\+ 예외를 지원합니다.  [Structured Exception Handling](http://msdn.microsoft.com/library/windows/desktop/ms680657) 에 설명된 것처럼 MFC는 직접적으로 Windows NT 구조적 예외 처리\(SEH\)를 지원하지 않습니다.  
  
##  <a name="_core_further_reading_about_exceptions"></a> 예외에 대한 추가 정보  
 다음 문서는 예외 처리를 위한 MFC 라이브러리의 사용을 설명합니다.  
  
-   [예외: 예외 Catch 및 삭제](../mfc/exceptions-catching-and-deleting-exceptions.md)  
  
-   [예외: 예외 내용 검사](../mfc/exceptions-examining-exception-contents.md)  
  
-   [예외: 예외의 개체 해제](../mfc/exceptions-freeing-objects-in-exceptions.md)  
  
-   [예외: 자체 함수에서 예외 Throw](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)  
  
-   [예외: 데이터베이스 예외](../mfc/exceptions-database-exceptions.md)  
  
-   [예외: OLE 예외](../mfc/exceptions-ole-exceptions.md)  
  
 다음 문서는 MFC 예외 매크로를 C\+\+예외 키워드를 비교하고 코드에 적용하는 방법을 설명합니다.  
  
-   [예외: 버전 3.0의 예외 매크로 변경 사항](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)  
  
-   [예외: MFC 예외 매크로에서 변환](../mfc/exceptions-converting-from-mfc-exception-macros.md)  
  
-   [예외: MFC 매크로 및 C\+\+ 예외 사용](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)  
  
## 참고 항목  
 [C\+\+ 예외 처리](../cpp/cpp-exception-handling.md)   
 [How Do I: Create my Own Custom Exception Classes?](http://go.microsoft.com/fwlink/?LinkId=128045)