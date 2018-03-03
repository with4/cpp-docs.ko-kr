---
title: "모듈 정의 문의 규칙 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- .def
dev_langs:
- C++
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 40eb4875b195871aff8d274667e005d63424a110
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="rules-for-module-definition-statements"></a>모듈 정의 문의 규칙
다음 구문 규칙은.def 파일의 모든 문에 적용 됩니다. 각 문을 사용 하 여 특정 문에 적용 되는 다른 규칙 설명 되어 있습니다.  
  
-   문, 특성 키워드 및 사용자 지정 식별자는 대/소문자 구분 합니다.  
  
-   긴 파일 공백 또는 세미콜론 (;)를 포함 하는 이름은 큰따옴표 (")로 묶어야 합니다.  
  
-   문 키워드 인수에서 구분 하 고 각 문을 구분 하나 이상의 공백, 탭 또는 줄 바꿈 문자를 사용 합니다. 콜론 (:) 또는 등호 (=) 인수를 지정 하는 0 이나 더 많은 공백, 탭 또는 줄 바꿈 문자로 묶 였는 합니다.  
  
-   A **이름** 또는 **라이브러리** 문을 사용 하는 경우 앞에 야 다른 모든 문입니다.  
  
-   **섹션** 및 **내보내기** 문을.def 파일에 두 번 이상 나타날 수 있습니다. 각 문에 하나 이상의 공백, 탭 또는 줄 바꿈 문자로 구분 해야 하는 여러 개의 사양을 사용할 수 있습니다. 문 키워드는 첫 번째 사양 적이 한 번 표시 되 고 각각의 추가 사양 앞에서 반복 될 수 있습니다.  
  
-   많은 문에 해당 하는 링크 명령줄 옵션이 권한이 있습니다. 자세한 내용을 보려면 해당 링크 옵션에 대 한 설명을 참조 하십시오.  
  
-   .Def 파일의 주석에 세미콜론 (;)으로 표시 됩니다. 각 주석 행의 시작 부분에 있습니다. 주석 선은 문을 수 없지만 여러 줄 문의 사양 사이 나타날 수 있습니다. (**섹션** 및 **내보내기** 은 여러 줄로 된 문이.)  
  
-   숫자 인수가 진수나 16 진수로 10 진수로 지정 합니다.  
  
-   문자열 인수 일치 하는 경우는 [예약어](../../build/reference/reserved-words.md), 큰따옴표 (")에 포함 되어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [모듈 정의(.Def) 파일](../../build/reference/module-definition-dot-def-files.md)  