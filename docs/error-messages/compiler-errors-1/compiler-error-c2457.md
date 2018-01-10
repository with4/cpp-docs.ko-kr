---
title: "컴파일러 오류 C2457 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2457
dev_langs: C++
helpviewer_keywords: C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff89bb3635936ae0f797438d73f71adf1ef08de7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2457"></a>컴파일러 오류 C2457

> '*매크로*': 미리 정의 된 매크로 함수 본문 외부에 사용할 수 없습니다

와 같은 미리 정의 된 매크로 사용 하려고 했습니다. [&#95; &#95; 함수 &#95; #95 ](../../preprocessor/predefined-macros.md), 전역 공간에서 합니다.

## <a name="example"></a>예

다음 샘플에서는 C2457 오류가 발생 하 고 올바른 사용법을 보여 줍니다.

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```