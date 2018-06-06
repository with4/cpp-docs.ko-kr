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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33328028"
---
# <a name="implement-pure-virtuals"></a>순수 가상 구현
**대상:** 클래스의 모든 순수 가상 메서드를 구현하는 데 필요한 코드를 즉시 생성할 수 있습니다. 

**시기:** 순수 가상 함수가 있는 클래스에서 상속받으려는 경우.  

**이유:** 모든 순수 가상 함수를 하나씩 수동으로 구현할 수 있지만 이 기능은 모든 메서드 시그니처를 자동으로 생성합니다.

**방법:**

1. 기본 클래스의 순수 가상 함수를 구현할 클래스 위에 텍스트 또는 마우스 커서를 놓습니다.

   ![강조 표시된 코드](images/virtuals_highlight.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.** 를 눌러 상황에 맞는 메뉴에서 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 **'*ClassName*' 클래스의 모든 순수 가상 구현**을 선택합니다. 여기서 *ClassName*은 선택된 클래스의 이름입니다.
   * **마우스**
     * 상황에 맞는 메뉴에서 마우스 오른쪽 단추를 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, **'*ClassName*' 클래스의 모든 순수 가상 구현**을 선택합니다. 여기서 *ClassName*은 선택된 클래스의 이름입니다.

1. 순수 가상 메서드 시그니처가 자동으로 만들어지고 구현할 준비가 됩니다.

   ![순수 가상 구현 결과](images/virtuals_result.png)
