---
title: "링크 형식 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
- linkage [C++], types of
- types [C++], linkage
- internal linkage, types of linkage
- external linkage, linkage types
ms.assetid: 41326c7f-4602-4bad-a648-697604858ba0
caps.latest.revision: 7
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: b4d5aca80e7b074c86a1446fabb9852f3b9fe3a9
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="types-of-linkage"></a>링크 형식
개체 및 함수 이름을 변환 단위 간에 공유하는 방법을 링크라고 합니다. 이러한 이름에는 다음이 있을 수 있습니다.  
  
-   내부 링크 - 이 경우 이러한 이름이 해당 변환 단위 내에 있는 프로그램 요소만 참조하며 다른 변환 단위와는 공유되지 않습니다.  
  
     다른 변환 단위의 동일한 이름이 다른 개체 또는 다른 클래스를 참조할 수 있습니다. 내부 링크가 있는 이름은 해당 변환 단위에서 로컬에 있는 것이라고도 합니다.  
  
     내부 링크가 있는 이름의 선언 예는 다음과 같습니다.  
  
    ```  
    static int i;   // The static keyword ensures internal linkage.  
    ```  
  
-   외부 링크 - 이 경우 이러한 이름이 프로그램의 모든 변환 단위에서 프로그램 요소를 참조할 수 있으며 프로그램 요소가 변환 단위 간에 공유됩니다.  
  
     다른 변환 단위의 동일한 이름은 동일한 개체 또는 클래스를 참조합니다. 외부 링크가 있는 이름은 전역에 있는 것이라고도 합니다.  
  
     외부 링크가 있는 이름의 선언 예는 다음과 같습니다.  
  
    ```  
    extern int i;  
    ```  
  
-   링크 없음 - 이 경우 이름이 고유 엔터티를 참조합니다. 다른 범위의 동일한 이름은 동일한 개체를 참조할 수 없습니다. 열거형을 예로 들 수 있습니다. 그러나 링크 없이 개체에 대한 포인터를 전달할 수 있습니다. 이것은 개체를 다른 변환 단위에서 액세스할 수 있도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 및 링크](../cpp/program-and-linkage-cpp.md)
