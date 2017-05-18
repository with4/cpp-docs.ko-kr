---
title: "컴파일러 경고 (수준 4) C4985 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 4a36692420ea9d5547f236c1e5dfeaa269afbb67
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4985"></a>컴파일러 경고(수준 4) C4985
'symbol name': 이전 선언에 특성이 없습니다.  
  
 현재 메서드 선언 또는 정의의 Microsoft SAL(Source code Annotation Language) 주석이 이전 선언의 주석과 다릅니다. 메서드 정의 및 선언에서 동일한 SAL 주석을 사용해야 합니다.  
  
 SAL은 함수에서 해당 매개 변수를 사용하는 방법, 이에 대한 가정 및 완료에 대한 보장을 설명하는 주석 모음을 제공합니다. 주석은 sal.h 헤더 파일에 정의됩니다.  
  
 프로젝트에 없는 경우 SAL 매크로가 확장 하지 것입니다는 [/analyze](../../build/reference/analyze-code-analysis.md) 플래그를 지정 합니다. **/analyze**를 지정하면 **/analyze**없이 나타난 경고 또는 오류가 없더라도 컴파일러에서 C4985가 발생할 수 있습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  메서드 정의 및 모든 해당 선언에서 동일한 SAL 주석을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SAL 주석](../../c-runtime-library/sal-annotations.md)
