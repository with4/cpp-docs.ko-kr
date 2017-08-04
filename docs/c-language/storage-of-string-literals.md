---
title: "문자열 리터럴 저장소 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- string literals, storage
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
caps.latest.revision: 9
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 8ee698c1db706c45b1b283a33ec95c135907e031
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="storage-of-string-literals"></a>문자열 리터럴 저장소
리터럴 문자열의 문자는 인접한 메모리 위치에 순서대로 저장됩니다. 문자열 리터럴 내의 이스케이프 시퀀스(예: **\\\\** 또는 **\\"**)는 단일 문자로 계산됩니다. null 문자(**\0** 이스케이프 시퀀스로 표현됨)가 각 문자열 리터럴에 자동으로 추가되어 끝을 표시합니다. (이러한 7번째 [변환 단계](../preprocessor/phases-of-translation.md) 중에 발생합니다.) 컴파일러는 서로 다른 두 주소에 동일한 두 문자열을 저장할 수 없습니다. [/GF](../build/reference/gf-eliminate-duplicate-strings.md)는 컴파일러가 동일한 문자열의 단일 복사본을 실행 파일에 배치하도록 합니다.  
  
## <a name="remarks"></a>설명  
 **Microsoft 전용**  
  
 문자열에는 정적 저장 기간이 있습니다. 저장 기간에 대한 자세한 내용은 [저장소 클래스](../c-language/c-storage-classes.md)를 참조하세요.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [C 문자열 리터럴](../c-language/c-string-literals.md)
