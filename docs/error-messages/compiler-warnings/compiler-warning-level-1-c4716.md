---
title: 컴파일러 경고 (수준 1) C4716 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4716
dev_langs:
- C++
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be620264c315fc9c2ff3cd4cb91bd9d77c8a4d07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288855"
---
# <a name="compiler-warning-level-1-c4716"></a>컴파일러 경고(수준 1) C4716
'function'은 값을 반환해야 합니다.  
  
 지정된 된 함수는 값을 반환 하지 않았습니다.  
  
 반환 형식이 void 수행할 수 있는 유일한 함수 반환 값 없이 반환 명령을 사용 합니다.  
  
 정의 되지 않은 값이이 함수를 호출할 때 반환 됩니다.  
  
 이 경고는 오류를 자동으로 승격 됩니다. 사용 하 여이 동작을 수정 하려는 경우 [#pragma 경고](../../preprocessor/warning.md)합니다.  
  
 다음 샘플에서는 C4716 오류가 생성 됩니다.  
  
```  
// C4716.cpp  
// compile with: /c /W1  
// C4716 expected  
#pragma warning(default:4716)  
int test() {  
   // uncomment the following line to resolve  
   // return 0;  
}  
```