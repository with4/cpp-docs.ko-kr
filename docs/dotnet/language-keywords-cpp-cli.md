---
title: "언어 키워드 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: keywords [C++]
ms.assetid: 021013b2-70ac-4df9-aa77-4af1c67a1a67
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e1107ad45feaae470ed2a7481f80bb17c389042d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="language-keywords-ccli"></a>언어 키워드(C++/CLI)
여러 언어 키워드는 Visual c + + Managed Extensions for c + + 변경 합니다.  
  
 새 Visual c + + 구문에서 두 개의 밑줄이 모든 키워드에서 접두사로 제거 됩니다 (한 가지 예외로: `__identifier` 유지). 예를 들어 속성이 이제로 선언 `property`이 아니라 `__property`합니다.  
  
 Managed Extensions에는 두 개의 밑줄 접두사를 사용 하기 위한 두 가지 기본 이유 했습니다.  
  
-   이것은 ISO c + + 표준에 로컬 확장을 제공 하는 중 일치 메서드입니다. Managed Extensions 디자인의 주요 목표 새 키워드 및 토큰과 같은 표준 언어와의 비 호환성을 제공 하지는 하는 것 이었습니다. 이 따라서 관리 되는 참조 형식의 개체의 선언에 대 한 포인터 구문 선택 동기 부여는 상당 부분 있었습니다.  
  
-   여기서 이중 밑줄이 호환 되 측면 이외의 사용 중인 언어 사용자의 기존 코드 베이스를 침해 하지 않는다는 이기도 합니다. 이 관리 되는 확장 디자인의 두 번째 주요 목표는 이었습니다.  
  
 두 개의 밑줄을 제거 하는 있음에도 불구 하 고 Microsoft 방침은 남아 있습니다. 그러나 지원 CLR 동적 개체 모델은 새롭고 강력한 프로그래밍 패러다임을 나타냅니다. 이 새로운 패러다임을 지원 하려면 자체 고급 키워드 및 토큰 필요 합니다. 우리는 완벽 하 게 표현이 새로운 패러다임 통합 하 고 표준 언어를 지 원하는 동안 제공 하고자 합니다. 새로운 구문 디자인에는 이러한 두 개의 서로 다른 개체 모델의 첫 번째 클래스 프로그래밍 환경을 제공합니다.  
  
 마찬가지로,을 이러한 새로운 언어 키워드의 기울였습니다 침해 하지 않습니다. 이것은 컨텍스트 및 공백이 포함 된 키워드를 사용 하 여 달성 되었습니다. 새로운 언어 구문을 살펴보기 전에 이러한 두 가지 특수 한 키워드 버전 이해 하기 보겠습니다.  
  
 상황별 키워드 특정 프로그램 컨텍스트 내에서 특별 한 의미가 있습니다. 예를 들어 일반적인 프로그램에서 `sealed` 는 일반 식별자로 처리 됩니다. 그러나 관리 되는 참조 클래스 형식의 선언 부분 내에서 발생할 때 해당 클래스 선언의 컨텍스트 내에서 키워드로 처리 됩니다. 이 영향을 최소화 잠재적인 침투 적 어떤 언어에서의 새로운 키워드를 도입 함으로써는 기존 코드 베이스를 가진 사용자에 게 매우 중요 생각 될 것입니다. 같은 시간에 사용자를의 새로운 기능을 관리 하는 확장 가능한 받았으나 문제가 추가 언어 기능의-첫 번째 클래스 경험이 있습니다. 방법의 예에 대 한 `sealed` 사용 참조 [관리 되는 클래스 형식 선언의](../dotnet/declaration-of-a-managed-class-type.md)합니다.  
  
 공백이 포함 된 키워드와 같은 `value class`의 컨텍스트 키워드는 특별 한 경우. Existing 키워드는 공백으로 구분 하 여 컨텍스트 한정자 쌍 것입니다. 쌍은 두 개의 별도 키워드가 아니라 단일 단위로 취급 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + /CLI 마이그레이션 입문](../dotnet/cpp-cli-migration-primer.md)   
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)