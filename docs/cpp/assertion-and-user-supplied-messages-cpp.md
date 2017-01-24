---
title: "어설션 및 사용자 제공 메시지 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "#error%2C assert%2C static_assert[C++]"
  - "사용자 제공 메시지[C++], 컴파일 타임"
  - "사용자 제공 메시지[C++], 전처리기 시간"
  - "사용자 제공 메시지[C++], 런타임"
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 어설션 및 사용자 제공 메시지 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 언어에서는 응용 프로그램을 디버깅하는 데 도움이 되는 세 가지 오류 처리 메커니즘인 [\#error 지시문](../preprocessor/hash-error-directive-c-cpp.md), [static\_assert](../cpp/static-assert.md) 키워드 및 [assert Macro, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 매크로를 지원합니다.  세 가지 메커니즘 모두 오류 메시지를 제공하고 두 메커니즘은 소프트웨어 어설션도 테스트합니다.  소프트웨어 어설션은 프로그램의 특정 지점에서 true가 될 조건을 지정합니다.  컴파일 타임 어설션이 실패하는 경우 컴파일러에서 진단 메시지와 컴파일 오류를 생성합니다.  런타임 어설션이 실패하는 경우에는 운영 체제에서 진단 메시지를 제공하고 응용 프로그램을 닫습니다.  
  
## 설명  
 응용 프로그램의 수명은 전처리, 컴파일 및 런타임 단계로 구성됩니다.  각 오류 처리 메커니즘은 이러한 단계 중 하나가 수행되는 동안 사용할 수 있는 디버그 정보에 액세스합니다.  효과적으로 디버깅하려면 해당 단계에 대한 적절한 정보를 제공하는 메커니즘을 선택합니다.  
  
-   [\#error 지시문](../preprocessor/hash-error-directive-c-cpp.md)은 전처리 타임에 적용됩니다.  이 지시문은 사용자 지정 메시지를 무조건 내보내고 컴파일이 오류와 함께 실패하도록 합니다.  메시지에는 전처리기 지시문으로 조작되는 텍스트가 포함될 수 있지만 모든 결과 식은 계산되지 않습니다.  
  
-   [static\_assert](../cpp/static-assert.md) 선언은 컴파일 타임에 적용됩니다.  이 선언은 부울로 변환할 수 있는 사용자 지정 정수 계열 식으로 표현된 소프트웨어 어설션을 테스트합니다.  식이 0\(false\)으로 계산되는 경우 컴파일러는 사용자 지정 메시지를 발행하고 컴파일이 오류와 함께 실패합니다.  
  
     `static_assert` 선언은 디버깅 템플릿에 특히 유용합니다. 이는 템플릿 인수가 사용자 지정 식에 포함될 수 있기 때문입니다.  
  
-   [assert Macro, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 매크로는 런타임에 적용됩니다.  이 매크로는 사용자 지정 식을 계산하며, 결과가 0인 경우 진단 메시지가 제공되고 응용 프로그램이 닫힙니다.  [\_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), `_ASSERTE` 등의 다른 매크로는 대부분 이 매크로와 유사하지만 다른 시스템 정의 또는 사용자 정의 진단 메시지를 제공합니다.  
  
## 참고 항목  
 [\#error 지시문](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert Macro, \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [\_ASSERT, \_ASSERTE, \_ASSERT\_EXPR 매크로](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)   
 [static\_assert](../cpp/static-assert.md)   
 [\_STATIC\_ASSERT 매크로](../c-runtime-library/reference/static-assert-macro.md)   
 [템플릿](../cpp/templates-cpp.md)