---
title: "Using CString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CString class (Visual C++)"
  - "CString objects, C++ string manipulation"
  - "CString objects, reference counting"
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Using CString
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 섹션의 항목에서는 `CString`을 사용한 프로그래밍 방법에 대해 설명합니다.  `CString` 클래스에 대한 참조 설명서는 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 설명서를 참조하세요.  
  
 `CString`을 사용하려면 `atlstr.h` 헤더를 포함합니다.  
  
 `CString`, `CStringA` 및 `CStringW` 클래스는 지원하는 문자 데이터 유형을 기반으로 하는 특수화된 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 클래스 템플릿입니다.  
  
 `CStringW` 개체는 `wchar_t` 형식을 포함하며 유니코드 문자열을 지원합니다.  `CStringA` 개체는 `char` 형식을 포함하며 싱글바이트 및 멀티바이트\(MBCS\) 문자열을 지원합니다.  `CString` 개체는 컴파일 시간에 정의되는 기호\(`MBCS` 기호 또는 `UNICODE` 기호\)에 따라 `char` 형식 또는 `wchar_t` 형식을 지원합니다.  
  
 `CString` 개체는 `CStringData` 개체에 문자 데이터를 보관합니다.  `CString`은 `null`로 종료되는 C 스타일 문자열을 허용하지만 저장된 문자 데이터에 `null` 문자를 보존하지는 않습니다.  대신 `CString`은 문자열 길이를 추적합니다.  `CString`은 C 스타일 문자열을 내보낼 때 null 종결자를 제공합니다.  `CString`에 `null`을 삽입할 수는 있지만 이렇게 하면 예기치 않은 결과가 발생할 수 있습니다.  
  
 `CAtlString`, `CAtlStringA` 및 `CAtlStringW` 문자열 클래스 집합은 MFC 라이브러리에 연결하지 않고 사용할 수 있습니다\(CRT 지원 포함\/미포함\).  
  
 `CString`은 네이티브 프로젝트에 사용됩니다.  관리 코드\(C\+\+\/CLI\) 프로젝트에는 `System::String`을 사용합니다.  
  
 `CString`, `CStringA` 또는 `CStringW`에서 현재 제공하는 것보다 많은 기능을 추가하려면 추가 기능이 포함된 `CStringT`를 만들어야 합니다.  
  
 다음 코드는 `CString`을 만들어 표준 출력으로 인쇄하는 방법을 보여줍니다.  
  
```cpp  
#include <atlstr.h>  
  
int main() {  
    CString aCString = CString(_T("A string"));  
    _tprintf(_T("%s"), (LPCTSTR) aCString);  
}  
```  
  
## 단원 내용  
 [기본 CString 작업](../atl-mfc-shared/basic-cstring-operations.md)  
 C 리터럴 문자열에서 개체를 만들고, `CString`의 개별 문자에 액세스하고, 두 개체를 연결하고, `CString` 개체를 비교하는 작업을 포함한 기본 `CString` 작업을 설명합니다.  
  
 [문자열 데이터 관리](../atl-mfc-shared/string-data-management.md)  
 `CString`에서 유니코드 및 MBCS를 사용하는 방법을 설명합니다.  
  
 [CString 의미 체계](../atl-mfc-shared/cstring-semantics.md)  
 `CString` 개체를 사용하는 방법을 설명합니다.  
  
 [C 스타일 문자열 관련 CString 작업](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)  
 C 스타일의 null로 종료되는 문자열과 같은 `CString` 개체의 콘텐츠를 조작하는 방법을 설명합니다.  
  
 [BSTR에 대해 메모리 할당 및 해제](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)  
 `BSTR` 및 COM 개체에 대해 메모리를 사용하는 방법을 설명합니다.  
  
 [CString 예외 정리](../atl-mfc-shared/cstring-exception-cleanup.md)  
 MFC 3.0 이상에서는 명시적 정리가 더 이상 필요하지 않은 이유에 대해 설명합니다.  
  
 [CString 인수 전달](../atl-mfc-shared/cstring-argument-passing.md)  
 CString 개체를 함수에 전달하고 함수에서 `CString` 개체를 반환하는 방법을 설명합니다.  
  
 [유니코드 및 MBCS\(멀티바이트 문자 집합\) 지원](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)  
 유니코드 및 MBCS가 지원되도록 MFC를 설정하는 방법을 설명합니다.  
  
## 참조  
 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)  
 `CStringT` 클래스에 대한 참조 정보를 제공합니다.  
  
 [CSimpleStringT Class](../atl-mfc-shared/reference/csimplestringt-class.md)  
 `CSimpleStringT` 클래스에 대한 참조 정보를 제공합니다.  
  
## 관련 단원  
 [문자열](../atl-mfc-shared/strings-atl-mfc.md)  
 문자열 데이터를 관리하는 여러 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [템플릿 클래스 인스턴스화](../Topic/Class%20Template%20Instantiation.md)  
 `CString`은 클래스 템플릿의 특수화된 인스턴스인 `CStringT`를 기반으로 하는 `typedef`입니다.