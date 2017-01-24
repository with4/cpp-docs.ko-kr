---
title: "String Data Management | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unicode, string objects"
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# String Data Management
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 문자열 데이터를 관리 하는 여러 방법을 제공 합니다.  
  
-   [문자열 조작](../c-runtime-library/string-manipulation-crt.md)C 스타일의 null로 끝나는 문자열에 작업에 대 한  
  
-   Win32 API 함수를 문자열 관리  
  
-   MFC의 클래스 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)에서 제공 하는 유연 하 고 크기 조정 가능한 문자열 개체  
  
-   클래스 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md), 동일한 기능을 가진 MFC 독립적인 문자열 개체 제공`CString`  
  
 거의 모든 프로그램 문자열 데이터로 작업 합니다.  MFC의 `CString` 클래스는 유연한 문자열 처리에 대 한 최상의 솔루션입니다.  7.0 버전 부터는 `CString` 독립 MFC 또는 MFC 프로그램에서 사용할 수 있습니다.  런타임 라이브러리 및 `CString` 유니코드 나 MBCS 프로그래밍 에서처럼 멀티 바이트 \(와이드\) 문자가 포함 된 문자열을 지원 합니다.  
  
 문자열 조작에 관련 된 클래스 라이브러리를 제공 하는 일반적인 서비스에 설명 합니다.  이 문서에서 다루는 내용은 다음과 같습니다.  
  
-   [유니코드 및 MBCS 제공 이식성](#_core_unicode_and_mbcs_provide_portability)  
  
-   [Cstring 및 const char 포인터](#_core_cstrings_and_const_char_pointers)  
  
-   [CString 참조 횟수](#_core_cstring_reference_counting)  
  
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) 문자열 조작에 대 한 지원 클래스를 제공 합니다.  교체 하 고 일반적으로 C 런타임 라이브러리 문자열 패키지에서 제공 하는 기능을 확장 하기 위한 것입니다.  `CString` 멤버 함수 및 연산자를 단순한 문자열 처리, Basic에서 발견 된 것과 유사한 클래스를 제공 합니다.  클래스 생성자와 연산자 생성, 할당 및 비교에서는  **Cstring** 및 표준 C\+\+ 문자열 데이터 형식입니다.  때문에 `CString` 에서 파생 된 `CObject`를 사용 하면 `CString` 개체와는 별도로 대부분 Microsoft Foundation 클래스 라이브러리 \(MFC\)의.  
  
 `CString`개체에 따라 "값 의미 합니다." A `CString` 개체는 고유 값을 나타냅니다.  생각은 `CString` 실제 문자열로, 문자열 포인터로 없습니다.  
  
 A `CString` 개체는 다양 한 문자 시퀀스로 나타냅니다.  `CString`개체의 문자 배열로 생각할 수 있습니다.  
  
##  <a name="_core_unicode_and_mbcs_provide_portability"></a> 유니코드 및 MBCS 이식성을 제공합니다.  
 MFC 버전 3.0 이상에서 MFC를 비롯 하 여와 `CString`, 유니코드와 멀티 바이트 문자 집합 \(MBCS\)를 사용 합니다.  이 지원 쉽게 ANSI 또는 유니코드 문자를 구축할 수 있도록 휴대용 응용 프로그램을 작성할 수 있습니다.  이 이식성의 각 문자를 사용 하는 `CString` 개체의 형식입니다  **TCHAR**로 정의 되어 `wchar_t` 기호를 정의 하는 경우  **\_UNICODE** 응용 프로그램을 빌드할 때 또는 `char` 하지 않으면.  A `wchar_t` 문자는 16 비트입니다.  기호를 빌드하는 경우 MBCS 활성화  **\_MBCS** 정의 합니다.  MFC 자체 구성 된는  **\_mbcs가** \(NAFX 라이브러리\)에 대 한 기호 또는  **\_UNICODE** \(UAFX 라이브러리\)에 정의 된 기호.  
  
> [!NOTE]
>  `CString` 이 예제는 문서 리터럴 문자열 형식이 유니코드 이식성에 대 한 문자열 표시를 함께 고 사용 하는  **\_T** 폼에 리터럴 문자열을 변환 하는 매크로:  
  
 `L"literal string"`  
  
> [!NOTE]
>  컴파일러 유니코드 문자열로 처리 합니다.  예를 들어, 다음 코드에서  
  
 [!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/CPP/string-data-management_1.cpp)]  
  
> [!NOTE]
>  경우에 유니코드 문자열로 변환 됩니다  **\_UNICODE** 정의 되어 있거나 그렇지 않은 경우로 ANSI 문자열입니다.  자세한 내용은 [유니코드 및 MBCS\(멀티바이트 문자 집합\) 지원](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
 A `CString` 개체를 저장할 수 있는  **INT\_MAX** \(2147483647\) 문자.  **TCHAR** 데이터 형식 내의 개별 문자를 설정 하는 데 사용 된 `CString` 개체입니다.  문자 배열과 달리는 `CString` 클래스에 내장 메모리 할당 기능이 있습니다.  그러면 `CString` 필요에 따라 자동으로 증가 하도록 개체 \(즉, 성장에 대 한 걱정할 필요가 없습니다를 `CString` 긴 문자열에 맞게 개체\).  
  
##  <a name="_core_cstrings_and_const_char_pointers"></a> Cstring 및 const char 포인터  
 A `CString` 개체 수도 있습니다 역할 같은 C 스타일 문자열 리터럴 \(은 `PCXSTR`, 것 같은  **const char \*** 에서 유니코드에 없는 경우\).  [CSimpleStringT::operator PCXSTR](../Topic/CSimpleStringT::operator%20PCXSTR.md) 변환 연산자 수 `CString` 자유롭게 문자 포인터 함수 호출에 대 한 대체 될 개체입니다.  **CString \(LPCWSTR**`pszSrc`**\)** 생성자에 대 한 대체 문자 포인터 있습니다 `CString` 개체입니다.  
  
 가 시도 된 `CString` 개체입니다.  두 하는 경우 `CString` 포함 된 개체를 `Chicago`예를 들어, 문자에서 `Chicago` 두 곳에 저장 됩니다.  \(에 의존 해야 하므로이 MFC의 다음 버전의 수 있습니다.\)  
  
> [!NOTE]
>  사용은 [CSimpleStringT::GetBuffer](../Topic/CSimpleStringT::GetBuffer.md) 및 [CSimpleStringT::ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md) 멤버 함수에 직접 액세스 하는 경우는 `CString` 으로 문자는 비상수 포인터.  
  
> [!NOTE]
>  사용의 [CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md) 및 [CStringT::SetSysString](../Topic/CStringT::SetSysString.md) 멤버 함수를 할당 하 여 설정 `BSTR` 자동화 \(이전의 OLE 자동화\)에 사용 되는 개체입니다.  
  
> [!NOTE]
>  할당 가능한 경우 `CString` 프레임 대신 힙의 개체입니다.  메모리에 저장 하 고 전달 하는 매개 변수를 단순화 합니다.  
  
 `CString` 클래스는 Mfc 라이브러리 컬렉션 클래스로 하지만 구현 되지 않았습니다 `CString` 개체 확실히 저장할 수로 컬렉션의 요소입니다.  
  
##  <a name="_core_cstring_reference_counting"></a> CString 참조 횟수  
 MFC 버전 4.0 기준으로 하면 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) 개체 복사, MFC 데이터를 복사 하지 않고 참조 횟수를 증가 시킵니다.  이 값과 반환 매개 변수로 전달 됩니다. `CString` 개체에서 값을 보다 효율적으로 합니다.  이러한 작업의 복사 생성자를 호출 한 번 이상 발생 합니다.  이러한 일반적인 작업의 오버 헤드가 줄어들고 있습니다 사용 하 여 참조 횟수를 증가 `CString` 방식이 적합 합니다.  
  
 각 복사가 소멸 될 때 원래 개체의 참조 횟수가 감소 됩니다.  원래 `CString` 개체의 참조 횟수가 0으로 줄어들 때까지 않습니다 파괴 합니다.  
  
 사용할 수는 `CString` 멤버 함수 [CSimpleStringT::LockBuffer](../Topic/CSimpleStringT::LockBuffer.md) 및 [CSimpleStringT::UnlockBuffer](../Topic/CSimpleStringT::UnlockBuffer.md) 참조 횟수를 설정 하거나 해제 합니다.  
  
## 참고 항목  
 [일반 MFC 항목](../mfc/general-mfc-topics.md)