---
title: 예외 처리기에 대 한 제한 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8775f752a541d2a250e9c1c5a0c325b684335988
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464602"
---
# <a name="restrictions-on-exception-handlers"></a>예외 처리기에 대한 제한
예외 처리기를 사용 하 여 코드에서의 주요 제한 사항은 사용할 수 없습니다는 **goto** 으로 이동 하는 문을 **__try** 문 블록입니다. 대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. 외부로 이동할 수는 **__try** 문을 차단 하 고 선택 하 여 예외 처리기를 중첩 합니다.  
  
## <a name="see-also"></a>참고자료  
 [예외 처리기 작성](../cpp/writing-an-exception-handler.md)   
 [구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)