---
title: 명시적 인스턴스화 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4925a60843ada350a2795709d9257ab796616a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415189"
---
# <a name="explicit-instantiation"></a>명시적 인스턴스화
명시적 인스턴스화를 통해 코드에서 실제로 사용하지 않고 템플릿 기반 클래스 또는 함수의 인스턴스를 만들 수 있습니다. 라이브러리 (.lib) 파일 배포에 대 한 템플릿을 사용 하는 만들 때 유용한 것은, 인스턴스화되지 않은 템플릿 정의 개체 (.obj) 파일에 배치 되지 않은 합니다.  
  
 다음 코드는 `MyStack` 변수 및 6개 항목에 대해 `int`을 명시적으로 인스턴스화합니다.  
  
```cpp  
template class MyStack<int, 6>;  
```  
  
 이 명령문은 개체에 대한 저장소 없이 `MyStack`의 인스턴스를 만듭니다. 모든 멤버에 대한 코드가 생성됩니다.  
  
 다음 줄은 생성자 멤버 함수만 명시적으로 인스턴스화합니다.  
  
```cpp  
template MyStack<int, 6>::MyStack( void );  
```  
  
 예제에 표시 된 대로 다시 선언 특정 형식 인수를 사용 하 여 함수 템플릿을 명시적으로 인스턴스화할 수 있습니다 [함수 템플릿 인스턴스화](../cpp/function-template-instantiation.md)합니다.  
  
 사용할 수는 `extern` 멤버의 자동 인스턴스화를 방지 하려면 키워드입니다. 예를 들어:  
  
```cpp  
extern template class MyStack<int, 6>;  
```  
  
 마찬가지로 특정 멤버를 외부 및 인스턴스화되지 않음으로 표시할 수 있습니다.  
  
```cpp  
extern template MyStack<int, 6>::MyStack( void );  
```  
  
 컴파일러가 둘 이상의 개체 모듈에서 같은 인스턴스화 코드를 생성하지 않도록 하려면 `extern` 키워드를 사용합니다. 함수가 호출되면 하나 이상의 연결된 모듈에서 지정된 명시적 템플릿 매개 변수를 사용하여 템플릿 함수를 인스턴스화해야 합니다. 그렇지 않으면 프로그램을 빌드할 때 링커 오류가 발생합니다.  
  
> [!NOTE]
>  `extern` 키워드는 특수화에서 클래스 본문 외부에서 정의 된 멤버 함수에만 적용 됩니다. 클래스 선언 안에 정의 된 함수가 인라인 함수 간주 되며 항상 인스턴스화됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수 템플릿](../cpp/function-templates.md)