---
title: 컴파일러 한계 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc7cd26add0a46bab8df7669fb6dfb6060b0010e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412139"
---
# <a name="compiler-limits"></a>컴파일러 한계
C++ 표준에서는 다양한 언어 구문에 대한 한도를 권장합니다. 다음은 Visual C++ 컴파일러에서 권장된 한도를 구현하지 않은 경우의 목록입니다. 첫 번째 수는 ISO C++ 11 표준(INCITS/ISO/IEC 14882-2011[2012], Annex B)으로 설정된 한도이고 두 번째 수는 Visual C++로 구현된 한도입니다.  
  
-   복합 문, 반복 제어 구조체 및 선택의 중첩 수준 제어 구조-c + + 표준: 256, Visual c + + 컴파일러: 중첩 된 문 다르지만 일반적으로 100 및 110 단계 조합에 따라 달라 집니다.  
  
-   단일 매크로 정의-c + + 표준의 매개 변수: 256, Visual c + + 컴파일러: 127입니다.  
  
-   하나의 매크로 호출의에서 인수-c + + 표준: 256, Visual c + + 컴파일러 127 개.  
  
-   문자는 문자에는 리터럴 또는 와이드 문자열 리터럴 (연결)-후 문자열 c + + 표준: 65536, Visual c + + 컴파일러: 65, 535 단일 바이트 문자를 포함 한는 `null` 종결자가 오는, 및는 를포함하여32767더블바이트문자`null` 종결자입니다.  
  
-   중첩 된 클래스, 구조체 또는 공용 구조체 정의에 단일 수준의 `struct-declaration-list` -c + + 표준: 256, Visual c + + 컴파일러: 16입니다.  
  
-   멤버 이니셜라이저 생성자 정의-c + + 표준: 6144, Visual c + + 컴파일러: 6144 개 이상 있습니다.  
  
-   범위 한정자 개수의 하나 이상의 식별자-c + + 표준: 256, Visual c + + 컴파일러: 127입니다.  
  
-   중첩 된 `extern` 사양-c + + 표준: 1024, Visual c + + 컴파일러: 9 (암시적를 세 지 않고 `extern` 10, 암시적를 계산 하는 경우 나 전역 범위에 사양 `extern` 전역 범위에서 지정...  
  
-   표준 c + +-템플릿 선언의 템플릿 인수: 1024, Visual c + + 컴파일러: 2046 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [비표준 동작](../cpp/nonstandard-behavior.md)