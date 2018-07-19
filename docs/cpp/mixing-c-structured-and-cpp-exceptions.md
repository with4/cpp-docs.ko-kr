---
title: (구조적) C 및 c + + 예외 혼합 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 495f0fe9faf0c75257f2ac7bbe0a3457438ffdf9
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37942044"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C(구조적) 및 C++ 예외 혼합
이식성이 높은 코드를 작성하려는 경우 C++ 프로그램에서 구조화된 예외 처리를 사용하지 않는 것이 좋습니다. 그러나 경우가 있습니다 사용 하 여 컴파일하도록 **/EHa** 구조적된 예외와 c + + 소스 코드를 조합 하 고 두 종류의 예외를 처리 하기 위한 일부 기능이 필요 합니다. C + + 코드에서 throw 된 예외를 처리할 수 없는 구조적된 예외 처리기 개체 또는 형식화 된 예외의 개념이 있어 그러나 c + + **catch** 처리기는 구조화 된 예외를 처리할 수 있습니다. 같은 c + + 예외 처리 구문을으로 (**시도**, **throw**합니다 **catch**)는 C 컴파일러의 경우 구조적된 예외 처리 구문을에서 허용 되지 않습니다 (**__try** 하십시오 **__except**, **__finally**) c + + 컴파일러에서 지원 됩니다.  
  
 참조 [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) c + + 예외로 구조적된 예외 처리에 대 한 정보에 대 한 합니다.  
  
 구조화된 예외와 C++ 예외를 혼합하려면 다음을 참조하십시오.  
  
1.  C++ 예외 및 구조화된 예외는 동일한 함수 내에서 혼합될 수 없습니다.  
  
2.  종료 처리기 (**__finally** 블록) 예외가 throw 된 후 해제 하는 동안에 항상 실행 됩니다.  
  
3.  C + + 예외 처리를 catch 할 수 및 preserve로 컴파일된 모든 모듈의 의미 체계를 해제 합니다 [/EH](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션 (이 옵션 해제 의미 체계를 사용 하도록 설정).  
  
4.  소멸자 함수가 모든 개체에 대해 호출하지 않는 일부 경우가 있을 수 있습니다. 예를 들어 초기화되지 않은 함수 포인터를 통해 함수 호출을 시도하는 동안 구조화된 예외가 발생한 경우 해당 함수는 호출 전 생성된 매개 변수 개체를 사용하고 이러한 개체에는 스택을 해제하는 동안 호출된 소멸자가 없습니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [C + + 프로그램에서 setjmp 또는 longjmp 사용](../cpp/using-setjmp-longjmp.md)  
  
-   [SEH와 c + + EH의 차이점](../cpp/exception-handling-differences.md)  
  
## <a name="see-also"></a>참고 항목  
 [C++ 예외 처리](../cpp/cpp-exception-handling.md)