---
title: "참조(C++ AMP) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::Reference (C++ AMP)"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ Accelerated Massive Parallelism, 참조"
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 참조(C++ AMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 섹션에는 C\+\+ AMP\(Accelerated Massive Parallelism\) 런타임에 대한 참조 정보가 포함됩니다.  
  
> [!NOTE]
>  C\+\+ 언어 표준에는 라이브러리와 같은 구현을 위해 밑줄\(`_`\) 문자로 시작하는 식별자의 사용이 예약되어 있습니다.  코드에 밑줄로 시작하는 이름을 사용하지 마십시오.  이름에 이 규칙을 사용하는 코드 요소의 동작은 보장되지 않으며 이후 릴리스에서 변경될 수 있습니다.  따라서 이러한 코드 요소는 이 설명서에서 생략됩니다.  
  
## 단원 내용  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)  
 클래스와 C\+\+ 코드의 실행 데이터 병렬 하드웨어 가속화하는 클래스와 기능을 제공합니다.  
  
 [Concurrency::direct3d 네임스페이스](../../../parallel/amp/reference/concurrency-direct3d-namespace.md)  
 D3D 상호 운용성 지원 기능을 제공합니다.  중복된 임시 사본을 만들지 않고도 AMP 코드에서 계산을 위해 D3D 리소스를 완벽하게 사용하고 D3D 코드의 AMP에서 만든 리소스를 사용할 수 있습니다.  C\+\+ AMP를 사용하여 DirectX 응용 프로그램의 계산 집중적인 부분을 점차적으로 가속화하고 AMP 계산에서 생성된 데이터에 D3D API를 사용할 수 있습니다.  
  
 [Concurrency::fast\_math 네임스페이스](../../../parallel/amp/reference/concurrency-fast-math-namespace.md)  
 Functions in the `fast_math` 네임스페이스에 있는 함수는 C99 규격이 아닙니다.  각 함수의 단정밀도 버전에만 제공됩니다.  이러한 함수는 DirectX 내장 함수를 사용합니다. 이는 `precise_math` 네임스페이스의 해당 함수보다 빠르며 액셀러레이터에 대해 확장된 배정밀도 지원이 필요하지 않지만 정확도는 떨어집니다.  C99 코드를 사용하는 소스 수준 호환성을 위한 각 함수에 대한 버전은 두 개입니다. 두 버전 모두 단일 정밀도 값을 사용하고 반환합니다.  
  
 [Concurrency::graphics 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-namespace.md)  
 그래픽 프로그래밍 유형 및 기능을 제공합니다.  
  
 [Concurrency::precise\_math 네임스페이스](../../../parallel/amp/reference/concurrency-precise-math-namespace.md)  
 `precise_math` 네임스페이스에 있는 함수는 C99 규격입니다.  각 함수의 두 단정밀도 버전 및 배정밀도 버전이 모두 포함되어 있습니다.  단정밀도 기능을 포함하는 이러한 함수는 액셀러레이터에 대해 확장된 이중 정밀도 지원이 필요합니다.  
  
## 관련 단원  
 [C\+\+ AMP\(C\+\+ Accelerated Massive Parallelism\)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 C\+\+ AMP는 개별 그래픽 카드의 GPU\(그래픽 처리 장치\)로 자주 사용되는 데이터 병렬 하드웨어를 활용하여 C\+\+코드의 실행 속도를 높입니다.