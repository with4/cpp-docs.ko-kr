---
title: "기본 CString 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42353a9c59bead96da8eb3b114c8acb2361b53d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="basic-cstring-operations"></a>기본 CString 작업
이 항목에서는 다음과 같은 기본 설명 [CString](../atl-mfc-shared/reference/cstringt-class.md) 작업:  
  
- [표준 C 리터럴 문자열에서 CString 개체 만들기](#_core_creating_cstring_objects_from_standard_c_literal_strings)  
  
- [CString의 개별 문자 액세스](#_core_accessing_individual_characters_in_a_cstring)  
  
- [두 개의 CString 개체를 연결합니다.](#_core_concatenating_two_cstring_objects)  
  
- [CString 개체 비교](#_core_comparing_cstring_objects)  
  
- [CString 개체 변환](#_core_converting_cstring_objects)  
  
 `Class CString`클래스 템플릿을 기반으로 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)합니다. `CString`이 `typedef` 의 `CStringT`합니다. 보다 정확 하 게 `CString` 는 `typedef` 의 *명시적 특수화* 의 `CStringT`, 하는 클래스 템플릿을 사용 하 여 클래스를 정의 하는 일반적인 방법입니다. 마찬가지로 정의 된 클래스는 `CStringA` 및 `CStringW`합니다.  
  
 `CString``CStringA`, 및 `CStringW` atlstr.h에 정의 됩니다. `CStringT`cstringt.h에 정의 됩니다.  
  
 `CString``CStringA`, 및 `CStringW` 메서드 및 정의 된 연산자의 집합을 가져오려면 각 `CStringT` 지 원하는 문자열 데이터와 함께 사용 합니다. 중복 및 경우에 따라 메서드 중 일부를 초과할 C 런타임 라이브러리의 문자열 서비스입니다.  
  
 참고: `CString` 기본 클래스입니다. C +에 사용 하기 위한 string 클래스에 대 한 + 관리 되는 프로젝트를 사용 하 여 CLI `System.String`합니다.  
  
##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a>표준 C 리터럴 문자열에서 CString 개체 만들기  
 리터럴 문자열을 C 스타일을 할당할 수 있습니다는 `CString` 하나를 할당할 수와 마찬가지로 `CString` 개체를 다른 개체입니다.  
  
-   C 리터럴 문자열을 값을 할당 한 `CString` 개체입니다.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]  
  
-   하나의 값을 할당 `CString` 다른 `CString` 개체입니다.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]  
  
     내용을 `CString` 한 경우 개체 복사는 `CString` 다른 개체를 할당 하는 합니다. 따라서 두 문자열이 문자열 구성 하는 실제 문자에 대 한 참조를 공유 하지 않습니다. 사용 하는 방법에 대 한 자세한 내용은 `CString` 값으로 개체 참조 [CString 의미 체계](../atl-mfc-shared/cstring-semantics.md)합니다.  
  
    > [!NOTE]
    >  _T 매크로 사용 하 여 코드 리터럴 문자열을 ANSI 또는 유니코드에 대해 컴파일할 수 있도록 응용 프로그램을 작성 하 합니다. 자세한 내용은 참조 [유니코드 및 멀티 바이트 문자 집합 (MBCS) 지원](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)합니다.  
  
##  <a name="_core_accessing_individual_characters_in_a_cstring"></a>CString의 개별 문자 액세스  
 개별 문자에서 액세스할 수 있습니다는 `CString` 사용 하 여 개체는 `GetAt` 및 `SetAt` 메서드. 배열 요소 또는 아래 첨자 연산자 () 대신 사용할 수도 있습니다 `GetAt` 개별 문자를 가져오려고 합니다. (이 비슷하며 배열 요소에 액세스 하 여 표준 C 스타일 문자열) 인덱스에 대 한 값 `CString` 문자는 0부터 시작 합니다.  
  
##  <a name="_core_concatenating_two_cstring_objects"></a>두 개의 CString 개체를 연결합니다.  
 연결할 두 `CString` 개체를 사용 하 여 연결 연산자 (+ 또는 + =), 다음과 같이 합니다.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]  
  
 연결 연산자의 인수 중 하나 이상 (+ 또는 + =) 이어야 합니다는 `CString` 개체를 사용할 수 있습니다 상수 문자열 (예를 들어 `"big"`) 또는 `char` (예를 들어 ' x') 다른 인수에 대 한 합니다.  
  
##  <a name="_core_comparing_cstring_objects"></a>CString 개체 비교  
 `Compare` 메서드 및 연산자에 대 한 = = `CString` 동일 합니다. `Compare``operator==`, 및 `CompareNoCase` 는 MBCS 및 유니코드 인식; `CompareNoCase` 대/소문자 구분 이기도 합니다. `Collate` 방식의 `CString` 로캘 구분 이며 종종 방식 보다 속도가 느립니다 `Compare`합니다. 사용 하 여 `Collate` 현재 로캘에 따라 지정 된 대로 규칙만 준수 해야 정렬 됩니다.  
  
 다음 표에서 사용 가능한 [CString](../atl-mfc-shared/reference/cstringt-class.md) 비교 함수 및 C 런타임 라이브러리에서의 해당 하는 유니코드/MBCS 이식 가능 기능은 합니다.  
  
|CString 함수|MBCS 함수|유니코드 함수|  
|----------------------|-------------------|----------------------|  
|`Compare`|`_mbscmp`|`wcscmp`|  
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|  
|`Collate`|`_mbscoll`|`wcscoll`|  
  
 `CStringT` 클래스 템플릿 정의 관계형 연산자 (<, \<=, > =, >, = =, 및! =)에서 사용할 수 있는 `CString`합니다. 두 개를 비교 `CStrings` 다음 예제와 같이 이러한 연산자를 사용 하 여 합니다.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]  
  
##  <a name="_core_converting_cstring_objects"></a>CString 개체 변환  
 CString 개체를 다른 문자열 형식으로 변환 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 다양 한 문자열 형식 간의 변환](../text/how-to-convert-between-various-string-types.md)합니다.  
  
## <a name="using-cstring-with-wcout"></a>Wcout CString 사용  
 CString를 사용 하려면 `wcout` 개체를 명시적으로 캐스팅 해야는 `const wchar_t*` 다음 예제와 같이:  
  
```  
CString cs("meow");

    wcout <<(const wchar_t*) cs <<endl;  
 
```  
  
 캐스팅, 하지 않으면 `cs` 로 처리 되는 `void*` 및 `wcout` 개체의 주소를 인쇄 합니다. 이 동작은 미묘한와 상호 작용 템플릿 인수 추론 및 오버 로드 확인에 올바른 자체 있는 사이 호환 되는 c + + 표준에 의해 발생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)   
 [템플릿 특수화](../cpp/template-specialization-cpp.md)   
 [방법: 다양한 문자열 형식 간 변환](../text/how-to-convert-between-various-string-types.md)

