---
title: 어설션 및 사용자 제공 메시지 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- user-supplied messages [C++], run time
- user-supplied messages [C++], preprocessor time
- '#error%2C assert%2C static_assert [C++]'
- user-supplied messages [C++], compile time
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e93798dadee3e4270d82eac84a794c6133c05c07
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411707"
---
# <a name="assertion-and-user-supplied-messages-c"></a>어설션 및 사용자 제공 메시지 (C++)
C + + 언어에서는 세 가지 오류 처리 메커니즘 데 도움이 되는 응용 프로그램을 디버깅할:는 [#error 지시문](../preprocessor/hash-error-directive-c-cpp.md), [static_assert](../cpp/static-assert.md) 키워드 및 [어설션 매크로, _assert, _ wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 매크로입니다. 세 가지 메커니즘 모두 오류 메시지를 제공하고 두 메커니즘은 소프트웨어 어설션도 테스트합니다. 소프트웨어 어설션은 프로그램의 특정 지점에서 true가 될 조건을 지정합니다. 컴파일 타임 어설션이 실패하는 경우 컴파일러에서 진단 메시지와 컴파일 오류를 생성합니다. 런타임 어설션이 실패하는 경우에는 운영 체제에서 진단 메시지를 제공하고 응용 프로그램을 닫습니다.  
  
## <a name="remarks"></a>설명  
 응용 프로그램의 수명은 전처리, 컴파일 및 런타임 단계로 구성됩니다. 각 오류 처리 메커니즘은 이러한 단계 중 하나가 수행되는 동안 사용할 수 있는 디버그 정보에 액세스합니다. 효과적으로 디버깅하려면 해당 단계에 대한 적절한 정보를 제공하는 메커니즘을 선택합니다.  
  
-   [#error 지시문](../preprocessor/hash-error-directive-c-cpp.md) 전처리 타임에 적용 됩니다. 이 지시문은 사용자 지정 메시지를 무조건 내보내고 컴파일이 오류와 함께 실패하도록 합니다. 메시지에는 전처리기 지시문으로 조작되는 텍스트가 포함될 수 있지만 모든 결과 식은 계산되지 않습니다.  
  
-   [static_assert](../cpp/static-assert.md) 선언 컴파일 타임에 적용 됩니다. 이 선언은 부울로 변환할 수 있는 사용자 지정 정수 계열 식으로 표현된 소프트웨어 어설션을 테스트합니다. 식이 0(false)으로 계산되는 경우 컴파일러는 사용자 지정 메시지를 발행하고 컴파일이 오류와 함께 실패합니다.  
  
     `static_assert` 선언은 디버깅 템플릿에 특히 유용합니다. 이는 템플릿 인수가 사용자 지정 식에 포함될 수 있기 때문입니다.  
  
-   [매크로, _assert, _wassert assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 런타임 시 적용 되는 매크로입니다. 이 매크로는 사용자 지정 식을 계산하며, 결과가 0인 경우 진단 메시지가 제공되고 응용 프로그램이 닫힙니다. 대부분의 매크로 같은[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 및 `_ASSERTE`,이 매크로 유사 하지만 서로 다른 시스템에 정의 된 또는 사용자 정의 진단 메시지를 발급 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [#error 지시문 (C/c + +)](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert Macro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [_ASSERT, _ASSERTE, _ASSERT_EXPR 매크로](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)   
 [static_assert](../cpp/static-assert.md)   
 [_STATIC_ASSERT 매크로](../c-runtime-library/reference/static-assert-macro.md)   
 [템플릿](../cpp/templates-cpp.md)