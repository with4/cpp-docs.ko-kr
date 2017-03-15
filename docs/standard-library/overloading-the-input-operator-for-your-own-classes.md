---
title: "고유 클래스에 대해 &gt;&gt; 오버로드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
caps.latest.revision: 8
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4ac48927cc0b68dc958a09ee541c41895f11f86b
ms.lasthandoff: 02/24/2017

---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>고유 클래스에 대해 &gt;&gt; 연산자 오버로드
입력 스트림은 표준 형식에 대해 추출(`>>`) 연산자를 사용합니다. 고유 형식용으로 유사한 추출 연산자를 작성할 수 있으며, 이 경우 공백을 정확하게 사용해야 합니다.  
  
 앞에서 살펴보았던 `Date` 클래스에 대한 추출 연산자의 한 예가 아래에 나와 있습니다.  
  
```  
istream& operator>> (istream& is, Date& dt)  
{  
    is>> dt.mo>> dt.da>> dt.yr;  
    return is;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [입력 스트림](../standard-library/input-streams.md)


