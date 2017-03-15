---
title: "static_assert | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "C2338"
  - "static_assert_cpp"
  - "static_assert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "어설션[C++], static_assert"
  - "C++ 키워드, static_assert"
  - "C2338"
  - "static_assert"
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# static_assert
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컴파일 시 소프트웨어 어설션을 테스트합니다.  지정된 상수 식이 `false`인 경우 컴파일러는 지정된 메시지를 표시하고 컴파일은 C2338 오류와 함께 실패합니다. 그렇지 않을 경우 선언은 영향을 미치지 않습니다.  
  
## 구문  
  
```  
static_assert(   
    constant-expression,   
    string-literal   
);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`constant-expression`|부울로 변환할 수 있는 정수 계열 상수 식입니다.<br /><br /> 계산된 식이 0이면\(false\) `string-literal` 매개 변수가 표시되고 컴파일이 오류와 함께 실패합니다.  식이 0이 아니면\(true\) `static_assert` 선언은 영향을 미치지 않습니다.|  
|`string-literal`|`constant-expression` 매개 변수가 0인 경우 표시되는 메시지입니다.  이 메시지는 [멀티 바이트 또는 와이드 문자](../c-language/multibyte-and-wide-characters.md)가 아닌 컴파일러의 [기본 문자 집합에](../c-language/ascii-character-set.md) 있는 문자열입니다.|  
  
## 설명  
 `static_assert`의 `constant-expression` 매개 변수는 *소프트웨어 어설션*을 나타냅니다.  소프트웨어 어설션은 프로그램의 특정 지점에서 true가 될 조건을 지정합니다.  조건이 true이면 `static_assert` 선언은 영향을 미치지 않습니다.  조건이 false이면 어설션이 실패하고 컴파일러가 `string-literal` 매개 변수의 메시지를 표시하며, 컴파일이 오류와 함께 실패합니다.  
  
 `static_assert` 선언은 컴파일할 때 소프트웨어 어설션을 테스트합니다.  반대로, [assert Macro, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 매크로는 런타임 시 소프트웨어 어설션을 테스트하고 공간 또는 시간의 런타임 비용을 발생시킵니다.  `static_assert` 선언은 디버깅 템플릿에 특히 유용합니다. 이는 템플릿 인수가 `constant-expression` 매개 변수에 포함될 수 있기 때문입니다.  
  
 컴파일러는 `static_assert` 선언이 발생하면 구문 오류에 대한 선언을 검사합니다.  템플릿이 매개 변수에 종속되지 않을 경우 `constant-expression` 컴파일러는 매개 변수를 즉시 확인합니다.  그렇지 않으면 템플릿이 인스턴스화될 경우, 컴파일러가 `constant-expression` 매개 변수를 평가합니다.  그 결과, 컴파일러는 선언이 발생할 때 진단 메시지를 한 번 내보내고 템플릿이 인스턴스화될 때 다시 한 번 메시지를 내보낼 수 있습니다.  
  
 `static_assert` 키워드를 네임스페이스, 클래스 또는 블록 범위에 사용할 수 있습니다. `static_assert` 키워드는 네임스페이스 범위에서 사용할 수 있으므로 새 이름을 프로그램에 알리지 않더라도 기술적으로 선언됩니다.  
  
## 설명  
 다음 예제에서 `static_assert` 선언은 네임스페이스 범위를 갖습니다.  컴파일러가 `void *` 형식의 크기를 알고 있기 때문에 식이 즉시 계산됩니다.  
  
## 예제  
  
```  
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## 설명  
 다음 예제에서 `static_assert` 선언은 클래스 범위를 갖습니다.  `static_assert`는 템플릿 매개 변수가 *POD*\(plain old data\) 형식인지 확인합니다.  컴파일러는 `static_assert`가 선언되면 그 선언을 검사하지만 `basic_string` 클래스 템플릿이 `main()`에서 인스턴스화될 때까지 `constant-expression` 매개 변수를 확인하지 않습니다.  
  
## 예제  
  
```  
#include <type_traits>  
#include <iosfwd>  
namespace std {  
template <class CharT, class Traits = std::char_traits<CharT> >  
class basic_string {  
    static_assert(tr1::is_pod<CharT>::value,  
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
  
## 설명  
 다음 예제에서 `static_assert` 선언은 블록 범위를 갖습니다.  `static_assert`는 VMPage 구조체의 크기가 시스템의 가상 메모리 페이지 크기와 같은지 확인합니다.  
  
## 예제  
  
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
  
## 참고 항목  
 [어설션 및 사용자 제공 메시지 \(C\+\+\)](../cpp/assertion-and-user-supplied-messages-cpp.md)   
 [\#error 지시문](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert Macro, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [템플릿](../cpp/templates-cpp.md)   
 [ASCII 문자 집합](../c-language/ascii-character-set.md)   
 [선언](../misc/declarations.md)