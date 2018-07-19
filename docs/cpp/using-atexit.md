---
title: Atexit 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- atexit
dev_langs:
- C++
helpviewer_keywords:
- atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1bb0c89c34b5107326a961e874289d20cbd2385c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420969"
---
# <a name="using-atexit"></a>atexit 사용
와 [atexit](../c-runtime-library/reference/atexit.md) 함수 프로그램 종료 전에 실행 하는 종료 처리 함수를 지정할 수 있습니다. `atexit`를 호출하기 전에 초기화된 전역 정적 개체는 종료 처리 함수의 실행 전에 소멸되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [추가 종료 고려 사항](../cpp/additional-termination-considerations.md)