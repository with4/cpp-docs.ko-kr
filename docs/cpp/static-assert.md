---
title: static_assert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- static_assert_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ keywords, static_assert
- C2338
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1428d890fe079c7ac1fce175686e9776f9c21746
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="staticassert"></a>static_assert
컴파일 시 소프트웨어 어설션을 테스트합니다. 지정 된 상수 식이 `false`, 컴파일러, 제공 된 경우 지정된 된 메시지를 표시 하 고 컴파일은 C2338 오류와 함께 실패, 선언에 영향을 주지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```   
static_assert( constant-expression, string-literal );  

**Visual Studio 2017 and later:**
static_assert( constant-expression ); 
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`constant-expression`|부울로 변환할 수 있는 정수 계열 상수 식입니다.<br /><br /> 계산된 식이 0이면(false) `string-literal` 매개 변수가 표시되고 컴파일이 오류와 함께 실패합니다. 식이 0이 아니면(true) `static_assert` 선언은 영향을 미치지 않습니다.|  
|`string-literal`|`constant-expression` 매개 변수가 0인 경우 표시되는 메시지입니다. 메시지는 문자열의 문자는 [기본 문자 집합](../c-language/ascii-character-set.md) 있는 컴파일러의이 아니라 [멀티 바이트 또는 와이드 문자](../c-language/multibyte-and-wide-characters.md)합니다.|  
  
## <a name="remarks"></a>설명  
 `constant-expression` 의 매개 변수는 `static_assert` 나타냅니다는 *소프트웨어 어설션을*합니다. 소프트웨어 어설션은 프로그램의 특정 지점에서 true가 될 조건을 지정합니다. 조건이 true이면 `static_assert` 선언은 영향을 미치지 않습니다. 조건이 false이면 어설션이 실패하고 컴파일러가 `string-literal` 매개 변수의 메시지를 표시하며, 컴파일이 오류와 함께 실패합니다. Visual Studio 2017 이상 버전에서는 문자열 리터럴 매개 변수는 선택 사항입니다. 
  
 `static_assert` 선언은 컴파일할 때 소프트웨어 어설션을 테스트합니다. 반면,는 [매크로, _assert, _wassert assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 매크로 실행 시 소프트웨어 어설션을 테스트와의 시간 또는 런타임에 비용이 발생 합니다. `static_assert` 선언은 디버깅 템플릿에 특히 유용합니다. 이는 템플릿 인수가 `constant-expression` 매개 변수에 포함될 수 있기 때문입니다.  
  
 컴파일러는 `static_assert` 선언이 발생하면 구문 오류에 대한 선언을 검사합니다. 템플릿이 매개 변수에 종속되지 않을 경우 `constant-expression` 컴파일러는 매개 변수를 즉시 확인합니다. 그렇지 않으면 템플릿이 인스턴스화될 경우, 컴파일러가 `constant-expression` 매개 변수를 평가합니다. 그 결과, 컴파일러는 선언이 발생할 때 진단 메시지를 한 번 내보내고 템플릿이 인스턴스화될 때 다시 한 번 메시지를 내보낼 수 있습니다.  
  
 `static_assert` 키워드를 네임스페이스, 클래스 또는 블록 범위에 사용할 수 있습니다. `static_assert` 키워드는 네임스페이스 범위에서 사용할 수 있으므로 새 이름을 프로그램에 알리지 않더라도 기술적으로 선언됩니다.  
  
## <a name="description"></a>설명  
 다음 예제에서 `static_assert` 선언은 네임스페이스 범위를 갖습니다. 컴파일러가 `void *` 형식의 크기를 알고 있기 때문에 식이 즉시 계산됩니다.  
  
## <a name="example"></a>예제  
  
```  
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## <a name="description"></a>설명  
 다음 예제에서 `static_assert` 선언은 클래스 범위를 갖습니다. `static_assert` 는 템플릿 매개 변수 인지 확인 한 *일반 이전 데이터* (POD) 형식입니다. 컴파일러는 `static_assert`가 선언되면 그 선언을 검사하지만 `constant-expression` 클래스 템플릿이 `basic_string`에서 인스턴스화될 때까지 `main()` 매개 변수를 확인하지 않습니다.  
  
## <a name="example"></a>예제  
  
```  
#include <type_traits>  
#include <iosfwd>  
namespace std {  
template <class CharT, class Traits = std::char_traits<CharT> >  
class basic_string {  
    static_assert(std::is_pod<CharT>::value,  
                  "Template argument CharT must be a POD type in class template basic_string");  
    // ...  
    };  
}  
  
struct NonPOD {  
    NonPOD(const NonPOD &) {}  
    virtual ~NonPOD() {}  
};  
  
int main()  
{  
    std::basic_string<char> bs;  
}  
```  
  
## <a name="description"></a>설명  
 다음 예제에서 `static_assert` 선언은 블록 범위를 갖습니다. `static_assert`는 VMPage 구조체의 크기가 시스템의 가상 메모리 페이지 크기와 같은지 확인합니다.  
  
## <a name="example"></a>예제  
  
```  
#include <sys/param.h> // defines PAGESIZE  
class VMMClient {  
public:  
    struct VMPage { // ...   
           };  
    int check_pagesize() {  
    static_assert(sizeof(VMPage) == PAGESIZE,  
        "Struct VMPage must be the same size as a system virtual memory page.");  
    // ...  
    }  
// ...  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [어설션 및 사용자 제공 메시지 (c + +)](../cpp/assertion-and-user-supplied-messages-cpp.md)   
 [#error 지시문 (C/c + +)](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert Macro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [서식 파일](../cpp/templates-cpp.md)   
 [ASCII 문자 집합](../c-language/ascii-character-set.md)   
 [선언 및 정의](declarations-and-definitions-cpp.md)
