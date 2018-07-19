---
title: 1.4 준수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c1bde41491f456ff99b0cd0d1ccc8ab98508412
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687233"
---
# <a name="14-compliance"></a>1.4 규격
OpenMP C/c + + API의 구현은 *OpenMP 규격* 부록 C. 부록 A "," B "," D "," E "및" F는 및 인식 하 고 장 1, 2, 3, 4에 따라 해당이 설정의 요소를 모두의 의미 체계를 유지 하는 경우 목적 으로만 사용 정보와 사양의 포함 되지 않습니다. API의 하위 집합만 포함 하는 구현 OpenMP 규격이 아닙니다.  
  
 OpenMP C 및 c + + API는 확장 구현에서 지원 되는 기본 언어입니다. 기본 언어는이 문서에는 언어 구문 또는 확장에 표시를 지원 하지 않으면, OpenMP 구현은 지원 하기 위한 않아도 됩니다.  
  
 모든 표준 C 및 c + + 라이브러리 함수 및 기본 제공 함수 (즉, 함수는 컴파일러는 특정 기술 자료) 스레드로부터 안전 하 게 해야 합니다. 병렬 영역 내에 서로 다른 스레드에 의해 스레드로부터 안전한 함수를 사용 하는 동기화 되지 않은 정의 되지 않은 동작이 생성 되지 않습니다. 그러나 동작이 아닐 수 있습니다 직렬 지역 에서도 동일. (난수 생성 함수에는 예입니다.)  
  
 OpenMP C/c + + API 지정 동작은 특정 *구현 정의 합니다.* 표준에 맞는 OpenMP 구현이 정의 하 고 이러한 경우의 동작을 문서화 하는 데 필요 합니다. 참조 [부록 E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md), 97 구현에서 정의 된 동작의 목록에 대 한 페이지입니다.