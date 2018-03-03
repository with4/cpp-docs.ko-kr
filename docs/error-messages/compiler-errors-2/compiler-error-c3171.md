---
title: "컴파일러 오류 C3171 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3171
dev_langs:
- C++
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed053e37dfbf5f3c85cf1f8ec44912eca3148315
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3171"></a>컴파일러 오류 C3171
'module': 프로젝트에서 다른 모듈 특성을 지정할 수 없습니다  
  
 [모듈](../../windows/module-cpp.md) 의 두 컴파일에 파일에서 다른 매개 변수 목록 사용 하 여 특성이 발견 되었습니다. 고유한 하나만 `module` 컴파일마다 특성을 지정할 수 있습니다.  
  
 동일한 `module` 둘 이상의 소스 코드 파일에서 특성을 지정할 수 있습니다.  
  
 예를 들어 경우 다음 `module` 특성이 발견 되었습니다.  
  
```  
// C3171.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];  
int main() {}  
```  
  
 그리고  
  
```  
// C3171b.cpp  
// compile with: C3171.cpp  
// C3171 expected  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];  
```  
  
 다르다는 C3171 (버전 값이 서로 참고).