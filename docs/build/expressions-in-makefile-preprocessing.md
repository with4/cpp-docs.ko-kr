---
title: "메이크파일 전처리 식 | Microsoft Docs"
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
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7bea4f0c4fea2c2d04681674734bc989424c7951
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="expressions-in-makefile-preprocessing"></a>메이크파일 전처리 식
**! IF** 또는 **! ELSE IF** `constantexpression` 10 진수 또는 C 언어 표기법으로 정수 상수, 문자열 상수 또는 명령으로 구성 됩니다. 그룹 식에 괄호를 사용 합니다. 식을 사용 하 여 C 스타일 부호 있는 정수 (long) 산술; 숫자는 32 비트 2의 보수 형식 범위-2147483648에서 2147483647입니다.  
  
 식 상수 값, 명령, 문자열, 매크로 및 파일 시스템 경로에서 종료 코드에 대해 작동 하는 연산자를 사용할 수 있습니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
 [메이크파일 전처리 연산자](../build/makefile-preprocessing-operators.md)  
  
 [전처리에서 프로그램 실행](../build/executing-a-program-in-preprocessing.md)  
  
## <a name="see-also"></a>참고 항목  
 [메이크파일 전처리](../build/makefile-preprocessing.md)