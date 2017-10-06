---
title: "불완전한 형식 | Microsoft Docs"
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
- void keyword [C], incomplete
- types [C], incomplete
- incomplete types
- unions, incomplete
- arrays [C], incomplete types
- void keyword [C]
- structures, incomplete
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: ebc73813c28f5ccd25b28cadf283412a204b57d3
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="incomplete-types"></a>불완전한 형식
불완전한 형식은 식별자를 설명하지만 식별자 크기를 확인하는 데 필요한 정보는 포함하지 않는 형식입니다. "불완전한 형식"은 다음 형식일 수 있습니다.  
  
-   아직 멤버를 지정하지 않은 구조체 형식  
  
-   아직 멤버를 지정하지 않은 공용 구조체 형식  
  
-   아직 차원을 지정하지 않은 배열 형식  
  
 void 형식은 완료할 수 없는 불완전한 형식입니다. 불완전한 형식을 완료하려면 누락된 정보를 지정합니다. 다음 예에서는 불완전한 형식을 만들고 완료하는 방법을 보여 줍니다.  
  
-   불완전한 구조체 형식을 만들려면 해당 멤버를 지정하지 않고 구조체 형식을 선언합니다. 이 예에서 `ps` 포인터는 `student`라는 불완전한 구조체 형식을 가리킵니다.  
  
    ```  
    struct student *ps;  
    ```  
  
-   불완전한 구조체 형식을 완료하려면 다음과 같이 멤버를 지정하여 나중에 같은 범위에서 동일 구조체 형식을 선언합니다.  
  
    ```  
    struct student  
    {  
        int num;  
    }                   /* student structure now completed */  
    ```  
  
-   불완전한 배열 형식을 만들려면 해당 반복 횟수를 지정하지 않고 배열 형식을 선언합니다. 예:  
  
    ```  
    char a[];  /* a has incomplete type */  
    ```  
  
-   불완전한 배열 형식을 완료하려면 다음과 같이 반복 횟수를 지정하여 나중에 같은 범위에서 동일한 이름을 선언합니다.  
  
    ```  
    char a[25]; /* a now has complete type */  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [선언 및 형식](../c-language/declarations-and-types.md)
