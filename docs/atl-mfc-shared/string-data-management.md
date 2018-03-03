---
title: "데이터 관리 문자열 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Unicode, string objects
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad7a17b1b34375fcb45019bcaf8878757288a290
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="string-data-management"></a>문자열 데이터 관리
Visual c + +에서는 문자열 데이터를 관리 하는 여러 방법을 제공 합니다.  
  
-   [문자열 조작](../c-runtime-library/string-manipulation-crt.md) C 스타일 null로 끝나는 문자열 작업에 대 한  
  
-   문자열을 관리 하기 위한 Win32 API 함수  
  
-   MFC의 클래스 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)를 유연 하 고 크기 조정 가능한 문자열 개체를 제공 하는  
  
-   클래스 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md), MFC에 독립적인 문자열 개체와 동일한 기능을 제공 하는`CString`  
  
 거의 모든 프로그램이 문자열 데이터를 사용 합니다. MFC의 `CString` 클래스는 유연한 문자열 처리에 적합 한 솔루션입니다. 버전 7.0부터 `CString` 프로그램 MFC / MFC에 독립적인에에서 사용할 수 있습니다. 런타임 라이브러리 및 `CString` 와 같이 유니코드 또는 MBCS 프로그래밍 멀티 바이트 (전체) 문자를 포함 하는 문자열을 지원 합니다.  
  
 이 문서는 일반적인 서비스 클래스 라이브러리는 관련 문자열 조작에 설명 합니다. 이 문서에서 다루는 항목은 다음과 같습니다.  
  
-   [유니코드 및 MBCS 제공 이식성](#_core_unicode_and_mbcs_provide_portability)  
  
-   [Cstring 및 const char 포인터](#_core_cstrings_and_const_char_pointers)  
  
-   [CString 참조 횟수](#_core_cstring_reference_counting)  
  
 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md) 클래스는 문자열 조작에 대 한 지원을 제공 합니다. 대체 하 고 일반적으로 C 런타임 라이브러리 문자열 패키지에서 제공 하는 기능을 확장 하는 것이 됩니다. `CString` 클래스 멤버 함수 및 간소화 된 문자열을 처리 하기 위한, basic에서 있는 것과 비슷한 연산자를 제공 합니다. 클래스는 생성자와 연산자를 생성 하 고 할당, 비교 **는 Cstring** 및 표준 c + + 문자열 데이터 형식입니다. 때문에 `CString` 에서 파생 되지 않은 `CObject`를 사용할 수 있습니다 `CString` 대부분 Microsoft Foundation 클래스 라이브러리 (MFC)의 관계 없이 개체입니다.  
  
 `CString`개체는 준수 "의미 체계를 값입니다." A `CString` 개체는 고유한 값을 나타냅니다. 에 참여 한 `CString` 문자열에 대 한 포인터 아닌 실제 문자열으로 합니다.  
  
 A `CString` 개체의 다양 한 수의 문자 시퀀스를 나타냅니다. `CString`개체의 문자 배열로 생각할 수 있습니다.  
  
##  <a name="_core_unicode_and_mbcs_provide_portability"></a>유니코드 및 MBCS 이식성을 제공합니다.  
 MFC 버전 3.0 이상 MFC를 비롯 한와 `CString`, 유니코드 및 멀티 바이트 문자 집합 (MBCS) 모두에 대해 사용 하도록 설정 합니다. 이 지원을 통해 쉽게 ANSI 또는 유니코드 문자에 대해 만들 수 있다는 휴대용 응용 프로그램을 작성할 수 있습니다. 이 이식성의 각 문자를 사용 하도록 설정 하려면 한 `CString` 형식의 개체는 **TCHAR**, 것으로 정의 된 `wchar_t` 기호를 정의 하는 경우 **_UNICODE** 응용 프로그램을 빌드할 때 또는 `char` 그렇지 않은 경우. A `wchar_t` 문자는 너비가 16 비트입니다. MBCS는 기호를 사용 하 여 빌드하는 경우 사용할 수 **_MBCS** 정의 합니다. MFC 자체가 중 하나를 사용 하 여 빌드는 **_MBCS** (NAFX 라이브러리)에 대 한 기호 또는 **_UNICODE** (UAFX 라이브러리)에 대 한 기호를 정의 합니다.  
  
> [!NOTE]
>  `CString` 이 예제 및 문서를 함께 제공 된 리터럴 문자열이 유니코드 이식성에 대 한 올바르게 서식 지정 문자열 표시, 사용 하는 **_T** 폼에 리터럴 문자열 변환 매크로:  
  
 `L"literal string"`  
  
> [!NOTE]
>  컴파일러는 유니코드 문자열로 취급 합니다. 예를 들어, 다음 코드는  
  
 [!code-cpp[NVC_ATLMFC_Utilities#187](../atl-mfc-shared/codesnippet/cpp/string-data-management_1.cpp)]  
  
> [!NOTE]
>  경우에 유니코드 문자열로 변환 됩니다 **_UNICODE** 정의 된 또는 ANSI로 그렇지 않은 경우 문자열 상수입니다. 자세한 내용은 문서 참조 [유니코드 및 멀티 바이트 문자 집합 (MBCS) 지원](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)합니다.  
  
 A `CString` 개체를 저장할 수 **INT_MAX** (2147483647) 자인 합니다. **TCHAR** 가져오기 또는 설정 내 개별 문자 데이터 형식이 사용 됩니다는 `CString` 개체입니다. 문자 배열 달리는 `CString` 클래스에 기본 제공 메모리 할당 기능이 있습니다. 이 통해 `CString` 필요에 따라 자동으로 증가 하는 개체 (증가에 대해 걱정할 필요가 없습니다 즉, 한 `CString` 더 긴 문자열에 맞게 개체).  
  
##  <a name="_core_cstrings_and_const_char_pointers"></a>Cstring 및 const char 포인터  
 A `CString` 도 개체 리터럴 C 스타일 문자열 처럼 작동할 수 (한 `PCXSTR`와 동일한 **const char\***  유니코드에 포함 되지 않은 경우). [CSimpleStringT::operator PCXSTR](../atl-mfc-shared/reference/csimplestringt-class.md#operator_pcxstr) 변환 연산자를 사용 하면 `CString` 자유롭게 함수 호출에서 문자 포인터에 대 한 대체 되는 개체입니다. **CString (lpcwstr을 사용** `pszSrc` **)** 생성자를 대체할 문자 포인터를 사용 하면 `CString` 개체입니다.  
  
 접기 하려고 시도 하지 `CString` 개체입니다. 두 개의 만들면 `CString` 포함 된 개체 `Chicago`, 예를 들어의 문자를 `Chicago` 두 위치에 저장 됩니다. (이 아닐 수, MFC의 이후 버전의 경우에 있으므로 신뢰 하지 않아야 합니다.)  
  
> [!NOTE]
>  사용 하 여는 [CSimpleStringT::GetBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 및 [CSimpleStringT::ReleaseBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) 에 직접 액세스 해야 하는 경우 멤버 함수는 `CString` 문자로 비상수 포인터로 합니다.  
  
> [!NOTE]
>  사용 하 여는 [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring) 및 [CStringT::SetSysString](../atl-mfc-shared/reference/cstringt-class.md#setsysstring) 를 할당 하는 멤버 함수 `BSTR` 자동화 (이전의 OLE 자동화)에서 사용 되는 개체입니다.  
  
> [!NOTE]
>  가능한 경우, 할당할 `CString` 프레임에 대신 힙에 개체입니다. 이 메모리를 절약 하 고 매개 변수 전달를 간소화 합니다.  
  
 `CString` 클래스로 구현 되지 않습니다 Microsoft Foundation Class 라이브러리 컬렉션 클래스, 하지만 `CString` 개체 컬렉션에 요소로 확실히 저장할 수 있습니다.  
  
##  <a name="_core_cstring_reference_counting"></a>CString 참조 횟수  
 MFC 버전 4.0 기준으로 때 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md) 개체를 복사 하 되, MFC 데이터를 복사 하지 않고 참조 횟수를 증가 시킵니다. 이렇게 하면 매개 변수 값을 반환 하 여 전달 `CString` 값 보다 효율적으로 개체입니다. 이러한 작업으로 인해 복사 생성자가 한 번 이상 호출 됩니다. 이러한 일반적인 작업에 대 한 오버 헤드가 감소 하 고 사용 하 여 참조 횟수를 늘리면 `CString` 방식이 있습니다.  
  
 각 복사본 제거 되는 원래 개체의 참조 횟수는 감소 합니다. 원래 `CString` 개체 참조 개수가 0으로 감소 될 때까지 제거 되지 않습니다.  
  
 사용할 수는 `CString` 멤버 함수 [CSimpleStringT::LockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) 및 [CSimpleStringT::UnlockBuffer](../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) 하거나 참조 횟수를 사용 하지 않도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [일반 MFC 항목](../mfc/general-mfc-topics.md)

