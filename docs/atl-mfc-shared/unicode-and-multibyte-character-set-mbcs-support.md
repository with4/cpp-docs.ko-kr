---
title: "유니코드 및 MBCS(멀티바이트 문자 집합) 지원 | Microsoft Docs"
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
  - "MFC[C++], 문자 집합 지원"
  - "MBCS[C++], 문자열 및 MFC 지원"
  - "문자열[C++], MFC의 MBCS 지원"
  - "문자 집합[C++], 멀티바이트"
  - "유니코드[C++], MFC 문자열"
  - "유니코드[C++], 문자열 개체"
  - "문자열[C++], 유니코드"
  - "문자열[C++], 문자 집합 지원"
ms.assetid: 44b3193b-c92d-40c5-9fa8-5774da303cce
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 유니코드 및 MBCS(멀티바이트 문자 집합) 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일부 언어\-예를들어, 일본어와 중국어\-는 큰 문자 집합이 있습니다.  이러한 시장에 대한 프로그래밍을 지원하기 위해서, Microsoft Foundation 클래스 라이브러리\(MFC\)는 큰 문자 집합을 처리하는 두 가지 방법에 사용할 수 있습니다.  
  
-   [Unicode](#_core_mfc_support_for_unicode_strings)  
  
-   [MBCS\(멀티바이트 문자 집합\)](#_core_mfc_support_for_mbcs_strings)  
  
 모든 새로운 개발을 위해 유니코드를 사용해야 합니다.  
  
##  <a name="_core_mfc_support_for_unicode_strings"></a> 유니코드 문자열에 대한 MFC 지원  
 전체 클래스 라이브러리는 유니코드 문자와 문자열 조건에 따라 사용할 수 있습니다.  특히, [CString](../atl-mfc-shared/reference/cstringt-class.md) 클래스는 유니코드를 지원 합니다.  
  
|||||  
|-|-|-|-|  
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|  
|MFC*xx*U.LIB|MFC*xx*U.PDB|MFC*xx*U.DLL|MFC*xx*UD.LIB|  
|MFC*xx*UD.PDB|MFC*xx*UD.DLL|MFCS*xx*U.LIB|MFCS*xx*U.PDB|  
|MFCS*xx*UD.LIB|MFCS*xx*UD.PDB|MFCM*xx*U.LIB|MFCM*xx*U.PDB|  
|MFCM*xx*U.DLL|MFCM*xx*UD.LIB|MFCM*xx*UD.PDB|MFCM*xx*UD.DLL|  
  
 \( *xx* 은 파일의 버전 번호를 나타냅니다. 예를 들어 '80'은 8.0 버전입니다.\)  
  
 `CString`은  `TCHAR`  데이터 형식을 기반으로 합니다.   `_UNICODE` 기호가 프로그램의 빌드에 정의된 경우,  `TCHAR`  은  `wchar_t` \(16 비트 문자 인코딩 형식\)형식으로 정의됩니다.   그렇지 않으면  `TCHAR`  은 보통 8 비트 문자 인코딩인  `char` 로 정의됩니다.  따라서 유니코드를 아래에  `CString`  의 16 비트 문자로 구성됩니다.  유니코드 없이  `char` 형식의 문자로 구성되어 있습니다.  
  
 응용 프로그램의 유니코드 프로그래밍을 완료하기 위해서 해야하는 일:  
  
-   조건부로 유니코드에 호환할 수 있는 리터럴 문자열을 코딩하기 위해  `_T`  매크로를 사용합니다.  
  
-   문자열을 전달할 때, 함수 인수가 문자 또는 바이트의 길이가 필요한지의 여부를 확인하십시오.  유니코드 문자열을 사용하는 경우에 중요한 차이가 있습니다.  
  
-   C 런타임 문자열 처리함수의 호환 가능한 버전을 사용하십시오.  
  
-   문자와 문자 포인터에 대해 다음 데이터 형식을 사용하십시오.  
  
    -   `TCHAR`\( `char` 을 사용할 수 있는 곳에\)  
  
    -   `LPTSTR`\( `char*` 을 사용할 수 있는 곳에\)  
  
    -   `LPCTSTR` \(`const char*`을 사용할 수 있는 곳에\)  `CString`은  `LPCTSTR`  을 제공합니다.  \( `CString`  와  `LPCTSTR` 를 변환을 위해\)  
  
 `CString`또한 유니코드 인식 생성자, 대입 연산자 및 비교 연산자를 제공합니다.  
  
 유니코드 프로그래밍에 관련된 정보에 대해서, [유니코드 항목](../mfc/unicode-in-mfc.md)을 확인하십시오.   [런타임 라이브러리 참조](../c-runtime-library/c-run-time-library-reference.md)는 호환 가능한 버전의 모든 문자열 처리 함수를 정의 합니다.  [국제화](../c-runtime-library/internationalization.md)범주를 확인하십시오.  
  
##  <a name="_core_mfc_support_for_mbcs_strings"></a> MBCS 문자열에 대한 MFC 지원  
  
> [!WARNING]
>  MBCS 문자열은 레거시 기술이며 새 프로젝트에서 사용할 수 없습니다.  MBCS를 사용하는 기존 코드를 유지,관리 해야하고 유니코드를 사용하여 코드를 업그레이드할 수 없는 경우에는 다음 정보가 제공됩니다.  
  
 또한 클래스 라이브러리는 더블 바이트 문자 집합 \(DBCS\)인 멀티 바이트 문자 집합을 사용할 수 있습니다.  
  
> [!IMPORTANT]
>  [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] 이후에, MSDN 다운로드 사이트의 Visual Studio의 추가기능으로 MFC Dll의 MBCS 버전으로 사용할 수 있습니다.  자세한 내용은 [MFC MBCS DLL Add\-in](../mfc/mfc-mbcs-dll-add-on.md) 을 참조하십시오.  
  
 멀티 바이트 문자 집합의 문자는 하나 또는 두 개의 바이트일 수 있습니다.  두 개의 바이트일 경우, 첫 번째 바이트는 코드 페이지가 사용중인에 따라 특정 범위에서 선택되는 특별한 "선행 바이트"입니다.  전체적으로 볼 때, lead와 "후행 바이트"는 고유 문자 인코딩을 지정 합니다.  
  
 `_MBCS` 기호가 프로그램의 빌드에 정의될 경우,   `TCHAR` \( `CString` 의 기반\)은  `char` 에 맵핑합니다.  사용자는  `CString` 의 바이트가 선행 바이트인지와 후행 바이트가 있는지를 결정합니다.  C 런타임 라이브러리는 사용자의 결정을 도울 수 있도록 함수를 제공합니다.  
  
 Dbcs에서 특정 string은 모든 싱글바이트 ANSI 문자, 모든 더블 바이트 문자 또는 둘의 조합을 포함할 수 있습니다.  문자열 구문 분석을 할 때는 특별히 주의해야 합니다.   `CString`  개체를 포함하고 있기 때문입니다.  
  
> [!NOTE]
>  Mfc에서 유니코드 문자열 직렬화을 통해 실행 중인 응용 프로그램의 버전에 관계 없이 유니코드와 MBCS 문자열을 읽을 수 있습니다.  데이터 파일은 유니코드 버전과 MBCS 버전의 프로그램 간에 호환이 가능 합니다.  
  
 `CString`멤버 함수는 그들이 호출하거나 유니코드 인식 기능을 사용한 C 런타임 함수의 특별한 "일반 텍스트" 버전을 사용합니다.  따라서 예를 들어  `CString`  함수가 일반적으로  `strcmp` 을 호출했을 경우, 대신에 해당 제네릭 텍스트 함수인  `_tcscmp` 을 호출합니다.   `_MBCS`  와  `_UNICODE` 가 정의 된 방법에 따라,  `_tcscmp` 은 다음과 같이 매핑합니다.  
  
|||  
|-|-|  
|`_MBCS`가 정의됨|`_mbscmp`|  
|`_UNICODE`가 정의됨|`wcscmp`|  
|어떤 기호도 정의되지 않음|`strcmp`|  
  
> [!NOTE]
>  `_MBCS` 옵션과 `_UNICODE` 옵션은 함께 사용할 수 없습니다.  
  
 모든 런타임 문자열 처리 루틴에 대한 일반 텍스트 함수 매핑에 대해서는 [C 런타임 라이브러리 참조](../c-runtime-library/c-run-time-library-reference.md)에 설명되어 있습니다.  특히 [국제화](../c-runtime-library/internationalization.md)을 확인하십시오.  
  
 마찬가지로,  `CString`  메서드는 "일반" 데이터 형식 매핑을 사용하여 구현됩니다.  MBCS와 유니코드를 모두 사용하려면, MFC는 `TCHAR`을 `char`대신, `LPTSTR` 을 `char*`대신, 그리고 `LPCTSTR` 을 `const char*`대신 사용하십시오.  이들은 MBCS 또는 유니코드 중 하나에 대한 올바른 매핑을 보장합니다.  
  
## 참고 항목  
 [문자열](../atl-mfc-shared/strings-atl-mfc.md)   
 [문자열 조작](../c-runtime-library/string-manipulation-crt.md)