---
title: "Basic CString Operations | Microsoft Docs"
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
  - "문자, accessing in CStrings"
  - "CString objects"
  - "CString objects, 기본 작업"
  - "literal strings, CString operations"
  - "문자열 비교, CString operations"
  - "문자열 리터럴, CString operations"
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
caps.latest.revision: 17
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Basic CString Operations
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 다음의 기본 설명  [CString](../atl-mfc-shared/reference/cstringt-class.md) 작업:  
  
-   [표준 C 리터럴 문자열이에서 CString 개체 만들기](#_core_creating_cstring_objects_from_standard_c_literal_strings)  
  
-   [Cstring에서 개별 문자 액세스](#_core_accessing_individual_characters_in_a_cstring)  
  
-   [두 개의 CString 개체 연결](#_core_concatenating_two_cstring_objects)  
  
-   [CString 개체를 비교합니다.](#_core_comparing_cstring_objects)  
  
-   [CString 개체를 변환합니다.](#_core_converting_cstring_objects)  
  
 `Class CString`클래스 템플릿을 기반으로 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md).  `CString`is a `typedef` of `CStringT`.  보다 정확 하 게 `CString` 되는 `typedef` 에  *명시적 특수화* 의 `CStringT`, 클래스 템플릿 클래스 정의에 사용 하는 일반적인 방법입니다.  이와 유사 하 게 정의 된 클래스는 `CStringA` 및 `CStringW`.  명시적 특수화에 대 한 자세한 내용은 [템플릿 클래스 인스턴스화](../Topic/Class%20Template%20Instantiation.md).  
  
 `CString` `CStringA`, 및 `CStringW` atlstr.h에 정의 됩니다.  `CStringT`cstringt.h에서 정의 됩니다.  
  
 `CString` `CStringA`, 및 `CStringW` 각 get 메서드와 연산자가 정의 된 집합 `CStringT` 지원 문자열 데이터로 사용 합니다.  중복 및 일부 경우에는 방법 C 런타임 라이브러리의 문자열 서비스를 능가할.  
  
 참고: `CString` 는 기본 클래스입니다.  C \+에서 사용 되는 string 클래스에 대 한 \+ CLI 관리 프로젝트를 사용 하는 `System.String`.  
  
##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> 표준 C 리터럴 문자열이에서 CString 개체 만들기  
 C 스타일의 리터럴 문자열을 할당할 수는 `CString` 만 지정할 수 있습니다 `CString` 다른 개체.  
  
-   C 리터럴 문자열 값을 할당 한 `CString` 개체입니다.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_1.cpp)]  
  
-   하나의 값을 할당 `CString` 다른 `CString` 개체입니다.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_2.cpp)]  
  
     내용의 `CString` 개체 복사 하나 `CString` 개체를 할당 됩니다.  따라서 두 문자열은 문자열을 구성 하는 실제 문자에 대 한 참조를 공유 하지 않습니다.  사용 하는 방법에 대 한 자세한 내용은 `CString` 값으로 개체를 참조 하십시오. [CString Semantics](../atl-mfc-shared/cstring-semantics.md).  
  
    > [!NOTE]
    >  유니코드 또는 ANSI, 리터럴 문자열을 \_T 매크로 사용 하 여 코드를 컴파일할 수 있도록 응용 프로그램을 작성.  자세한 내용은 [유니코드 및 MBCS\(멀티바이트 문자 집합\) 지원](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)을 참조하십시오.  
  
##  <a name="_core_accessing_individual_characters_in_a_cstring"></a> Cstring에서 개별 문자 액세스  
 개별 문자에 액세스할 수 있습니다는 `CString` 를 사용 하 여 개체의 `GetAt` 및 `SetAt` 메서드.  대신 배열 요소 또는 아래 첨자 연산자 \(\)을 사용할 수 있습니다 `GetAt` 개별 문자를 인식 하도록 합니다.  \(이 배열 요소에 액세스 하 여 표준 C 스타일 문자열 인덱스를 유사합니다.\) 인덱스 값에 대 한 `CString` 문자는 0부터 시작 합니다.  
  
##  <a name="_core_concatenating_two_cstring_objects"></a> 두 개의 CString 개체 연결  
 두 개를 연결 하 여 `CString` 개체를 사용 하 여 연결 연산자 \(\+ 또는 \+ \=\)와 같이.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_3.cpp)]  
  
 인수 중 적어도 하나에 연결 연산자 \(\+ 또는 \+ \=\) 있어야는 `CString` 있지만 개체, 문자열 상수를 사용할 수 있습니다 \(예를 들어, `"big"`\) 또는 `char` \(예를 들어, ' x'\) 다른 인수에 대 한.  
  
##  <a name="_core_comparing_cstring_objects"></a> CString 개체를 비교합니다.  
 `Compare` 메서드 및 \= \= 연산자를 `CString` 과 같습니다.  `Compare``operator==`, 및 `CompareNoCase` MBCS와 유니코드 인식 하 고 있습니다.  `CompareNoCase`또한 대\/소문자 구분입니다.  `Collate` 메서드의 `CString` 로캘 구분 되며 보다 느린 경우가 `Compare`.  사용 `Collate` 만 위치 하면 정렬에서 준수 해야 규칙으로 지정 된 현재 로케일에 있습니다.  
  
 다음 표에서 사용할 수 있는  [CString](../atl-mfc-shared/reference/cstringt-class.md) 비교 함수 및 C 런타임 라이브러리에서 그 해당 하는 유니코드\/MBCS 노트북 기능.  
  
|CString 함수|MBCS 함수|유니코드 함수|  
|----------------|-------------|-------------|  
|`Compare`|`_mbscmp`|`wcscmp`|  
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|  
|`Collate`|`_mbscoll`|`wcscoll`|  
  
 `CStringT` 클래스 템플릿 정의 관계형 연산자 \(\<, \< \=, \> \=, \>, \=, \= 및\! \=\)에서 사용할 수 있는 `CString`.  두 값을 비교할 수 있습니다 `CStrings` 다음 예제와 같이 이러한 연산자를 사용 하 여.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/CPP/basic-cstring-operations_4.cpp)]  
  
##  <a name="_core_converting_cstring_objects"></a> CString 개체를 변환합니다.  
 CString 개체를 다른 문자열 형식으로 변환 하는 방법에 대 한 자세한 내용은 참조 하십시오. [방법: 다양한 문자열 형식 간 변환](../text/how-to-convert-between-various-string-types.md).  
  
## CString wcout을 사용 하 여  
 Cstring을 사용 하려면 `wcout` 개체에 명시적으로 캐스팅 해야는 `const wchar_t*` 다음 예제와 같이:  
  
```  
CString cs("meow");  
  wcout << (const wchar_t*) cs << endl;  
  
```  
  
 캐스트를 하지 않고 `cs` 취급 되는 `void*` 및 `wcout` 개체의 주소를 인쇄 합니다.  이 동작은 C\+\+ 표준 준수 자체에서 올바른 템플릿 인수가 추론 및 오버 로드 확인 간의 미묘한 상호 작용 때문입니다.  
  
## 참고 항목  
 [문자열](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)   
 [템플릿 클래스 인스턴스화](../Topic/Class%20Template%20Instantiation.md)   
 [클래스 템플릿의 명시적 특수화](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)   
 [클래스 템플릿의 부분 특수화](../cpp/template-specialization-cpp.md)   
 [방법: 다양한 문자열 형식 간 변환](../text/how-to-convert-between-various-string-types.md)