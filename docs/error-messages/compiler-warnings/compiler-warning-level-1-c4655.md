---
title: "컴파일러 경고 (수준 1) C4655 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4655
dev_langs:
- C++
helpviewer_keywords:
- C4655
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
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
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 058086bb4617f59f53de706b38477bd868e297d3
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4655"></a>컴파일러 경고(수준 1) C4655
**'**   
 ***기호* ': 변수 형식이 마지막 빌드 이후 새 프로젝트 이거나 다른 곳에서 다르게 정의 된**  
  
 마지막으로 빌드가 성공한 이후 새 데이터 형식을 변경하거나 추가했습니다. 편집하며 계속하기는 기존 데이터 형식에 대한 변경 내용은 지원하지 않습니다.  
  
 이 경고 다음에 [심각한 오류 C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md)합니다. 자세한 내용은 참조는 [지원 되는 코드 변경](/visualstudio/debugger/supported-code-changes-cpp)합니다.  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>현재 디버그 세션을 끝내지 않고 이 경고를 제거하려면  
  
1.  데이터 형식을 오류가 발생하기 이전 상태로 다시 변경합니다.  
  
2.  **디버그** 메뉴에서 **코드 변경 내용 적용**을 선택합니다.  
  
### <a name="to-remove-this-warning-without-changing-your-source-code"></a>소스 코드를 변경하지 않고 이 경고를 제거하려면  
  
1.  **디버그** 메뉴에서 **디버깅 중지**를 선택합니다.  
  
2.  **빌드** 메뉴에서 **빌드**를 선택합니다.
