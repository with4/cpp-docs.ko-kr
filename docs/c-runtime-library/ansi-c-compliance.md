---
title: "ANSI C 규격 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Ansi
dev_langs: C++
helpviewer_keywords:
- underscores, leading
- compatibility [C++], ANSI C
- compliance with ANSI C
- conventions [C++], Microsoft extensions
- underscores
- naming conventions [C++], Microsoft library
- ANSI [C++], C standard
- Microsoft extensions naming conventions
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f9c8831ef19e14d5d65ae39abde9af8ed669bb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ansi-c-compliance"></a>ANSI C 규격
런타임 시스템(예: 함수, 매크로, 상수, 변수 및 형식 정의)의 모든 Microsoft 고유의 식별자에 대한 명명 규칙은 ANSI 규격입니다. 이 설명서에서는 ANSI/ISO C 표준을 따르는 모든 런타임 함수를 ANSI 호환으로 기록합니다. ANSI 호환 응용 프로그램은 이러한 ANSI 호환 함수를 사용해야 합니다.  
  
 Microsoft 고유의 함수 및 전역 변수 이름은 단일 밑줄로 시작합니다. 이러한 이름은 코드의 범위 내에서 로컬로만 재정의할 수 있습니다. 예를 들어 Microsoft 런타임 헤더 파일을 포함할 때 같은 이름의 지역 변수를 선언함으로써 로컬에서 `_open`이라는 이름의 Microsoft 고유의 함수를 재정의할 수 있습니다. 그러나 고유한 전역 함수나 전역 변수에는 이 이름을 사용할 수 없습니다.  
  
 Microsoft 매크로 및 매니페스트 상수의 이름은 두 개의 밑줄로 시작하거나 단일 선행 밑줄과 바로 이어지는 대문자로 시작합니다. 이러한 식별자의 범위는 절대입니다. 예를 들어 이러한 이유로 Microsoft 식별자 **_UPPER**를 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [호환성](../c-runtime-library/compatibility.md)