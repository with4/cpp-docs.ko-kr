---
title: 순수 가상 구현 | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afce516f2718a76658846ed4f992aeabff75330b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="implement-pure-virtuals"></a>순수 가상 구현
**:** 즉시 클래스에서 모든 순수 가상 메서드를 구현 하는 데 필요한 코드를 생성할 수 있습니다. 

**경우:** 순수 가상 함수를 사용 하 여 클래스에서 상속 하려는 경우.  

**이유:** 이 기능에서 모든 메서드 시그니처를 자동으로 생성 되지만 모든 순수 가상 함수 하나씩 여을 수동으로 구현할 수 있습니다.

**방법:**

1. 기본 클래스의 순수 가상 함수를 구현 하려는 클래스를 통해 텍스트 또는 마우스 커서를 놓습니다.

   ![강조 표시된 코드](images/virtuals_highlight.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.** 를 눌러 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **클래스의 모든 순수 가상 구현*ClassName*'** 상황에 맞는 메뉴에서 여기서  *ClassName* 선택한 클래스의 이름입니다.
   * **마우스**
     * 마우스 오른쪽 단추로 클릭 하 고 선택 된 **빠른 작업 및 리팩터링** 메뉴를 선택 **클래스의 모든 순수 가상 구현*ClassName*'** 상황에 맞는 메뉴에서 위치  *ClassName* 선택한 클래스의 이름입니다.

1. 순수 가상 메서드 시그니처를 자동으로 생성 된, 구현할 준비가 됩니다.

   ![순수 가상 구현 결과](images/virtuals_result.png)
