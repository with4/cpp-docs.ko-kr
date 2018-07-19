---
title: 캐스팅 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- casting [C++]
- coercion [C++]
- virtual functions [C++], in derived classes [C++]
- static cast operator
- dynamic cast operator
- polymorphic classes [C++]
- classes [C++], polymorphism
ms.assetid: 3dbeb06e-2f4b-4693-832d-624bc8ec95de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07abd7c6a6a5c646dade15299fe6cfe78d9ff1d8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411730"
---
# <a name="casting"></a>캐스팅
C++ 언어에서는 클래스가 가상 함수를 포함하는 기본 클래스에서 파생되는 경우 해당 기본 클래스 형식에 대한 포인터를 사용하여 파생 클래스 개체에 있는 가상 함수의 구현을 호출할 수 있습니다. 가상 함수를 포함하는 클래스를 "다형 클래스"라고도 합니다.  
  
 파생 클래스에는 해당 클래스가 파생되는 모든 기본 클래스의 정의가 완전히 포함되어 있으므로 포인터를 이러한 기본 클래스에 대한 클래스 계층 구조 위로 캐스팅해도 됩니다. 기본 클래스에 포인터를 지정하면 포인터를 계층 구조 아래로 캐스팅해도 안전할 수 있습니다. 포인터가 지정 중인 개체가 실제로 기본 클래스에서 파생된 형식이면 안전합니다. 이 경우 실제 개체는 "완전한 개체"라고 합니다. 기본 클래스의 포인터는 완전한 개체의 "하위 개체"를 가리킨다고 합니다. 예를 들어 다음 그림과 같은 클래스 계층 구조를 고려해 보겠습니다.  
  
 ![클래스 계층 구조](../cpp/media/vc38zz1.gif "vc38ZZ1")  
클래스 계층 구조  
  
 `C` 형식의 개체는 다음 그림과 같이 시각화될 수 있습니다.  
  
 ![Sub 포함 클래스 C&#45;개체 B 및 A](../cpp/media/vc38zz2.gif "vc38ZZ2")  
B 하위 개체 및 A 하위 개체를 포함하는 C 클래스  
  
 `C` 클래스의 인스턴스를 제공하면 `B` 하위 개체 및 `A` 하위 개체가 있습니다. `C` 및 `A` 하위 개체를 포함한 `B`의 인스턴스는 "완전한 개체"입니다.  
  
 런타임 형식 정보를 사용하면 실제로 포인터가 완전한 개체를 가리키며 해당 계층 구조에서 다른 개체를 가리키도록 안전하게 캐스팅될 수 있는지 여부를 확인할 수 있습니다. [dynamic_cast](../cpp/dynamic-cast-operator.md) 연산자는 이러한 캐스팅 형식을 만드는 데 사용할 수 있습니다. 이러한 연산자는 안전하게 작업하는 데 필요한 런타임 검사도 수행합니다.  
  
 비 다형 형식의 변환에 사용할 수 있습니다는 [static_cast](../cpp/static-cast-operator.md) 연산자 (이 여기서는 정적 및 동적 캐스팅 변환 간의 및 각 사용 하기에 적합 한 차이 설명 하는 데 사용).  
  
 이 단원에서는 다음 항목에 대해 설명합니다.  
  
-   [캐스팅 연산자](../cpp/casting-operators.md)  
  
-   [런타임 형식 정보](../cpp/run-time-type-information.md)  
  
## <a name="see-also"></a>참고 항목  
 [식](../cpp/expressions-cpp.md)