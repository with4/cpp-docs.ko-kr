---
title: 종료 처리기에 대 한 제한 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ae16363956afc7cca853307ef2888846a02864d
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461772"
---
# <a name="restrictions-on-termination-handlers"></a>종료 처리기에 대한 제한
사용할 수 없습니다는 **goto** 으로 이동 하는 문에 **__try** 문 블록 또는 **__finally** 문 블록. 대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. 그러나 (의 외부로 이동할 수 있습니다는 **__try** 문 블록입니다.) 예외 처리기 나 종료 처리기를 중첩할 수 없습니다는 또한을 **__finally** 블록입니다.  
  
 또한 종료 처리기에 허용되는 몇 종류의 코드는 그 결과가 불확실하기 때문에 주의하여 사용해야 합니다(있는 경우). 하나는 **goto** 밖으로 점프 문을 **__finally** 문 블록입니다. 블록이 정상적인 종료의 일부분으로 실행되는 경우 비정상적인 일이 생기지 않지만 시스템이 스택을 해제하는 경우 해제가 중지되고 비정상적인 종료가 없는 것처럼 현재 함수가 제어권을 갖습니다.  
  
 A **반환** 내에서 문을 **__finally** 문 블록 표시와 거의 같은 상황입니다. 종료 처리기를 포함하는 함수의 직접 실행 호출자에게 제어가 반환됩니다. 시스템이 스택을 해제 중이었으면 이 프로세스가 중단되고, 예외가 발생하지 않은 것처럼 프로그램이 계속됩니다.  
  
## <a name="see-also"></a>참고자료  
 [종료 처리기 작성](../cpp/writing-a-termination-handler.md)   
 [구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)