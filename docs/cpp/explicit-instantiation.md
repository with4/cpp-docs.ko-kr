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
ms.openlocfilehash: 834a71f5fd670874fd7dad5a77cb89a837119c2d
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940617"
---
# <a name="explicit-instantiation"></a>명시적 인스턴스화
명시적 인스턴스화를 통해 코드에서 실제로 사용하지 않고 템플릿 기반 클래스 또는 함수의 인스턴스를 만들 수 있습니다. 이기 때문에 유용한 라이브러리 (.lib) 파일 배포에 대 한 템플릿을 사용 하는 만드는 경우 인스턴스화되지 않은 템플릿 정의 개체 (.obj) 파일에 포함 되지 않습니다.  
  
 이 코드에서 명시적으로 인스턴스화합니다 `MyStack` 에 대 한 **int** 변수 및 6 개 항목:  
  
```cpp  
template class MyStack<int, 6>;  
```  
  
 이 명령문은 개체에 대한 저장소 없이 `MyStack`의 인스턴스를 만듭니다. 모든 멤버에 대한 코드가 생성됩니다.  
  
 다음 줄은 생성자 멤버 함수만 명시적으로 인스턴스화합니다.  
  
```cpp  
template MyStack<int, 6>::MyStack( void );  
```  
  
 예제에 나와 있는 것 처럼 다시 선언할 수, 특정 형식 인수를 사용 하 여 함수 템플릿을 명시적으로 인스턴스화할 수 있습니다 [함수 템플릿 인스턴스화](../cpp/function-template-instantiation.md)합니다.  
  
 사용할 수는 **extern** 멤버 자동 인스턴스화를 방지 하는 키워드입니다. 예를 들어:  
  
```cpp  
extern template class MyStack<int, 6>;  
```  
  
 마찬가지로 특정 멤버를 외부 및 인스턴스화되지 않음으로 표시할 수 있습니다.  
  
```cpp  
extern template MyStack<int, 6>::MyStack( void );  
```  
  
 사용할 수는 **extern** 컴파일러 둘 이상의 개체 모듈에서 같은 인스턴스화 코드를 생성 하지 않도록 하려면 키워드입니다. 함수가 호출되면 하나 이상의 연결된 모듈에서 지정된 명시적 템플릿 매개 변수를 사용하여 템플릿 함수를 인스턴스화해야 합니다. 그렇지 않으면 프로그램을 빌드할 때 링커 오류가 발생합니다.  
  
> [!NOTE]
>  합니다 **extern** 특수화에는 키워드를 클래스 본문 외부에서 정의 된 멤버 함수에만 적용 됩니다. 클래스 선언 안에 정의 된 함수가 인라인 함수 간주 되며 항상 인스턴스화됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수 템플릿](../cpp/function-templates.md)