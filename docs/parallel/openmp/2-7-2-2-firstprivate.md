---
title: 2.7.2.2 firstprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b8e44ca52ba1f76d5b3791a1d08301bf06e7eab
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687402"
---
# <a name="2722-firstprivate"></a>2.7.2.2 firstprivate
**firstprivate** 절에서 제공 하는 기능의 상위 집합을 제공 된 **개인** 절. 구문은 **firstprivate** 절은 다음과 같습니다.  
  
```  
firstprivate(variable-list)  
```  
  
 에 지정 된 변수 *변수 목록* 가 **개인** 절에서 의미 체계에 설명 된 대로 [섹션 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 페이지 25입니다. 초기화 또는 생성 하는 구문에서 스레드의 실행 전에 스레드당 한 번 수행 된 하는 경우 발생 합니다. 에 대 한는 **firstprivate** 병렬 구문에 절을 새 전용 개체의 초기 값은 처리할 스레드는 병렬 구문 바로 앞에 있는 원래 개체의 값입니다. 에 대 한는 **firstprivate** 작업 공유 구문에 절을 작업 공유 생성자를 실행 하는 각 스레드에 대 한 새 전용 개체의 초기 값은 시간에 지점 이전의 존재 하는 원래 개체의 값입니다 동일한 스레드에서 작업 공유 생성자에서 발생 합니다. 또한 c + + 개체에 대 한 각 스레드에 대 한 새 전용 개체는 원본 개체에서 복사 생성 합니다.  
  
 시의 제한 된 **firstprivate** 절은 다음과 같습니다.  
  
-   에 지정 된 변수는 **firstprivate** 절 불완전 한 형식 또는 참조 형식이 있어야 합니다.  
  
-   으로 지정 된 클래스 형식의 변수에 **firstprivate** 액세스 가능 하며 명확한 복사 생성자가 있어야 합니다.  
  
-   변수 또는 개인 병렬 영역 내부에 표시 되는 **감소** 절은 **병렬** 지시문에 지정할 수 없습니다는 **firstprivate** 절에는 병렬 구문에 바인딩하는 작업 공유 지시문입니다.