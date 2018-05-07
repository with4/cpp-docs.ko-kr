---
title: 컴파일러 오류 C3550 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3550
dev_langs:
- C++
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91003af2069ba32083caefa8f5a79cbe0e7cd9c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3550"></a>컴파일러 오류 C3550
이 컨텍스트에 일반 'decltype(auto)'만 사용할 수 있습니다.  
  
 `decltype(auto)`을 함수 반환 형식의 자리 표시자로 사용하는 경우 자체에서 사용되어야 합니다. 포인터 선언(`decltype(auto*)`), 참조 선언(`decltype(auto&)`) 또는 이러한 기타 모든 한정의 일부로 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [auto](../../cpp/auto-cpp.md)