---
title: "힌트 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cpp.hint
- vc.hint.file
dev_langs:
- C++
helpviewer_keywords:
- stop file
- cpp.hint
- hint file
- cpp.stop
- Class View, hint file
ms.assetid: 17194f66-cf62-4523-abec-77db0675ab65
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 432b5fa5041a7997c9df0593dc511c29854387ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hint-files"></a>힌트 파일
A *힌트 파일* Visual Studio를 통해 통합된 개발 환경 (IDE) 함수 및 매크로의 이름과 같은 Visual c + + 식별자를 해석 합니다. Visual c + + 프로젝트, IDE를 열면 *구문 분석 시스템* 프로젝트의 각 소스 파일의 코드를 분석 하 고 모든 식별자에 대 한 정보를 수집 합니다. IDE와 같은 기능을 지원 하기 위해 해당 정보를 사용 하 여는 **클래스 뷰** 브라우저 및 **탐색 모음**합니다.  
  
 Visual c + + 2010에서 도입 된 구문 분석 시스템 C/c + + 구문을 이해 하기는 하지만 매크로 포함 하는 문의 잘못 해석할 수 있습니다. 문은 매크로 사용 하면 소스 코드를 작성 된 대로 잘못 된 구문이 있는 경우 잘못 해석 될 수 있습니다. 전처리기에서 대체 하 고 소스 코드를 컴파일할 때 문이 구문이 잘못 될 수는 [매크로 식별자](../preprocessor/hash-define-directive-c-cpp.md) 해당 정의 사용 합니다. 구문 분석 시스템 힌트 파일을 사용 하 여 매크로를 해석 하기 때문에 프로젝트를 만들 필요 없이 작동 합니다. 따라서와 같은 기능을 검색 **클래스 뷰** 즉시 사용할 수 있습니다.  
  
 힌트 파일에 포함 된 사용자 지정 가능한 *힌트*를 충족 하는 C/c + + 매크로 정의 구문은 동일 합니다. Visual c + +는 대부분의 프로젝트에 대 한 충분 하는 기본 제공 힌트 파일에 포함 되어 있지만 Visual Studio에서 식별자를 처리 하는 방식을 개선 하기 위해 사용자 고유의 힌트 파일을 만들 수 있습니다.  
  
> [!IMPORTANT]
>  를 수정 하거나 추가 힌트 파일.sdf 파일 및/또는 솔루션에서 변경 내용을 적용 하려면 VC.db 파일을 삭제 해야 합니다.  
  
## <a name="scenario"></a>시나리오  
 다음 코드를 검사 하는 소스 파일에 있다고 가정은 **클래스 뷰** 브라우저. `STDMETHOD` 라는 메서드를 선언 하는 매크로 `myMethod` 매개 변수를 사용 하 고에 대 한 포인터를 반환 하는 **HRESULT**합니다.  
  
```  
// Source code file.  
STDMETHOD(myMethod)(int parameter1);  
```  
  
 다음 매크로 정의 별도 헤더 파일입니다.  
  
```  
// Header file.  
#define STDMETHOD(method) HRESULT (STDMETHODCALLTYPE * method)  
#define STDMETHODCALLTYPE __stdcall  
#define HRESULT void*  
```  
  
 구문 분석 시스템 STDMETHOD 라는 함수를 선언으로 나타나기 때문에 소스 코드를 해석할 수 없으면 및 두 개의 매개 변수 목록에 있기 때문에 해당 선언이 구문이 잘못 되었습니다. 구문 분석 시스템 헤더 파일에 대 한 정의 검색 하려면 열리지 않고는 `STDMETHOD`, `STDMETHODCALLTYPE`, 및 `HRESULT` 매크로입니다. 구문 분석 시스템 해석할 수 없기 때문에 `STDMETHOD` 매크로 전체 문이 무시 하 고 다음 구문 분석을 계속 합니다.  
  
 프로젝트에 하나 이상의 중요 한 헤더 파일에서 사용할 수 있는 때문에 구문 분석 시스템 헤더 파일을 사용 하지 않습니다. 모든 헤더 파일이 변경 되 면 구문 분석 시스템 IDE의 성능이 느려집니다 프로젝트에서 헤더 파일을 다시 검사 해야 합니다. 구문 분석 시스템 처리 하는 방법을 지정 하는 힌트를 사용 하는 대신,는 `STDMETHOD`, `STDMETHODCALLTYPE`, 및 `HRESULT` 매크로입니다.  
  
 힌트를 사용 해야 하는 어떻게 알 수 있을까요? 및 힌트가 필요한 경우 종류 만들어야 하는지에 대해? 하나의 힌트는 필요한 경우 경우 보기에 있는 식별자의 **클래스 뷰** 의 뷰와 일치 하지 않습니다는 **편집기**합니다. 예를 들어 **클래스 뷰** 사용자가 알고 있는 클래스 멤버가 있는 표시 될 수 있습니다. 또는 멤버의 이름이 올바르지 않습니다. 일반적인 문제를 해결 하는 힌트의 형식에 대 한 자세한 내용은 무엇 매크로 필요 A 힌트를 참조 하세요? 이 항목의 뒷부분에 나오는 섹션입니다.  
  
## <a name="architecture"></a>아키텍처  
 힌트 파일 실제 디렉터리와 관련 된, 논리적 디렉터리가 아니라에 표시 된 **솔루션 탐색기**합니다. 힌트 파일 효과가 힌트 파일에 대 한 프로젝트에 추가할 필요가 없습니다. 소스 파일을 구문 분석 하는 경우에 힌트 파일을 사용 하는 구문 분석 됩니다.  
  
 모든 힌트 파일의 이름은 **cpp.hint**합니다. 따라서 많은 디렉터리에는 힌트 파일에는 포함 될 수 있지만 하나의 힌트 파일은 특정 디렉터리에서 발생할 수 있습니다.  
  
 0 개 이상의 힌트 파일 프로젝트에 영향을 받을 수 있습니다. 힌트 파일이 없습니다 구문 분석 시스템 오류 복구 기법을 사용 하 여 해독할 수 없는 소스 코드를 무시 합니다. 그렇지 않으면 구문 분석 시스템을 찾고 힌트 수집 다음 전략을 사용 합니다.  
  
### <a name="search-order"></a>검색 순서  
 구문 분석 시스템에서는 다음과 같은 순서로 힌트 파일에 대 한 디렉터리를 검색합니다.  
  
-   Visual c + +에 대 한 설치 패키지를 포함 하는 디렉터리 (**vcpackages**). 이 디렉터리에 같은 자주 사용 되는 시스템 파일의에서 기호에 설명 하는 기본 제공 힌트 파일 **windows.h**합니다. 따라서 프로젝트 필요로 하는 힌트의 대부분을 자동으로 상속 합니다.  
  
-   소스 파일 자체를 포함 하는 디렉터리를 소스 파일의 루트 디렉터리 경로입니다. 일반적인 Visual c + + 프로젝트의 루트 디렉터리는 솔루션 또는 프로젝트 파일을 포함합니다.  
  
     이 규칙에 대 한 예외는 경우는 *중지 파일* 소스 파일 경로 있습니다. 중지 파일 검색 순서에 대 한 추가 제어를 제공 하며 모든 라는 파일을 **cpp.stop**합니다. 루트 디렉터리에서 시작 하는 대신 구문 분석 하는 시스템 중지 파일을 원본 파일이 포함 된 디렉터리에 포함 된 디렉터리에서 검색 합니다. 일반적인 프로젝트에서는 중지 파일이 필요 하지 않습니다.  
  
### <a name="hint-gathering"></a>힌트 모으고 있습니다.  
 힌트 파일에 포함 된 0 개 이상의 *힌트*합니다. 힌트는 정의 되었거나 C/c + + 매크로와 동일 하 게 삭제 합니다. 즉,는 `#define` 전처리기 지시문을 만들거나 한 힌트를 재정의 및 `#undef` 지시문은 힌트를 삭제 합니다.  
  
 구문 분석 하는 시스템 검색 순서에 따라 앞에서 설명한 각 힌트 파일을 열고, 각 파일의 힌트 집합이를 누적 *유효한 힌트*, 다음 유효한 힌트를 사용 하 여 코드의 식별자를 해석 합니다.  
  
 힌트를 누적 다음 규칙을 사용 하는 구문 분석 됩니다.  
  
-   새 힌트에 이미 정의 되어 있지 않은 이름을 지정 하는 경우 새 힌트 이름을 유효한 힌트에 추가 합니다.  
  
-   새 힌트에 이미 정의 되어 있는 이름을 지정 하는 경우 새 힌트는 기존 힌트 다시 정의 합니다.  
  
-   새 힌트는 경우는 `#undef` 기존의 유효한 힌트를 지정 하는 지시문, 새 힌트는 기존 힌트를 삭제 합니다.  
  
 첫 번째 규칙 하면 유효한 힌트 이전에 열린된 힌트 파일에서 상속 됩니다. 마지막 두 개의 규칙 검색 순서에서 나중에 발생 하는 힌트가 이전에 발생 한 힌트를 재정의할 수을 의미 합니다. 예를 들어 소스 파일을 포함 하는 디렉터리에서 힌트 파일을 만들면 모든 이전 힌트를 재정의할 수 있습니다.  
  
 힌트 수집 방법의 개요를 참조 하십시오.는 `Example` 이 항목의 뒷부분에 나오는 섹션.  
  
### <a name="syntax"></a>구문  
 힌트는 생성 및 만들고 매크로 삭제 하는 전처리기 지시문과 동일한 구문을 사용 하 여 삭제 됩니다. 사실, 구문 분석 시스템 힌트를 평가 하는 C/c + + 전처리기를 사용 합니다. 전처리기 지시문에 대 한 자세한 내용은 참조 [#define 지시문 (C/c + +)](../preprocessor/hash-define-directive-c-cpp.md) 및 [#undef 지시문 (C/c + +)](../preprocessor/hash-undef-directive-c-cpp.md)합니다.  
  
 만 비정상적인 구문 요소가 `@<`, `@=`, 및 `@>` 대체 문자열입니다. 에 사용 되는 힌트 파일 구체적인 대체 문자열은 *지도* 매크로입니다. 지도 다른 데이터, 함수 또는 이벤트 처리기에 데이터, 함수 또는 이벤트와 관련 된 매크로 집합. 예를 들어 `MFC` 지도 사용 하 여 만들려는 [메시지 맵](../mfc/reference/message-maps-mfc.md), 및 `ATL` 지도 사용 하 여 만들려는 [지도 개체](../atl/reference/object-map-macros.md)합니다. 힌트 파일 구체적인 대체 문자열 map의 시작, 중간, 및 끝 요소를 나타냅니다. 맵 매크로의 이름만 중요 합니다. 따라서 각 대체 문자열은 매크로의 구현을 의도적으로 숨깁니다.  
  
 힌트는 다음 구문을 사용 합니다.  
  
|구문|의미|  
|------------|-------------|  
|`#define`*힌트 이름* *대체 문자열*<br /><br /> `#define`*힌트 이름* `(` *매개 변수*,... `)` *대체 문자열*|새 힌트를 정의 하거나 기존 힌트를 재정의 하는 전처리기 지시문 전처리기 지시문, 뒤의 각 항목을 대체 *힌트 이름* 만으로도 소스 코드에서 *대체 문자열*합니다.<br /><br /> 두 번째 구문 형식 함수 형식 힌트를 정의합니다. 각 항목에 전처리기 함수 형식 힌트에 소스 코드에서 발생 하는 경우 먼저 대체 *매개 변수* 에 *대체 문자열* 소스 코드 및 대체에는 해당 인수 사용 *힌트 이름* 와 *대체 문자열*합니다.|  
|`@<`|힌트 파일 특정 *대체 문자열* 의 지도 요소 집합의 시작을 나타내는입니다.|  
|`@=`|힌트 파일 특정 *대체 문자열* 중간 지도 요소를 나타내는입니다. 지도 요소가 여러 개 있을 수 있습니다.|  
|`@>`|힌트 파일 특정 *대체 문자열* 의 지도 요소 집합의 끝을 나타내는입니다.|  
|`#undef`*힌트 이름*|기존 힌트를 삭제 하는 전처리기 지시문 힌트의 이름을 제공는 *힌트 이름* 식별자입니다.|  
|`//`*주석*|한 줄 주석입니다.|  
|`/*` *comment* `*/`|여러 줄 설명입니다.|  
  
## <a name="what-macros-require-a-hint"></a>어떤 힌트가 필요한 매크로?  
 특정 유형의 매크로 구문 분석 시스템을 방해할 수 있습니다. 이 섹션에서는 문제를 일으킬 수 있는 매크로의 형식과 힌트 해당 문제를 해결 하기 위해 만들 수 있습니다를 설명 합니다.  
  
### <a name="disruptive-macros"></a>방해가 되는 매크로  
 일부 매크로 구문 분석 시스템 소스 코드를 잘못 해석 되지만 검색 환경을 손상 없이 무시 될 수 있습니다. 예를 들어 소스 코드 주석 언어 ([SAL](../c-runtime-library/sal-annotations.md)) 매크로 프로그래밍 버그 찾기 데 도움이 되는 c + + 특성을 확인 합니다. 코드를 탐색할 때 SAL 주석을 무시 하려는 경우 해당 주석을 숨기는 힌트 파일을 만드는 것이 좋습니다.  
  
 다음 소스 코드에 대 한 매개 변수 입력은 `FormatWindowClassName()` 함수는 `PXSTR`, 매개 변수 이름이 고 `szBuffer`합니다. 그러나 구문 분석 시스템 실수는 `_Pre_notnull_` 및 `_Post_z_` SAL 주석은 매개 변수 형식 또는 매개 변수 이름입니다.  
  
 **소스 코드:**  
  
```  
static void FormatWindowClassName(_Pre_notnull__Post_z_ PXSTR szBuffer)  
```  
  
 **방법:** 정의 Null  
  
 이 경우 전략 존재 하지 않은 경우 처럼 SAL 주석을 처리 하는 것입니다. 이 위해 인 대체 문자열은 null 힌트를 지정 합니다. 따라서 구문 분석 시스템 무시 주석, 및 **클래스 뷰** 브라우저에서 표시 되지 않습니다. (Visual c + + SAL 주석을 숨기는 기본 제공 힌트 파일 포함)  
  
 **힌트 파일:**  
  
```  
#define _Pre_notnull_  
```  
  
### <a name="concealed-cc-language-elements"></a>숨겨진된 C/c + + 언어 요소  
 구문 분석 시스템 소스 코드를 해석 하는 일반적인 이유는 매크로 C/c + +를 숨깁니다 [문장 부호](../cpp/punctuators-cpp.md) 또는 [키워드](../cpp/keywords-cpp.md) 토큰입니다. 즉, 매크로 포함 될 수 있습니다 문장 부호, 쌍 중 절반와 같은 `<>`, `[]`, `{}`, 및 `()`합니다.  
  
 다음 소스 코드에서는 `START_NAMESPACE` 매크로 짝이 없는 왼쪽된 중괄호 숨깁니다 (`{`).  
  
 **소스 코드:**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
 **방법:** 직접 복사  
  
 매크로의 의미 체계 검색 환경을에 중요 한 경우 힌트는는 매크로 만듭니다. 구문 분석 시스템 힌트 파일의 정의를 매크로 확인합니다.  
  
 소스 파일에서 다른 매크로 포함 하는 경우 해당 매크로 해석 되도록 유효한 힌트의 집합에 이미 있는 경우에 note 합니다.  
  
 **힌트 파일:**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
### <a name="maps"></a>지도  
 지도 요소를 시작, 끝 요소 및 0 개 이상의 중간 요소를 지정 하는 매크로 구성 됩니다. 각 지도 매크로 C/c + + 언어 요소를 숨깁니다 전체 C/c + + 문 구문에 서로 다른 여러 매크로 분산 하기 때문에 지도 해석 하는 구문 분석 시스템입니다.  
  
 다음 소스 코드에서 정의 된 `BEGIN_CATEGORY_MAP`, `IMPLEMENTED_CATEGORY`, 및 `END_CATEGORY_MAP` 매크로입니다.  
  
 **소스 코드:**  
  
```  
#define BEGIN_CATEGORY_MAP(x)\  
static const struct ATL::_ATL_CATMAP_ENTRY* GetCategoryMap() throw() {\  
static const struct ATL::_ATL_CATMAP_ENTRY pMap[] = {  
#define IMPLEMENTED_CATEGORY( catid ) { _ATL_CATMAP_ENTRY_IMPLEMENTED, &catid },  
#define END_CATEGORY_MAP()\  
   { _ATL_CATMAP_ENTRY_END, NULL } };\  
   return( pMap ); }  
```  
  
 **방법:** 식별 지도 요소  
  
 시작, 중간 (있는 경우) 및 end에 대 한 힌트 지정 map의 요소입니다. 특수 한 맵 대체 문자열을 사용 하 여 `@<`, `@=`, 및 `@>`합니다. 자세한 내용은 참조는 `Syntax` 이 항목의 섹션입니다.  
  
 **힌트 파일:**  
  
```  
// Start of the map.  
#define BEGIN_CATEGORY_MAP(x) @<  
// Intermediate map element.  
#define IMPLEMENTED_CATEGORY( catid ) @=  
// Intermediate map element.  
#define REQUIRED_CATEGORY( catid ) @=  
// End of the map.  
#define END_CATEGORY_MAP() @>  
```  
  
### <a name="composite-macros"></a>복합 매크로  
 복합 매크로 구문 분석 시스템 혼동 하는 매크로 형식이 중 하나 이상을 포함 합니다.  
  
 다음 소스 코드에는 `START_NAMESPACE` 네임 스페이스 범위 시작을 지정 하는 매크로 및 `BEGIN_CATEGORY_MAP` 지도의 시작을 지정 하는 매크로입니다.  
  
 **소스 코드:**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
 **방법:** 직접 복사  
  
 만들기에 대 한 힌트는 `START_NAMESPACE` 및 `BEGIN_CATEGORY_MAP` 매크로, 다음에 대 한 힌트를 만듭니다는 `NSandMAP` 매크로 같은 소스 코드 앞에 표시 된 것입니다. 또는 복합 매크로 구성 된 경우 방해가 되는 매크로 및 공백 인 대체 문자열은 null 정의 하는 힌트를 정의할 수 있습니다.  
  
 이 예제에서는 가정 `START_NAMESPACE` 힌트를 이미이 항목에 설명 된 대로 `Concealed C/C++ Language Elements` 부제목 합니다. 가정 및 `BEGIN_CATEGORY_MAP` 에서 이전에 설명 된 대로 힌트가 `Maps`합니다.  
  
 **힌트 파일:**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
### <a name="inconvenient-macros"></a>불편 한 매크로  
 구문 분석 하는 시스템에서 일부 매크로 해석할 수 있지만 소스 코드에는 너무 길거나 복잡 하기 때문에 읽기 어려운. 가독성을 높이기 위해 매크로의 표시를 단순화 하는 힌트를 제공할 수 있습니다.  
  
 **소스 코드:**  
  
```  
#define STDMETHOD(methodName) HRESULT (STDMETHODCALLTYPE * methodName)  
```  
  
 **방법:** 단순화  
  
 보다 간단한 매크로 정의 표시 하는 힌트를 만듭니다.  
  
 **힌트 파일:**  
  
```  
#define STDMETHOD(methodName) void* methodName  
```  
  
## <a name="example"></a>예  
 다음 예제에서는 힌트가 힌트 파일에서 누적 되는 방법을 보여 줍니다. 이 예에서 중지 파일 사용 되지 않습니다.  
  
 다음 그림은 Visual c + + 프로젝트에 있는 실제 디렉터리 중 일부를 보여 줍니다. 힌트 파일은는 `vcpackages`, `Debug`, `A1`, 및 `A2` 디렉터리입니다.  
  
### <a name="hint-file-directories"></a>힌트 파일 디렉터리  
 ![일반 및 프로젝트 &#45; 특정 힌트 파일 디렉터리입니다. ] (../ide/media/hintfile.png "HintFile")  
  
### <a name="directories-and-hint-file-contents"></a>디렉터리 및 힌트 파일 내용  
 다음 목록은 힌트 파일 및 해당 힌트 파일의 내용을 포함 하는이 프로젝트의 디렉터리를 나타냅니다. 일부에 있는 여러 힌트는 `vcpackages` 디렉터리 힌트 파일 나열 됩니다.  
  
-   vcpackages  
  
    ```  
    // vcpackages (partial list)  
    #define _In_  
    #define _In_opt_  
    #define _In_z_  
    #define _In_opt_z_  
    #define _In_count_(size)  
    ```  
  
-   디버그  
  
    ```  
    // Debug  
    #undef _In_  
    #define OBRACE {  
    #define CBRACE }  
    #define RAISE_EXCEPTION(x) throw (x)  
    #define START_NAMESPACE namespace MyProject {  
    #define END_NAMESPACE }  
    ```  
  
-   A1  
  
    ```  
    // A1  
    #define START_NAMESPACE namespace A1Namespace {  
    ```  
  
-   A2  
  
    ```  
    // A2  
    #undef OBRACE  
    #undef CBRACE  
    ```  
  
### <a name="effective-hints"></a>유효한 힌트  
 다음 표에서이 프로젝트의 소스 파일에 대 한 유효한 힌트를 나열합니다.  
  
-   원본 파일: A1_A2_B.cpp  
  
-   유효한 힌트:  
  
    ```  
    // vcpackages (partial list)  
    #define _In_opt_  
    #define _In_z_  
    #define _In_opt_z_  
    #define _In_count_(size)  
    // Debug...  
    #define RAISE_EXCEPTION(x) throw (x)  
    // A1  
    #define START_NAMESPACE namespace A1Namespace {   
    // ...Debug  
    #define END_NAMESPACE }  
    ```  
  
 다음 내용은 앞의 목록에 적용 됩니다.  
  
-   유효한 힌트는는 `vcpackages`, `Debug`, `A1`, 및 `A2` 디렉터리입니다.  
  
-   **#undef** 지시어는 `Debug` 힌트 파일 제거는 `#define _In_` 힌트는 `vcpackages` 힌트 파일 디렉터리입니다.  
  
-   힌트 파일에는 `A1` 다시 정의 하는 디렉터리 `START_NAMESPACE`합니다.  
  
-   `#undef` 힌트는 `A2` 디렉터리에 대 한 힌트를 제거 `OBRACE` 및 `CBRACE` 에 `Debug` 힌트 파일 디렉터리입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트용 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)    
 [#define 지시문 (C/c + +)](../preprocessor/hash-define-directive-c-cpp.md)   
 [#undef 지시문 (C/c + +)](../preprocessor/hash-undef-directive-c-cpp.md)   
 [SAL 주석](../c-runtime-library/sal-annotations.md)   
 [메시지 맵](../mfc/reference/message-maps-mfc.md)   
 [메시지 맵 매크로](../atl/reference/message-map-macros-atl.md)   
 [개체 맵 매크로](../atl/reference/object-map-macros.md)