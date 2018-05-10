---
title: 참조 (c + + AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
dev_langs:
- C++
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c39528bf3b1e6c9235e4b2daabcd8bbddd0d52f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="reference-c-amp"></a>참조(C++ AMP)
이 섹션에는 c + + Accelerated Massive Parallelism (c + + AMP) 런타임에 대 한 참조 정보가 포함 되어 있습니다.  
  
> [!NOTE]
>  C++ 언어 표준에는 라이브러리와 같은 구현을 위해 밑줄(`_`) 문자로 시작하는 식별자의 사용이 예약되어 있습니다. 코드에 밑줄로 시작하는 이름을 사용하지 마세요. 해당 이름이 이 규칙을 따르는 코드 요소의 동작은 보장되지 않으며 이후 릴리스에서 변경될 수 있습니다. 이러한 이유로 이 설명서에서는 해당 코드 요소가 생략되었습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)  
 클래스와 c + + 코드에서 데이터 병렬 하드웨어 가속을 사용 하도록 설정 하는 함수를 제공 합니다.  
  
 [Concurrency::direct3d 네임스페이스](concurrency-direct3d-namespace.md)  
 D3D 상호 운용성을 지 원하는 기능을 제공 합니다. 중간 중복 복사본을 만들지 않고 AMP에 D3D 코드에서 만들어진 리소스 사용 및 AMP 코드에는 계산에 대 한 D3D 리소스의 원활 하 게 사용할 수 있도록 합니다. C + + AMP를 증분식으로 DirectX 응용 프로그램의 계산 집약적인 섹션을 가속화 하 고 D3D API를 사용 하 여 AMP 계산에서 생성 된 데이터를 사용할 수 있습니다.  
  
 [Concurrency::fast_math 네임스페이스](concurrency-fast-math-namespace.md)  
 함수는 `fast_math` 네임 스페이스는 C99 규격이 아닙니다. 각 함수의 단 정밀도 버전에만 제공 됩니다. 이러한 함수에서 해당 함수 보다 더 빠른 되는 DirectX 내장 함수를 사용 하 여는 `precise_math` 네임 스페이스는 가속기에서 연장된 배정도 지원 필요 하지 않지만 덜 시행 되 고 있습니다. 두 가지 버전의 소스 수준 C99 코드;와 호환성에 대 한 각 함수 두 버전 모두 수행 하 고 단 정밀도 값을 반환 합니다.  
  
 [Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)  
 그래픽 프로그래밍에 대 한 형식 및 설계 된 함수를 제공 합니다.  
  
 [Concurrency::precise_math 네임스페이스](concurrency-precise-math-namespace.md)  
 함수는 `precise_math` 네임 스페이스는 C99 규정을 준수 합니다. 각 함수의 버전을 단 정밀도 배정밀 모두 포함 됩니다. 이러한 함수-여기에 단 정밀도 함수-액셀러레이터에서 확장 된 배정도 지원이 필요 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [C++ AMP(C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 C + + AMP 계속 일반적으로 개별 그래픽 카드에 그래픽 처리 장치 (GPU)으로 제공 되는 데이터 병렬 하드웨어를 활용 함으로써 c + + 코드를 실행 합니다.





