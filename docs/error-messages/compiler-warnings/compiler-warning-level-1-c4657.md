---
title: "컴파일러 경고 (수준 1) C4657 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4657
dev_langs:
- C++
helpviewer_keywords:
- C4657
ms.assetid: eb750050-cea6-4ead-b80c-d5dcd4971cfc
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 2ac407b6e2ed17eb7a9c1f1232756e9977ed7511
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4657"></a>컴파일러 경고(수준 1) C4657
최근 빌드 후 새로 만들어진 데이터 형식이 식에 들어 있습니다.  
  
 데이터 형식을 추가하거나 변경하여 마지막으로 성공한 빌드 후 소스 코드에 대해 새롭게 만들었습니다. 편집하며 계속하기는 기존 데이터 형식에 대한 변경 내용은 지원하지 않습니다.  
  
 이 경고는 뒤에 항상 [심각한 오류 C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md)합니다. 자세한 내용은 참조는 [지원 되는 코드 변경](/visualstudio/debugger/supported-code-changes-cpp)합니다.  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>현재 디버그 세션을 끝내지 않고 이 경고를 제거하려면  
  
1.  데이터 형식을 오류가 발생하기 이전 상태로 다시 변경합니다.  
  
2.  **디버그** 메뉴에서 **코드 변경 내용 적용**을 선택합니다.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>소스 코드를 변경하지 않고 이 오류를 제거하려면  
  
1.  **디버그** 메뉴에서 **디버깅 중지**를 선택합니다.  
  
2.  **빌드** 메뉴에서 **빌드**를 선택합니다.
