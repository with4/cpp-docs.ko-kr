---
title: "예외 처리기에 대 한 제한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 42207a9bc1e9a355e6785a609ab0b130be063d55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="restrictions-on-exception-handlers"></a>예외 처리기에 대한 제한
코드에서 예외 처리기를 사용할 때의 주요 제한 사항은 `goto` 문을 사용하여 `__try` 문 블록으로 이동할 수 없다는 점입니다. 대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. `__try` 문 블록의 외부로 이동할 수 있으며 선택한 예외 처리기를 중첩할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리기 작성](../cpp/writing-an-exception-handler.md)   
 [구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)