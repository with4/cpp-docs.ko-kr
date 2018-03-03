---
title: "값 형식 명시적 Boxing | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- boxing, Visual C++
- __box keyword
- boxing
- boxing, __box keyword
- value types, boxed
ms.assetid: 9597c92f-a3fe-44af-ad80-f9d656847a35
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0c4725cdd7e8630131f77e02eedc2af14a469d20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implicit-boxing-of-value-types"></a>값 형식 명시적 boxing
값 형식의 boxing Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 언어 디자인에서는 입장에서 기능을 대신이 대화 상자 인 입장을 실제로 했습니다. 예를 들어, 원본에서 다중 상속 언어 디자인 Stroustrup이 만든 결정 파생된 클래스 생성자 내에서 가상 기본 클래스의 하위 개체를 초기화할 수 없습니다 및 따라서 언어 필요 하는 가상 기본으로 모든 클래스 클래스는 기본 생성자를 정의 해야 합니다. 이후의 모든 가상 파생 하 여 때 호출 되는 기본 생성자는  
  
 가상 기본 클래스 계층의 공유 가상 하위 개체의 초기화에 대 한 책임 이후의 각 파생 디자이너로 옮기면는입니다. 예를 들어 기본 클래스를 정의 하는 경우 초기화를 사용 하는 버퍼에 해당 버퍼의 사용자 지정 크기의 할당 수 인수로 전달할 수는 생성자에 있습니다. 다음 두 개의 가상 파생 제공, 전화할 `inputb` 및 `outputb`, 각 기본 클래스 생성자에 특정 값을 제공 합니다. 이제 파생는 `in_out` 클래스에서 `inputb` 및 `outputb`, 계산 될 수 눈에 띄도록 공유 가상 기본 클래스 하위 개체에 값을 모두 합니다.  
  
 따라서 원래 언어 디자인 stroustrup이 작성 멤버가 초기화 목록 내의 파생된 클래스 생성자의 가상 기본 클래스를 명시적으로 초기화할 수 없습니다. 문제를 해결이 동안 실제로 가상 기본 클래스의 초기화를 입증 impracticable 합니다. 에 프리웨어 버전의 nihcl 라는 SmallTalk 컬렉션 라이브러리 구현, Keith Gorlen National Institute의 상태를 유도 하는 것 보다 유연한 언어 디자인 he 'd Stroustrup의 원칙 음성 했습니다.  
  
 계층적 개체 지향 디자인 원칙은 파생된 클래스 관련 되어야 해당 직접 기본 클래스의 private이 아닌 구현에만 저장 됩니다. 가상 상속에 대 한 유연한 초기화 디자인을 지원 하기 위해 Stroustrup이이 원칙을 위반 했습니다. 계층 구조에서 가장 많이 파생 된 클래스에 계층 구조의 상관 없이 모든 가상 하위 개체 초기화에 대 한 책임을 가정 합니다. 예를 들어 `inputb` 및 `outputb` 가 둘 다를 명시적으로 직접 가상 기본 클래스를 초기화 합니다. 때 `in_out` 둘 다에서 파생 `inputb` 및 `outputb`, `in_out` 는 한 번의 초기화 가상 기본 클래스를 제거 하 고 초기화 하는 내에서 명시적 수행에 대 한 책임을 집니다 `inputb` 및 `outputb` 은 표시 되지 않습니다.  
  
 복잡 한 의미 체계 언어 개발자가 커밋되지만 필요한 유연성을 제공 합니다. 상태 비저장 하 고 간단히 인터페이스를 지정 하도록 허용 하는 가상 기본 클래스를 제한할 경우 이러한 부담 complication의 삭제 되기 합니다. 이 c + +에서 권장 되는 디자인 요소입니다. Clr 프로그래밍, 인터페이스 형식으로는 정책에 발생 합니다.  
  
 다음은 간단한 코드 예제-및 명시적 boxing이 경우에 필요 하지 않습니다.  
  
```  
// Managed Extensions for C++ requires explicit __box operation  
int my1DIntArray __gc[] = { 1, 2, 3, 4, 5 };  
Object* myObjArray __gc[] = {   
   __box(26), __box(27), __box(28), __box(29), __box(30)  
};  
  
Console::WriteLine( "{0}\t{1}\t{2}", __box(0),  
   __box(my1DIntArray->GetLowerBound(0)),  
   __box(my1DIntArray->GetUpperBound(0)) );  
```  
  
 볼 수 있듯이 boxing이 진행가 많이 있습니다. Visual c + +, 값 형식이 boxing은 암시적:  
  
```  
// new syntax makes boxing implicit  
array<int>^ my1DIntArray = {1,2,3,4,5};  
array<Object^>^ myObjArray = {26,27,28,29,30};  
  
Console::WriteLine( "{0}\t{1}\t{2}", 0,   
   my1DIntArray->GetLowerBound( 0 ),   
   my1DIntArray->GetUpperBound( 0 ) );  
```  
  
## <a name="see-also"></a>참고 항목  
 [값 형식 및 동작 (C + + /cli CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Boxing](../windows/boxing-cpp-component-extensions.md)