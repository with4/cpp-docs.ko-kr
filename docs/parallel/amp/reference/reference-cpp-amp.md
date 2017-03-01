---
title: "참조 (c + + AMP) | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
dev_langs:
- C++
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: cc654cedd8639377ab7011c91454f1508c730247
ms.lasthandoff: 02/24/2017

---
# <a name="reference-c-amp"></a>참조(C++ AMP)
이 섹션에는 c + + Accelerated Massive Parallelism (c + + AMP) 런타임에 대 한 참조 정보가 포함 되어 있습니다.  
  
> [!NOTE]
>  C++ 언어 표준에는 라이브러리와 같은 구현을 위해 밑줄(`_`) 문자로 시작하는 식별자의 사용이 예약되어 있습니다. 코드에 밑줄로 시작하는 이름을 사용하지 마세요. 해당 이름이 이 규칙을 따르는 코드 요소의 동작은 보장되지 않으며 이후 릴리스에서 변경될 수 있습니다. 이러한 이유로 이 설명서에서는 해당 코드 요소가 생략되었습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [동시성 Namespace (c + + AMP)](concurrency-namespace-cpp-amp.md)  
 클래스와 c + + 코드에서 데이터 병렬 하드웨어 가속을 사용 하도록 설정 하는 함수를 제공 합니다.  
  
 [Concurrency:: direct3d Namespace](concurrency-direct3d-namespace.md)  
 D3D 상호 운용성을 지 원하는 기능을 제공 합니다. 완벽 한 리소스 사용 하 여 D3D AMP 코드에는 계산에 대 한 중간 중복 복사본을 만들지 않고 amp에서 D3D 코드에서 만든 리소스의 사용이 가능 합니다. 증분 DirectX 응용 프로그램의 계산 집약적인 섹션을 가속화 하 D3D API를 사용 하 여 AMP 계산에서 생성 된 데이터에 c + + AMP를 사용할 수 있습니다.  
  
 [Concurrency:: fast_math Namespace](concurrency-fast-math-namespace.md)  
 가 작동 하는 `fast_math` 네임 스페이스 C99와 호환 되지 않습니다. 각 함수는 단 정밀도 버전만 제공 됩니다. 이러한 함수는 해당 함수에 보다 빠르게 있는 DirectX 내장 함수를 사용 하 여는 `precise_math` 네임 스페이스를 액셀러레이터의 연장된 배정밀 지원 필요 하지 않지만 덜 정확 하 게 구성 하 고 있습니다. 두 가지 버전의 소스 수준 코드와의 호환성 C99;에 대 한 각 함수 두 버전 모두 수행 하 고 단 정밀도 값을 반환 합니다.  
  
 [Concurrency:: graphics Namespace](concurrency-graphics-namespace.md)  
 그래픽 프로그래밍에 대 한 형식 및 설계 된 함수를 제공 합니다.  
  
 [Concurrency:: precise_math Namespace](concurrency-precise-math-namespace.md)  
 가 작동 하는 `precise_math` 네임 스페이스 C99 호환 됩니다. 각 함수의 버전을 단 정밀도 및 배정밀 모두 포함 됩니다. 이러한 함수-여기에 단 정밀도 함수 포함 됩니다.-액셀러레이터에서 확장 된 이중 정밀도 지원이 필요 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [C++ AMP(C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 C + + AMP은 일반적으로 개별 그래픽 카드에 그래픽 처리 장치 (GPU)로 제공 되는 데이터 병렬 하드웨어를 활용 하 여 c + + 코드의 실행을 가속화 합니다.






