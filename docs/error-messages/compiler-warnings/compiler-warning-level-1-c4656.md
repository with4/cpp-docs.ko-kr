---
title: "컴파일러 경고 (수준 1) C4656 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4656
dev_langs:
- C++
helpviewer_keywords:
- C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
caps.latest.revision: 7
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: b88f2add0a7b8f365d3617b8eb28eecdfa5a0a26
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4656"></a>컴파일러 경고(수준 1) C4656
'symbol': 새로운 또는 마지막 빌드 이후에 변경 된 또는 다른 곳에서 다르게 정의 된 데이터 형식  
  
 데이터 형식을 추가하거나 변경하여 마지막으로 성공한 빌드 후 소스 코드에 대해 새롭게 만들었습니다. 편집하며 계속하기는 기존 데이터 형식에 대한 변경 내용은 지원하지 않습니다.  
  
 이 경고는 뒤에 항상 [심각한 오류 C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md)합니다. 자세한 내용은 참조는 [지원 되는 코드 변경](/visualstudio/debugger/supported-code-changes-cpp)합니다.  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>현재 디버그 세션을 끝내지 않고 이 경고를 제거하려면  
  
1.  데이터 형식을 오류가 발생하기 이전 상태로 다시 변경합니다.  
  
2.  **디버그** 메뉴에서 **코드 변경 내용 적용**을 선택합니다.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>소스 코드를 변경하지 않고 이 오류를 제거하려면  
  
1.  **디버그** 메뉴에서 **디버깅 중지**를 선택합니다.  
  
2.  **빌드** 메뉴에서 **빌드**를 선택합니다.
