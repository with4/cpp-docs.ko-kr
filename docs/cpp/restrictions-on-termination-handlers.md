---
title: "종료 처리기에 대 한 제한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers, limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0c7be69cf8371b354f13863177d48cbb00f647b0
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="restrictions-on-termination-handlers"></a>종료 처리기에 대한 제한
`goto` 문을 사용하여 `__try` 문 블록 또는 `__finally` 문 블록으로 점프할 수 없습니다. 대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. 그러나 `__try` 문 블록 밖으로 점프할 수 있습니다. 또한 `__finally` 블록 안에 예외 처리기나 종료 처리기를 중첩시킬 수 없습니다.  
  
 또한 종료 처리기에 허용되는 몇 종류의 코드는 그 결과가 불확실하기 때문에 주의하여 사용해야 합니다(있는 경우). 그 중 하나는 `goto` 문 블록 밖으로 점프하는 `__finally` 문입니다. 블록이 정상적인 종료의 일부분으로 실행되는 경우 비정상적인 일이 생기지 않지만 시스템이 스택을 해제하는 경우 해제가 중지되고 비정상적인 종료가 없는 것처럼 현재 함수가 제어권을 갖습니다.  
  
 `return` 문 블록 안에 `__finally` 문을 사용해도 상황이 거의 같습니다. 종료 처리기를 포함하는 함수의 직접 실행 호출자에게 제어가 반환됩니다. 시스템이 스택을 해제 중이었으면 이 프로세스가 중단되고, 예외가 발생하지 않은 것처럼 프로그램이 계속됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [종료 처리기 작성](../cpp/writing-a-termination-handler.md)   
 [구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)
