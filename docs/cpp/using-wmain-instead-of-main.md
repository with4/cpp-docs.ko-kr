---
title: Main 대신 wmain 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- wmain
dev_langs:
- C++
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e093bc006a5b2c8ebba6fd2967a2a549d46c574
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466051"
---
# <a name="using-wmain-instead-of-main"></a>main 대신 wmain 사용
## <a name="microsoft-specific"></a>Microsoft 전용  
 유니코드 프로그래밍 모델에서의 와이드 문자 버전을 정의할 수 있습니다는 `main` 함수입니다. 사용 하 여 **wmain** 대신 `main` 유니코드 사양을 준수 하는 이식 가능한 코드를 작성 하려는 경우.  
  
 정식 매개 변수를 선언 **wmain** 에 유사한 형식을 사용 하 여 `main`입니다. 와이드 문자 인수 또는 와이드 문자 환경 포인터를 프로그램에 전달할 수 있습니다. 합니다 *argv* 하 고 *envp* 매개 변수를 **wmain** 형식의 `wchar_t*`합니다.  
  
 프로그램을 사용 하는 경우는 `main` 함수는 멀티 바이트 문자 환경이 프로그램 시작 시 운영 체제에서 만들어집니다. 환경의 와이드 문자 복사본은 필요한 경우에 생성 됩니다 (예를 들어를 호출 하 여 합니다 [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) 또는 [_wputenv](../c-runtime-library/reference/putenv-wputenv.md) 함수). `_wputenv` 또는 `_wgetenv`의 첫 번째 호출에서 MBCS 환경이 이미 있는 경우 해당 와이드 문자 문자열 환경이 만들어지고 `_wenviron` 전역 변수의 와이드 문자 버전인 `_environ` 전역 변수에 의해 가리킵니다. 이 시점에서 환경 복사본 두 개(MBCS와 유니코드)가 동시에 존재하며 프로그램의 수명 내내 운영 체제에 의해 유지 관리됩니다.  
  
 마찬가지로, 프로그램을 사용 하는 경우는 **wmain** 함수는 MBCS (ASCII) 환경이 첫 번째 호출에서 만들어집니다 `_putenv` 또는 `getenv`,이 가리키는 및는 `_environ` 전역 변수입니다.  
  
 MBCS 환경에 대 한 자세한 내용은 참조 하세요. [싱글바이트 및 멀티 바이트 문자 집합](../c-runtime-library/single-byte-and-multibyte-character-sets.md) 에 *런타임 라이브러리 참조 합니다.*  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [main: 프로그램 시작](../cpp/main-program-startup.md)